
## 2nd QUEST
<br/>

## 목 표
##### `STM32MP1 Developer Package의 구성을 확인하고 SDK를 사용하여 간단한 Application을 작성하고 동작시켜 본다. (A7 part)`
<br/>

## 실 습
### PREFACE
  - 이번 Quest의 주제는 Wiki page, [Develop on Arm® Cortex®-A7](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7) 내용을 확인하고 실습해 보는 것이다. Developer Package는 Starter Package를 기반으로 제공되는 (이후 설명할 Distribution Package에 비해) 제한적인 개발, 배포가 가능한 소프트웨어 패키지로 정의된다. 자세한 내용은 [[패키지 선택 - Developer Package]](https://wiki.st.com/stm32mpu/wiki/Which_STM32MPU_Embedded_Software_Package_better_suits_your_needs#Developer_Package) 항목을 살펴보자. 이전 Quest인 [Starter Package](https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-01/README.md)와의 차이점을 생각하면서 실습에 임해보자.
<br/><br/>
### STEP.1
  - Deveoper Package에서는 사용자가 타겟 시스템을 빌드했던 환경(컴파일러, 라이브러리 등)을 SDK(Sofeware Developement Kit)으로 제공해 준다. 사용자는 이 도구를 통해 
  
  (https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Install_the_SDK#Host_computer_configuration)
+ [Develop on Arm® Cortex®-A7](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7)의 내용대로 간단한 리눅스 어플리케이션을 작성해 본다.<br/>
  (1) SDK 설치<br/>
  (2) 간단한 Hello-world 작성<br/>
  (3) Linux kernel 수정 및 Rebuild<br/>
