# GPIO

## LED TEST
* LED : GPIO Output (PD12~PD15)
* Blue Button : GPIO Input (PA0)
* 버튼이 입력되면 high, 입력이 없다면 low

![image](https://user-images.githubusercontent.com/68395698/122168738-9c352e00-ceb7-11eb-80d9-6b6504147c1b.png)
### GPIO Output
```
HAL_GPIO_WritePin(GPIOx, GPIO_Pin, PinState);
// 어느 포트인지, 어느 핀인지, high or low (set or reset)
HAL_GPIO_WritePin(GPIOD, GPIO_PIN_12, GPIO_PIN_RESET);
// D 12번 pin에 low 신호
```
### GPIO Input
```
if(HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0)==GPIO_PIN_SET){
~
}
```
### Delay
```
HAL_Delay(mx);
HAL_Delayt(1000); //1초
```

### LED
```
int main(void)
{
  /* USER CODE BEGIN 1 */

  /* USER CODE END 1 */

  /* MCU Configuration--------------------------------------------------------*/

  /* Reset of all peripherals, Initializes the Flash interface and the Systick. */
  HAL_Init();

  /* USER CODE BEGIN Init */

  /* USER CODE END Init */

  /* Configure the system clock */
  SystemClock_Config();

  /* USER CODE BEGIN SysInit */

  /* USER CODE END SysInit */

  /* Initialize all configured peripherals */
  MX_GPIO_Init();
  MX_I2C1_Init();
  MX_I2S3_Init();
  MX_SPI1_Init();
  MX_USB_HOST_Init();
  /* USER CODE BEGIN 2 */
 HAL_GPIO_WritePin(GPIOD, GPIO_PIN_12, GPIO_PIN_RESET); //Yellow
 HAL_GPIO_WritePin(GPIOD, GPIO_PIN_13, GPIO_PIN_RESET); //Orange
 HAL_GPIO_WritePin(GPIOD, GPIO_PIN_14, GPIO_PIN_RESET); //Red
 HAL_GPIO_WritePin(GPIOD, GPIO_PIN_15, GPIO_PIN_RESET); //Blue
  /* USER CODE END 2 */

  /* Infinite loop */
  /* USER CODE BEGIN WHILE */
  while (1)
  {
    /* USER CODE END WHILE */
    MX_USB_HOST_Process();

    /* USER CODE BEGIN 3 */
	if(HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0)==GPIO_PIN_SET){
		 HAL_GPIO_WritePin(GPIOD, GPIO_PIN_12, GPIO_PIN_SET); //Yellow
		 HAL_GPIO_WritePin(GPIOD, GPIO_PIN_13, GPIO_PIN_SET); //Orange
		 HAL_GPIO_WritePin(GPIOD, GPIO_PIN_14, GPIO_PIN_SET); //Red
		 HAL_GPIO_WritePin(GPIOD, GPIO_PIN_15, GPIO_PIN_SET); //Blue

	}else{
		HAL_GPIO_WritePin(GPIOD, GPIO_PIN_12, GPIO_PIN_RESET); //Yellow
		HAL_GPIO_WritePin(GPIOD, GPIO_PIN_13, GPIO_PIN_RESET); //Orange
		HAL_GPIO_WritePin(GPIOD, GPIO_PIN_14, GPIO_PIN_RESET); //Red
		HAL_GPIO_WritePin(GPIOD, GPIO_PIN_15, GPIO_PIN_RESET); //Blue
	}
  }
  /* USER CODE END 3 */
}
 ```
 
 ### Result
![KakaoTalk_20210616_120211183](https://user-images.githubusercontent.com/68395698/122151822-2d49dc00-ce9b-11eb-8a46-4f54e403c4f2.gif)

### Circuit
![image](https://user-images.githubusercontent.com/68395698/122168659-86c00400-ceb7-11eb-84a9-83b64785176b.png)
