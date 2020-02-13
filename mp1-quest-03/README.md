
## 3rd QUEST
<br/>

## 목 표
##### `STM32MP1 Developer Package의 Cortex-M4 개발 환경을 설치하고 간단한 예제를 수행시켜 본다. (M4 part)`
<br/>

## 실 습
### PREFACE
  이번 Quest의 주제는 [Develop on Arm® Cortex®-M4](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-M4) 내용을 확인하고 실습해 보는 것이다.<br/>
  STM32MP1 시리즈는 Arm® Cortex®-A7(dual or single)과 Cortex®-M4의 비대칭(Heterogeneous) 코어 구조를 가진다.<br/>
  M4 영역에서는 A7과 같은 큰 코어 및 Linux와 같은 범용 시스템에서 달성하기 어려운 실시간성, 저전력 요구사항 충족이 가능하다.<br/>
  그리고 소프트웨어 개발은 STM32 MCU의 ecosystem을 거의 그대로 사용하는 것을 목표로 하기 때문에 기존의 STM32 MCU 개발자들은 하드웨어 구조에 대한 특성 이해, A7 영역과의 통신 부분 정도를 제외하고는 익숙한 개발환경하에서 빠른 개발을 시작할 수 있다.

<br/><br/>
### STEP.1
  이번 단계에서는 STM32MP1 시리즈의 M4 영역 개발을 위한 사전 준비 단계로 통합 개발 환경(IDE)와 MP1-M4를 위한 소프트웨어 패키지를 설치하는 과정을 다룬다. 여기에서 통합 개발 환경(IDE)은 STM32 MCU 개발에 사용되는 IDE와 동일하며, 소프트웨어 패키지는 MP1 HAL 라이브러리 패키지가 된다.
  > CubeIDE에 통합된 CubeMX는 M4 영역을 위한 설정, 코드 생성 외에 A7 영역을 위한 Device Tree 소스도 생성한다.
#### § STM32CubeIDE 설치
  - [Install the STM32CubeIDE](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-M4/Install_the_IDE)의 내용대로 STM32CubeIDE를 설치한다.
    - [Installation Guide](https://www.st.com/resource/en/user_manual/dm00603964.pdf)의 <ins><em>Chapter 4. STM32CubeIDE installation (Linux®)</ins></em> 항목의 지시대로 설치를 수행한다.
      - Quest 기준 기본 호스트 환경이 Ubuntu이므로 <strong><em>`PACKAGE`</em></strong>는 Debian(<strong><em>`deb_bundle.sh`</em></strong>)으로 선택한다.
      - 설치가 정상적으로 완료된 경우 IDE를 실행하여 아래와 같은 화면을 확인할 수 있다.
    <kbd><img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-03/images/stm32cubeide.png" alt="" width="100%" height="100%" /></kbd><br/>
#### § STM32Cube MP1 package 설치
  - [Install STM32Cube MP1 package](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-M4/Install_STM32Cube_MP1_package)를 참고하여 M4 소프트웨어 패키지를 설치한다.
    - <strong>Note</strong>
      - 패키지 다운로드 및 압축해제에 대한 내용이 ecosystem 버전별로 나뉘어 설명되어 있다. 반드시 타겟에 설치된 ecosystem 버전과 동일한 버전의 소프트웨어 패키지를 설치하도록 하자. (해당 Quest는 <ins><em><strong>Ecosystem v.1.1.0</strong></em></ins> 기준으로 작성되어 있다)
      - 소프트웨어 패키지는 STM32 MP1 HAL 라이브러리로 별도의 설치과정은 없다.
    - 설치된 패키지 구조에 대한 간략한 설명을 [STM32Cube MP1 package structure](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-M4/Install_STM32Cube_MP1_package#For_ecosystem_release_v1-1-0_2)를 통해 꼭 한번 확인해 보도록 하자.
    <img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-03/images/stm32cube-mp1-sw-package.png" alt="" width="100%" height="100%" /><br/>
<br/><br/>
### STEP.2 (Working in progress)
  (3) Firmware 작성 및 다운로드

<br/>
