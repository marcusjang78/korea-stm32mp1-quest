## 9th QUEST (2020.03.23 ~ 27)
<br/>

## 목 표
##### `MP1 타겟 보드에 STM32MP1 ecosystem 'Distribution Package'에서 Optimization(size & speed)을 하여 부팅 속도개선 및 Image 사이즈를 최적화 해본다.`
<br/>

## 실 습
### STEP.1
+ [Modifying the Linux kernel device tree](https://wiki.st.com/stm32mpu/wiki/How_to_cross-compile_with_the_Distribution_Package#Modifying_the_Linux_kernel_device_tree) 참고하여 DK2 보드의 LED(LD3)를 ON 해 본다.<br/>
  (1) LED GPIO Device tree 수정<br/>
  (2) bitbake virtual/kernel -C compile<br/>
  (3) 최종 이미지 빌드 및 flashing, LED(LD3) ON 확인<br/>
