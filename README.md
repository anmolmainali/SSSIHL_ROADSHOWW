# SSSIHL_Roadshow
This repository documents my experience in RISC-V and VLSI Chip Design Roadshow   &amp; Upskilling Workshop at SSSIHL

# Workshop Overview
In this one-day workshop, my fellow Physics enthusiast and I were introduced to VLSI and RISC-V and got to understand the process of making a chip. This workshop also helped us understand various kinds of chips and microprocessors. This workshop was very useful as it helped us delve more into the field of VLSI and chip designing, giving us more career options in the future.

# Process 
We first installed all the software as shown below

![Screenshot 2024-12-14 094402](https://github.com/user-attachments/assets/bf5f1750-9096-48b0-a24a-40817bcfc72d)
# ABOUT THE SOFTWARE
* Slack is a platform on which we received our codes. On it, we could share our personal progress with other designers and interact with them.

* Oracle virtual box helped us use an external OS where we designed our code(The OS used was  Ubuntu 18.04 LTS(Bionic Beaver).

* vsd squadron was exported to the virtual box where we used to open the OS.

# The follow-up steps

Now after setting up our necessary tools, we processed to open the Virtual Box and we were encountered with a preface of this kind.


![image](https://github.com/user-attachments/assets/56956e88-a59f-499d-b691-d3532b334678)




* After opening Virtual Box we opened a new terminal where we wrote our new commands to install gedit.

* We use the command ### Example Commands to clone a Git repository and install gedit:

  ` sudo apt install gedit`

  * The password provided by the host was used to install gedit.
 
    ![image](https://github.com/user-attachments/assets/3f5d0740-4f8c-4e76-807c-9b0ef220f67c)



* The new white interface was used to write our code and to save it.

  ### Code ###
```
  #include<stdio.h>
int main(){
    int sum = 0, i, n;
    printf("Enter the value of n = ");
    scanf("%d",&n);
    for(i = 1;i <= n;i++){
       sum = sum + i;
    }
    printf("The Sum of numbers from 1 to %d is %d\n",n,sum);
    return 0;
}
```
![image](https://github.com/user-attachments/assets/72a62bdb-9bfc-44b1-bd3c-b4c0777f1c71)


This was a simple code which adds the number from 1 to n where 'n' is the number provided by us.

* After saving the file we opened the previous terminal where we executed the code.

* we used two commands here

 1.  ` gcc {file name}.c`
  
  2. `./a.out`

  * After running the code we provided the number and it gave the sum of 1 to n.

   ![image (3)](https://github.com/user-attachments/assets/55dd227b-3d1e-4604-8968-a1c7f97fcddd)


## Then as we were using RISC-V architecture we also used the following command to do so :##
  
    `riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o {filename}.o {filename}.c`
* Then we disassembled the file for the RISC-V architecture using the following command :
  
    ```
  iscv64-unknown-elf-objdump -d {filename}.o
    ```
  After we ran the code we got the output as:

  ![image (4)](https://github.com/user-attachments/assets/8751e4d1-1567-448f-90d6-1d6e39e8ac14)




  ## We then changed the directory of the openlane. ##

  ```
  cd Desktop/work/tools/openlane_working_dir/openlane
  ```


![image (5)](https://github.com/user-attachments/assets/7d0e8c5e-fae8-4cbf-bdc8-70ed8affdb7a)




* Then we specify the version to 0.9 by the following command
    ```
    package require openlane 0.9
    ```
* Then we prepare the design workspace for a specific project which in our case is picorv32a using the following command.
     ```
     prep -design picorv32a
     ```

We then got

![image (8)](https://github.com/user-attachments/assets/f7e7735a-7749-4876-ad40-5240702abce7)



* Then we triggered the synthesis stage of the digital IC design flow by using the following command:-
  ```
   run_synthesis
  ```

  Then we got:

 
  
![image (2)](https://github.com/user-attachments/assets/b9282a2c-2ac0-4f67-bf1f-681c45baee95)


* Then we executed the floorplanning state of the IC design flow .It was a crucial step in translating the synthesized gate-level netlist into a physical design by defining the chip's layout structure and preparing it for placement and routing. This was done by executing the following command.

  ```
      run_floorplan
  ```

  
![Screenshot 2024-12-13 123744](https://github.com/user-attachments/assets/1ee2bf44-60c3-4b9b-bc8c-ccde32e63684)


* Then we opened a new terminal and typed the following command to display the floorplan image(some changes in command is required) :

  ```
   eog designs/picorv32a/runs/{press tab as it varies from device to device}/results/floorplan/picorv32a.floorplan.def.png
  ```

  Then a png file was opened
  

![image (9)](https://github.com/user-attachments/assets/fd53c7ef-8bae-4e73-9430-411223e8f742)



* For the placement stage of the digital ASIC design flow we used the following command
  ```
  run_placement
  ```
![image (11)](https://github.com/user-attachments/assets/9a072606-847f-4dad-be1a-def8bc480c06)


* Then we open a new terminal and typed the following command to display the placement image(some changes in command is required)
  
```
eog designs/picorv32a/runs/{press tab as it varies from device to device}/results/placement/picorv32a.placement.def.png
```

![image (10)](https://github.com/user-attachments/assets/01805d32-ee30-4755-9d48-31ad9183b9d0)





* Then we ran the command n the OpenLane flow stands for Clock Tree Synthesis (CTS), and its purpose was to create a clock distribution network for our design.
    ```
      run_cts
    ```


    ![Screenshot 2024-12-13 141933](https://github.com/user-attachments/assets/b71adc0e-cf6d-4436-83ab-c18b580add44)


* Once CTS was completed, the next step was routing. This was where the tool connected all the cells using metal layers, creating the physical interconnections that make up the logic and clock paths of the design.We did this by running the following code:
 ```
run_route
```

                  
![Screenshot 2024-12-13 143036](https://github.com/user-attachments/assets/72883670-6852-4e64-b703-dd68262e6c4f)

### This was the final step in designing a chip which was now ready for production ###

# Working a code on the VSD squadron #

After all the designing part we finally got the boards, now it was time to run a code on this board.

* We opened VS code where we used the Platform IO extension to run the code which was given to us on Slack.
* We then connected the board to to our laptop
* Then a little bit of changes were made to the code
* We changed 1NVIC_PriorityGroup_2` to `NVIC_PriorityGroup_1`

  
![Screenshot 2024-12-14 133311](https://github.com/user-attachments/assets/8fe7f659-aa81-4350-bc70-71c448a19f47)


  
* Then the `Delay_Ms()` was changed from 1000 to 100 so that the LED blinks faster


![Screenshot 2024-12-14 133435](https://github.com/user-attachments/assets/b42f1fee-d2ea-4a27-8e23-63cf9c3af7ed)

# This was what was noticed on the board




https://github.com/user-attachments/assets/bf2ec9dd-2f0b-48b4-bc0c-b83540750823




# The code we used 

```
#include <ch32v00x.h>
#include <debug.h>

#define BLINKY_GPIO_PORT GPIOD
#define BLINKY_GPIO_PIN GPIO_Pin_6
#define BLINKY_CLOCK_ENABLE RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE)

void NMI_Handler(void) __attribute__((interrupt("WCH-Interrupt-fast")));
void HardFault_Handler(void) __attribute__((interrupt("WCH-Interrupt-fast")));
void Delay_Init(void);
void Delay_Ms(uint32_t n);

int main(void)
{
	NVIC_PriorityGroupConfig(NVIC_PriorityGroup_1);
	SystemCoreClockUpdate();
	Delay_Init();

	GPIO_InitTypeDef GPIO_InitStructure = {0};

	BLINKY_CLOCK_ENABLE;
	GPIO_InitStructure.GPIO_Pin = BLINKY_GPIO_PIN;
	GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
	GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
	GPIO_Init(BLINKY_GPIO_PORT, &GPIO_InitStructure);

	uint8_t ledState = 0;
	while (1)
	{
		GPIO_WriteBit(BLINKY_GPIO_PORT, BLINKY_GPIO_PIN, ledState);
		ledState ^= 1; // invert for the next run
		Delay_Ms(100);
	}
}

void NMI_Handler(void) {}
void HardFault_Handler(void)
{
	while (1)
	{
	}
}
```


# We then used another code on the same platform to now cause the LED to fade slowly fade out

# Code

```
#include "debug.h"
#define TIME_PERIOD 1000
#define PRESC       0
#define PULSE       632
#define STEP_SIZE   10
volatile u16 val;
volatile u8 dir;
void TIM1_PWMOut_Init(void){
    GPIO_InitTypeDef GPIO_InitStructure={0};
    TIM_OCInitTypeDef TIM_OCInitStructure={0};
    TIM_TimeBaseInitTypeDef TIM_TimeBaseInitStructure={0};
    //RCC_APB2PeriphClockCmd( RCC_APB2Periph_GPIOC | RCC_APB2Periph_TIM1, ENABLE );
    RCC_APB2PeriphClockCmd( RCC_APB2Periph_GPIOD | RCC_APB2Periph_AFIO, ENABLE );
    RCC_APB1PeriphClockCmd( RCC_APB1Periph_TIM2, ENABLE );
    GPIO_PinRemapConfig(GPIO_FullRemap_TIM2, ENABLE);
    GPIO_InitStructure.GPIO_Pin = GPIO_Pin_6;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_AF_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init( GPIOD, &GPIO_InitStructure);
    TIM_TimeBaseInitStructure.TIM_Period = TIME_PERIOD;
    TIM_TimeBaseInitStructure.TIM_Prescaler = PRESC;
    TIM_TimeBaseInitStructure.TIM_ClockDivision = TIM_CKD_DIV1;
    TIM_TimeBaseInitStructure.TIM_CounterMode = TIM_CounterMode_Up;
    TIM_TimeBaseInit( TIM2, &TIM_TimeBaseInitStructure);
    TIM_OCInitStructure.TIM_OCMode = TIM_OCMode_PWM2;
    TIM_OCInitStructure.TIM_OutputState = TIM_OutputState_Enable;
    TIM_OCInitStructure.TIM_Pulse = PULSE;
    TIM_OCInitStructure.TIM_OCPolarity = TIM_OCPolarity_High;
    TIM_OC3Init( TIM2, &TIM_OCInitStructure );
    TIM_CtrlPWMOutputs(TIM2, ENABLE );
    //TIM_OC3PreloadConfig( TIM1, TIM_OCPreload_Disable );
    //TIM_ARRPreloadConfig( TIM1, ENABLE );
    TIM_Cmd( TIM2, ENABLE );
}
int main(void)
{
    NVIC_PriorityGroupConfig(NVIC_PriorityGroup_1);
    SystemCoreClockUpdate();
    Delay_Init();
    TIM1_PWMOut_Init();
    val = 0;
    dir = 0;
    // Loop
    while(1){
        val += (dir) ? -STEP_SIZE : STEP_SIZE;
        TIM_SetCompare3(TIM2, val);
        dir ^= (val == 1000 || val == 0) ? 1 : 0;
        Delay_Ms(15);
    }
}

```

# The was what we observed with the new code






https://github.com/user-attachments/assets/d85d5e89-225f-4729-8e53-e3cd237a3eea







### This was about the workshop that we as a department attended. It was really helpful for us and we got a lot of insights about VSLI and chip designing. ###
### I  would like to thank Mr. Kunal Gosh and his team for teaching and providing us with the equipment required for this workshop. I would also like to thank our Institute and our department for providing us with this opportunity. ###
