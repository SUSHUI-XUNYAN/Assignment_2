# 电控组第二次培训作业

**姓名：王清攝**

***学号：20263004511***

**避免阻塞思路：**

通过HAL_GetTick()函数获取单片机启动的时间，然后声明变量clock读取每一次循环的HAL_GetTick()值，

再声明变量N = HAL_GetTick() - clock表达每一轮的相对时间，最后以if 、else来判断该时刻N应该是哪个LED亮起。

**核心代码片段：**

==uint32_t clock = HAL_GetTick();==  

/* USER CODE END 2 */  

/* Infinite loop */  
/* USER CODE BEGIN WHILE */  
wh==ile (1)  
{  
  uint32_t N =HAL_GetTick() - clock;  
  if (N <= 500)  
  {  
    HAL_GPIO_WritePin(LED0_GPIO_Port, LED0_Pin, GPIO_PIN_SET);  
    HAL_GPIO_WritePin(LED1_GPIO_Port, LED1_Pin, GPIO_PIN_RESET);  
    HAL_GPIO_WritePin(LED2_GPIO_Port, LED2_Pin, GPIO_PIN_RESET);  
  }  
  else if (N <= 1000)  
  {  
    HAL_GPIO_WritePin(LED0_GPIO_Port, LED0_Pin, GPIO_PIN_RESET);  
    HAL_GPIO_WritePin(LED1_GPIO_Port, LED1_Pin, GPIO_PIN_SET);  
    HAL_GPIO_WritePin(LED2_GPIO_Port, LED2_Pin, GPIO_PIN_RESET);  
  }  
  else if (N <= 1500)  
  {  
    HAL_GPIO_WritePin(LED0_GPIO_Port, LED0_Pin, GPIO_PIN_RESET);  
    HAL_GPIO_WritePin(LED1_GPIO_Port, LED1_Pin, GPIO_PIN_RESET);  
    HAL_GPIO_WritePin(LED2_GPIO_Port, LED2_Pin, GPIO_PIN_SET);  
  }  
  else  
  {  
    clock = HAL_GetTick();  
  }==






