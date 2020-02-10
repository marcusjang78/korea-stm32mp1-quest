
## 2nd QUEST
<br/>

## 목 표
##### `STM32MP1 Developer Package의 구성을 확인하고 SDK를 사용하여 간단한 Application을 작성하고 동작시켜 본다. (A7 part)`
<br/>

## 실 습
### PREFACE
  - 이번 Quest의 주제는 Wiki page, [Develop on Arm® Cortex®-A7](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7) 내용을 확인하고 실습해 보는 것이다.<br/>
  Developer Package는 Starter Package를 기반으로 제공되는 (이후 설명할 Distribution Package에 비해) 제한적인 개발, 배포가 가능한 소프트웨어 패키지로 정의된다.<br/>
  Developer Package에 대한 상세 내용을 [[패키지 선택 - Developer Package]](https://wiki.st.com/stm32mpu/wiki/Which_STM32MPU_Embedded_Software_Package_better_suits_your_needs#Developer_Package) 항목을 통해 살펴보자.

<br/><br/>
### STEP.1
Deveoper Package에서는 사용자가 타겟 시스템을 빌드했던 환경(컴파일러, 라이브러리 등)을 SDK(Sofeware Developement Kit)로 제공한다.<br/>
사용자는 이 도구를 통해 타겟 시스템과 동일한 설정을 기반으로 한 머신 코드, Application을 생성할 수 있다.<br/>
먼저 준비 과정은 크게 호스트에 의존 패키지를 설치하는 것과 제공되는 SDK를 다운로드 받아 설치하는 2단계로 구성된다.<br/>
  - [Host computer configuration](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Install_the_SDK#Host_computer_configuration)를 참고하여 호스트 의존 패키지를 설치.
  - [Download the SDK](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Install_the_SDK#Download_the_SDK)를 참고하여 SDK를 다운로드, 설치하고 설정.
    - [Run the SDK installation script](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Install_the_SDK#Run_the_SDK_installation_script)
    - [Starting up the SDK](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Install_the_SDK#Starting_up_the_SDK)

<br/><br/>
### STEP.2
#### § 타겟 보드 준비
  - Developer Package는 기본적으로 Starter Package에서 제공되는 이미지에 핵심 소프트웨어 컴포넌트의 수정이 가능하도록 각각의 개별 전체 소스코드와 함께 이를 cross-build 할 수 있는 SDK를 제공한다.<br/>따라서 Starter Package가 설치된 타겟 보드(DK2)가 요구된다.<br/>
    > 만약 타겟 보드(DK2)에 Starter Package가 설치되지 않은 경우라면 이전 [`1st QUSET`](https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-01/README.md) 또는 [`Getting Started - Let's start`](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start)를 참고하여 패키지를 먼저 설치하고 진행하도록 하자.
  - 참고로 Developer Package에서 제공하는 핵심 소프트웨어 컴포넌트는 아래와 같다.
    - U-Boot
    - Trusted Firmware-A (TF-A)
    - Linux® kernel
    - (Optionally) Open source Trusted Execution Environment (OP-TEE)

<br/><br/>
### STEP.3
#### § A7 어플리케이션 작성 및 확인
  - 기본 제공되는 ecosystem, st-image-weston (openstlinux-weston)은 [Wayland](https://ko.wikipedia.org/wiki/%EC%9B%A8%EC%9D%B4%EB%9E%9C%EB%93%9C) 기반에 GTK+ GUI 환경을 제공한다.<br/>
  [Create a simple hello-world application](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Create_a_simple_hello-world_application) 항목을 통해 앞서 설치한 SDK를 사용하여 GTK+ application을 빌드하고 타겟에 배포(deploy by scp tool)하여 동작을 확인해 볼 수 있다.
    <kbd><img src="https://wiki.st.com/stm32mpu/nsfr_img_auth.php/thumb/c/c9/STM32MP1_gtk_hello_world.png/600px-STM32MP1_gtk_hello_world.png" alt="" width="100%" height="100%" /></kbd>
  - 간단한 Console Application 빌드도 가능하다.
    <img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-02/images/host-console-hello-world.png" alt="" width="100%" height="100%" />
    <img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-02/images/target-console-hello-world.png" alt="" width="100%" height="100%" />

<br/><br/>
(3) Linux kernel 수정 및 Rebuild<br/>
