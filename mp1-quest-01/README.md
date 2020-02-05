
## 1st QUEST
<br/>

## 목 표
##### `MP1 타겟 보드에 STM32MP1 ecosystem 'Starter Package'를 다운로드하고 동작시켜 본다.`
<br/>

## 실 습
### STEP.1
- [Unpack the STM32MP157C-DK2 board](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Unpack_the_STM32MP157C-DK2_board) 의 내용을 참고하여 실습할 보드를 준비한다.
  - 이어지는 실습을 위해서 [4 Connection](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Unpack_the_STM32MP157C-DK2_board#Connection)의 `Power supply`, `USB OTG`, `ST-LINK/V2-1`의 3가지 케이블 연결은 필수.
<br/><br/>

### STEP.2
  > [Populate the target and boot the image](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Populate_the_target_and_boot_the_image)의 내용대로 호스트에 'Starter Package'를 위한 환경을 구축하고 다운로드하여 동작을 확인한다.<br/>
#### § 호스트 환경 설정 (Network, Tools)
  - 리눅스 호스트가 준비 안된 경우 먼저 호스트 환경 [Ubuntu 18.04 LTS](https://ubuntu.com/#download)을 구축.
  - 네트워크 환경이 프록시 서버를 경유하는 경우 [Check the host computer Internet access](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Populate_the_target_and_boot_the_image#Check_the_host_computer_Internet_access)를 참조하여 설정해 준다.
  - [Install tools](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Populate_the_target_and_boot_the_image#Install_the_tools) 항목을 타겟 이미지 다운로드 툴체인을 설치한다.
    - STM32CubeProgrammer + USB link
#### § 이미지 다운로드
  - [Download Image](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Populate_the_target_and_boot_the_image#Download_the_image)를 참고하여 Starter package 파일을 다운로드한다.
    > 해당 Starter package 이미지는 미리 컴파일 된 것으로 사용자는 이미지를 다운로드하고 미리 탑재된 데모를 통해 기본적인 평가가 가능하다.
#### § 보드에 이미지를 다운로드 
  - [Populate the Board](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Populate_the_target_and_boot_the_image#Populate_the_SDCard)의 내용대로 보드를 설정하고 CubeProgrammer를 통해 이미지를 다운로드 한다.
    - 특히 다운로드를 위해서는 Boot pin을 조작해 boot mode를 `Serial`로 설정해야 함에 유의한다. Boot mode에 대한 자세한 내용은 [Boot Pin](https://wiki.st.com/stm32mpu/wiki/STM32MP15_ROM_code_overview#Configuration)을 참고.
    - STM32CubeProgrammer의 경우 command line 수행도 가능하다. [이곳](https://wiki.st.com/stm32mpu/wiki/STM32CubeProgrammer#How_to_flash_with_STM32CubeProgrammer)을 참고.
      - `STM32_Programmer_CLI -l`
      - `STM32_Programmer_CLI -c port=usb1 -w flashlayout_st-image-weston/FlashLayout_sdcard_stm32mp157c-dk2-trusted.tsv`
      <img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-01/images/about.usb.png" alt="" width="80%" height="80%" />
    - DK2 보드는 Sdcard를 단일 스토리지로 가지기 때문에 이미지는 이곳으로 다운로드 된다. (FlashLayout_sdcard_*.tsv)
    - 다운로드 과정은 DK2 보드의 LCD 화면과 `ST-LINK/V2-1`를 통해 연결된 CDC terminal(/dev/ttyACM*)로도 확인이 가능.
#### § 보드를 정상 부팅하여 동작 확인
  - [Boot the board](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start/Populate_the_target_and_boot_the_image#Boot_the_board)를 참고하여 보드가 정상 부팅하여 이미지가 잘 다운로드 되었는지 확인한다.
    - 마찬가지로 Boot pin - boot mode 설정에 유의한다.
    - `ST-LINK/V2-1`이 연결된 경우에는 부트 및 리눅스 커널 로그가 확인 가능하고 부팅 완료 후 쉘 프롬프트가 표시되면 기본적인 명령어를 입력할 수 있다. 확인해 보도록 하자.
    <img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-01/images/about.shell.png" alt="" width="80%" height="80%" /><br/>
      <img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-01/images/shell-log.png" alt="" width="80%" height="80%" />
