## 11_30_GPIO

![[Pasted image 20251130160144.png]]

Step1:锁存器（PD2）置高电平

Step2:将相应的GPIO口置低电平

Step3:锁存器（PD2）置低电平

![[Pasted image 20251130161418.png]]

将PCX和PD2置高电平,上电一瞬间，锁存器就是可写入状态，PCX以高电平形式接入LED负端（熄灭状态）

![[Pasted image 20251130162721.png]]

创建一个自己写代码的文件，熟悉几个常用的头文件

![[0ed783d2835af7449fd88715fde12fe9.jpg]]

![[Pasted image 20251130165102.png]]

将PC8口置低电平，成功点亮LED1

![[Pasted image 20251130171337.png]]

按键位PB0，设置为上拉输入模式，没有按下则输入得到高电平，按下时输入得到低电平

根据如图所示的电路图，按键控制的是线路的末端是否接地

![[Pasted image 20251130171918.png]]

PB0,1,2，PA0 分别对应 B1 B2 B3 B4 按键
设置为上拉输入模式

![[Pasted image 20251130190455.png]]

实现按键控制LED

![[Pasted image 20251130193208.png]]
![[Pasted image 20251130193225.png]]

LCD正常显示，注意，初始化函数不应放在while（）中，否则模块将不断处于"重启"状态

![[Pasted image 20251130193805.png]]

LCD与LED1~8共用了引脚PC7~15，引脚冲突

![[Pasted image 20251130200450.png]]

新增按键B2关闭LED1功能

![[Pasted image 20251130200725.png]]
![[Pasted image 20251130200807.png]]

 1. 使用锁存器保存LED的高电平状态
 2. 创建一个temp值，保存LCD的输出状态
 
未完全解决LCD引脚冲突问题

![[Pasted image 20251130212346.png]]

流水灯相关函数，All_off和light_one函数可以确保LED一个一个亮

![[Pasted image 20251130212832.png]]

将按键的状态封装成一个有返回值的函数

![[Pasted image 20251130213310.png]]

流水灯主逻辑

![[Pasted image 20251130213407.png]]

把SysTick(滴答定时器)改为TIM6定时器

不足：流水灯的显示并不流畅，容易发生“跳变”，而且并不从头尾开始，这与计算current_LED的算法有关

## 12_7_PWM

“ARR 的比较结果是触发 Update Event（进而导致 CNT 重装、UIF 置位、可触发中断等全局行为），而 CCR 的比较结果是触发 CCx Event（进而根据模式决定本通道引脚动作、锁存时间戳、可触发中断等局部行为）”


## 12_14_ADC_UART

ADCx->INx 置为Single_Ended（单端模式），完成ADC的初始化

用 **HAL_ADC_GetValue（ADC_HandleTypeDef* hadc）** 获取数值，数字信号通过公式转换成模拟信号

注意使用 **HAL_ADC_Start（ADC_HandleTypeDef* hadc）** 函数使能ADC！

****************
**发：**

ENABLE  UART1，让PA9和PA10作为UART的TX和RX口，设置波特率

**HAL_UART_Transmit (&huart1,( uint8_t * )  text,sizeof(text), 50 );**

注意函数参数的**数据类型**

最后用一个Delay函数让芯片喘口气

**收：**

收的原理是：收到数据之后再重新发送给串口助手

*没在串口上显示*

