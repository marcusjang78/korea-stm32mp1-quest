
## 1st QUEST (2020.01.13 ~ 17)
<br/>

## 목 표
##### `MP1 타겟 보드에 STM32MP1 ecosystem 'Starter Package'를 다운로드하고 동작시켜 본다.`
<br/>

## 실 습
### STEP.1
+ [Unpack the STM32MP157C-DK2 board](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Unpack_the_STM32MP157C-DK2_board) 의 내용을 참고하여 실습할 보드를 준비한다.
  - 이어지는 실습을 위해서 [4 Connection](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Unpack_the_STM32MP157C-DK2_board#Connection)의 `Power supply`, `USB OTG`, `ST-LINK/V2-1`의 3가지 케이블 연결은 필수.
<br/><br/>

### STEP.2
+ [Populate the target and boot the image](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Populate_the_target_and_boot_the_image)의 내용대로 호스트에 'Starter Package'를 위한 환경을 구축하고 다운로드하여 확인한다.<br/>
  (1) 리눅스 호스트가 준비 안된 경우 먼저 호스트 환경([Ubuntu 18.04 LTS](https://ubuntu.com/#download))을 구축.
  (2) STM32MP15-Ecosystem-v1.1.0 Starter Package Download
  (3) DK2 Board Boot 설정 후 STM32Cube Programmer를 이용하여 보드에 이미지 다운로드
  (4) Consol terminal을 이용하여 부팅로그 확인

### STEP.3
+ [Develop on Arm® Cortex®-A7](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7)의 내용대로 간단한 리눅스 어플리케이션을 작성해 본다.<br/>
  (1) SDK 설치
  (2) 간단한 Hello-world 작성
  (3) Linux kernel 수정 및 Rebuild
  
  
### STEP.4
+ [Develop on Arm® Cortex®-M4](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-M4)의 내용대로 M4 Core의 Firmware를 작성한다.<br/>
  (1) IDE 설치
  (2) STM32Cube MP1 Package 설치
  (3) Firmware 작성 및 다운로드
