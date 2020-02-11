
## 2nd QUEST
<br/>

## 목 표
##### `STM32MP1 Developer Package의 구성을 확인하고 SDK를 사용하여 간단한 Application을 작성하고 동작시켜 본다. (A7 part)`
<br/>

## 실 습
### PREFACE
  이번 Quest의 주제는 [Develop on Arm® Cortex®-A7](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7) 내용을 확인하고 실습해 보는 것이다.<br/>
  Developer Package는 Starter Package를 기반으로 제공되는 (이후 설명할 Distribution Package에 비해) 제한적인 개발, 배포가 가능한 소프트웨어 패키지로 정의된다.<br/>
  Developer Package에 대한 요약을 [[패키지 선택 - Developer Package]](https://wiki.st.com/stm32mpu/wiki/Which_STM32MPU_Embedded_Software_Package_better_suits_your_needs#Developer_Package) 항목을 통해 살펴보고 시작하자.

<br/><br/>
### STEP.1
Deveoper Package에서는 (Ecosystem - Starter Package 용) 타겟 시스템을 빌드했던 환경(컴파일러, 라이브러리 등)을 SDK(Sofeware Developement Kit)로 제공한다.<br/>
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
    - <strong>Note</strong>
      > 타겟 보드(DK2)에 Starter Package가 설치되지 않은 경우라면 이전 [`1st QUSET`](https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-01/README.md) 또는 [`Getting Started - Let's start`](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Let%27s_start)를 참고하여 패키지를 먼저 설치하고 진행하도록 하자.
  - 참고로 Developer Package에서 제공하는 핵심 소프트웨어 컴포넌트는 아래와 같다.
    - U-Boot
    - Trusted Firmware-A (TF-A)
    - Linux® kernel
    - (Optionally) Open source Trusted Execution Environment (OP-TEE)

<br/><br/>
### STEP.3
#### § A7 애플리케이션 작성 및 확인
  - 기본 제공되는 ecosystem, st-image-weston (openstlinux-weston)은 [Wayland](https://ko.wikipedia.org/wiki/%EC%9B%A8%EC%9D%B4%EB%9E%9C%EB%93%9C) 기반에 GTK+ GUI 환경을 제공한다.<br/>
  [Create a simple hello-world application](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Create_a_simple_hello-world_application) 항목을 통해 앞서 설치한 SDK를 사용하여 GTK+ application을 빌드하고 타겟에 배포(deploy by scp tool)하여 동작을 확인해 볼 수 있다.
    <kbd><img src="https://wiki.st.com/stm32mpu/nsfr_img_auth.php/thumb/c/c9/STM32MP1_gtk_hello_world.png/600px-STM32MP1_gtk_hello_world.png" alt="" width="100%" height="100%" /></kbd>
  - 간단한 Console Application 빌드도 가능하다.<br/>
    <img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-02/images/host-console-hello-world.png" alt="" width="100%" height="100%" />
    <img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-02/images/target-console-hello-world.png" alt="" width="100%" height="100%" />
  - <strong>Note</strong>
    - 애플리케이션을 빌드하는 경우, 반드시 SDK 설정([Setup SDK](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Install_the_SDK#Starting_up_the_SDK))이 되어 있어야 함에 유의.

<br/><br/>
### STEP.4
  앞서 설명한대로 Developer Package는 핵심 소프트웨어 컴포넌트로 U-Boot, TF-A, Linux® kernel, OP-TEE의 소스코드를 제공한다.<br/>
  여기에서는 [Modify, rebuild and reload the Linux® kernel](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Modify,_rebuild_and_reload_the_Linux%C2%AE_kernel)를 참고하여 Linux® kernel을 빌드하여 타겟에 배포(Deploy)하는 과정을 확인해 본다.
#### § 리눅스 커널 소스 다운로드, 패치
  - [Download the the Linux® kernel source code](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Modify,_rebuild_and_reload_the_Linux%C2%AE_kernel#Download_the_the_Linux-C2-AE_kernel_source_code) 항목의 링크를 통해 소스 코드를 다운로드하고 이어지는 [Prepare the Linux® kernel source code](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Modify,_rebuild_and_reload_the_Linux%C2%AE_kernel#Prepare_the_Linux-C2-AE_kernel_source_code)를 참고하여 커널 소스 압축을 해제하고 포함된 패치들을 적용한다.
    - <strong><u>Patches</strong></u>: 커널 소스코드에 대한 STM32MP1 종속 패치
    - <strong><u>Fragments</strong></u>: systemd, modules 외 optee에 대한 설정 패치<br/>
  - <strong>Note</strong>
    - 권한 문제가 있을 수 있다. chmod 명령을 사용하자.<br/>
    - Patch, Fragments 적용 쉘 스크립트가 동작하지 않는 경우, 아래의 명령으로 다시 시도해 본다.<br/>
      - <em><strong><u>``` for p in ls ../*.patch; do patch -p1 < $p; done ```</em></strong></u><br/>
      - <em><strong><u>``` for f in ls ../fragment*.config; do scripts/kconfig/merge_config.sh -m -r .config $f; done ```</em></strong></u><br/>
#### § 리눅스 커널 빌드
  - [Build the Linux® kernel source code for the first time](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Modify,_rebuild_and_reload_the_Linux%C2%AE_kernel#Build_the_Linux-C2-AE_kernel_source_code_for_the_first_time)를 참고하여 커널을 빌드한다.
    - 빌드 과정은 `리눅스 커널 이미지`와 커널이 런타임에 동적으로 로드하는 `커널 모듈` 빌드의 두가지 단계로 크게 구성된다.
    - 모든 과정을 완료하면 vmlinux(elf)와 이를 바탕으로 생성된 uImage(compressed + u-boot wrapper) 외에 device tree (dtbs), artifact(kernel moudles)들이 생성되는데 대략 아래와 같다.
      <img src="https://github.com/marcusjang78/korea-stm32mp1-quest/blob/master/mp1-quest-02/images/build-outputs.png" alt="" width="100%" height="100%" />
#### § 타겟 보드로 커널 재배포
  - [Deploy the Linux® kernel on the board](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Modify,_rebuild_and_reload_the_Linux%C2%AE_kernel#Build_the_Linux-C2-AE_kernel_source_code_for_the_first_time)를 참고하여 빌드된 Kernel, kernel modules, Device Tree등을 타겟 보드로 배포하고 정상 부팅하는지 확인해 본다.
    - 배포는 크게 아래의 3단계로 구성된다.
      - [Push the Linux® kernel into the board](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Modify,_rebuild_and_reload_the_Linux%C2%AE_kernel#Push_the_Linux-C2-AE_kernel_into_the_board): 커널 이미지(uImage) 배포
      - [Push the devicetree into the board](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Modify,_rebuild_and_reload_the_Linux%C2%AE_kernel#Push_the_devicetree_into_the_board): Device Tree Blob (dtb) 배포
      - [Push the kernel modules into the board](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Modify,_rebuild_and_reload_the_Linux%C2%AE_kernel#Push_the_kernel_modules_into_the_board): 커널 모듈 배포
#### § 커널 드라이버 수정하여 반영
  - [Modifying a built-in Linux kernel device driver](https://wiki.st.com/stm32mpu/wiki/Getting_started/STM32MP1_boards/STM32MP157C-DK2/Develop_on_Arm%C2%AE_Cortex%C2%AE-A7/Modify,_rebuild_and_reload_the_Linux%C2%AE_kernel#Modifying_a_built-in_Linux_kernel_device_driver)를 참고하여 built-in 커널 드라이버에 간단한 메세지를 삽입, 빌드하여 타겟 보드에 배포 후 확인한다.
    - 본 예제는 [DRM(Direct Rendering Manager)](https://en.wikipedia.org/wiki/Direct_Rendering_Manager)의 STM32MP1 그래픽 출력 관련 하드웨어(MIPI 및 LTDC) 드라이버 관련 코드의 일부를 수정해 보는 것.
      > <u>Ecosystem에서 그래픽 관련 장치 드라이버는 DRM/KMS 기반으로 제공됨을 의미</u>

<br/><br/>
### STEP.5
#### § 더 많은 주제 (Working in progress)

