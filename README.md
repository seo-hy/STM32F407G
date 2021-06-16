# STM32F4
`STM32F4 STUDY`
- MCU : STM32F407VG
- Board : STM32F407G-DISC1

## Install
- [JAVA](https://www.java.com/ko/download/)
- [CubeMX](https://www.st.com/en/development-tools/stm32cubemx.html)
- [TrueStudio](https://www.st.com/content/st_com/en/products/development-tools/software-development-tools/stm32-software-development-tools/stm32-ides/truestudio.html)

## Project
### Basic setting
* Board Selector -> STM32F407G
* Project Manager > Project > Toolchain / IDE : `TrueSTUDIO`
* Project Manager > Code Generator > Generated files : <b>Check</b> Generate peripheral initialization as a pair of '.c/.h' files per peripheral
* Generate : `GENERATE CODE`
* Or open .ioc file
* Open : `.cproject`
* main code : Core/Src/main.c
* Write the code according to the comments
  ```
  /* USER CODE BEGIN */
     ~~~
  /* USER CODE END */
  ```
 * Autocomplete : ctrl + space
  
  [+ Detail](https://github.com/seoh02h/STM32F4/tree/master/stm32f4-setting)

## Contents
1. [GPIO](https://github.com/seoh02h/STM32F4/tree/master/GPIO)
2. 

## Pinout
![image](https://user-images.githubusercontent.com/68395698/122174109-698e3400-cebd-11eb-8eab-c5bd9c4e5a9c.png)

