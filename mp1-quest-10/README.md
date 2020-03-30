## 9th QUEST (2020.03.23 ~ 27)
<br/>

## 목 표
##### `MP1 타겟 보드에 STM32MP1 ecosystem 'Distribution Package'에서 Optimization(size & speed)을 하여 부팅 시간 개선 및 Image 사이즈를 최적화 해본다.`
<br/>

## 실 습
### STEP.1
+ [How to optimize the boot time](https://wiki.st.com/stm32mpu/wiki/How_to_optimize_the_boot_time) 참고하여 실제 부팅 시간을 줄여본다.<br/>
  (1) TF-A Optimization<br/>
  (2) U-Boot Optimization<br/>
  (3) Linux Kernel Optimization<br/>

### STEP.2
+ st-image-core를 빌드하여 이미지 size를 줄여본다.<br/>
  (1) bitbake st-image-core<br/>
  (2) flashing image<br/>
  (3) st-image-weston과 비교하여 달라진 것을 확인한다.<br/>
