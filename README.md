PSoC™ 6S2 GPIO-PDL LED Blink Lab
Lab 102

GPIO-PDL LED Blink Lab
Lab Objective:
The purpose of this lab is to offer students a hands-on understanding of GPIO (General Purpose Input Output) implementation using the PSoC 6 microcontroller from Cypress (CY8CKIT-062S2-43012 Infineon Board). Upon completing this lab, students will be proficient in initializing GPIOs, controlling GPIO states, and developing basic delay functions.

Lab Description:
This lab instructs students to program a PSoC 6 microcontroller to manage an LED through a GPIO, employing the GPIO-PDL (Peripheral Driver Library). The task will demonstrate the core functionality of GPIO output.

The code will:
Initialize the device and necessary board peripherals.

Set up a GPIO pin (connected to the LED) as an output utilizing GPIO-PDL functions.

Establish an endless loop that will:

Drive the pin low

Wait 250 ms

Drive the pin high

Wait 250 ms This sequence will lead to the LED blinking on and off every half-second (250ms on, 250ms off), showcasing an elementary control of GPIO output through GPIO-PDL.

Note: See the PDL API documentation for the GPIO functions to drive the pin high and low.

Note: Use the 
Cy_SysLib_Delay
 function for the delay.

🔥 Requirements
Resources	Links
Computer

💻

ModusToolbox™ software v3.0 or later

Link

CY8CKIT-062S2-43012 Infineon Board

Link

Technical Report

dropbox

🚩 Let start
Create Application
👉 Open Eclipse IDE ModusToolbox


👉 Select Board


image
👉 Select Application


Device Configuration  for initializing LED and UART pin
Open Device Configuration to initialize LED Pin

Find Pin and search for led then select the P1[5]


Set the pins Drive Mode parameter to Strong Drive Input buffer off.


 Initialize debug UART


Coding
Coding: Open the main.c file and add the following code to the main() function.

Copy
for (;;)
  {
        /* Drive the USER LED pin high (LED off) */
      	Cy_GPIO_Set(CYBSP_USER_LED_PORT, CYBSP_USER_LED_NUM);
      
        /* Wait 250 ms */
    	Cy_SysLib_Delay(250U);
    
        /* Drive the USER LED pin low (LED on) */
    	Cy_GPIO_Clr(CYBSP_USER_LED_PORT, CYBSP_USER_LED_NUM);
    
        /* Wait 250 ms */
	Cy_SysLib_Delay(250U);
  }
for (;;) This line starts an infinite loop. The code contained within the curly braces {} will repeat indefinitely.

Cy_GPIO_Set(CYBSP_USER_LED_PORT, CYBSP_USER_LED_NUM);sets the GPIO pin specified by CYBSP_USER_LED_PORT and CYBSP_USER_LED_NUM to a high state, turning off the LED. 

Cy_SysLib_Delay(250U); introduces a delay of 250 milliseconds, causing a pause in the execution of the program. This delay is implemented using a system library function.

Cy_GPIO_Clr(CYBSP_USER_LED_PORT, CYBSP_USER_LED_NUM); clears (sets to a low state) the GPIO pin specified by CYBSP_USER_LED_PORT and CYBSP_USER_LED_NUM, turning On the LED. 

Another Cy_SysLib_Delay(250U); introduces another delay of 250 milliseconds.

This sequence of code turns on the LED, waits for 250 milliseconds, turns off the LED, and then waits for another 250 milliseconds. The cycle then repeats, creating a blinking effect for the LED.

Build the Application
👉 Build the Application


Launching the Application
👉 Launching the Application

Before launching the program to the board, make sure that you have already connected the board to the computer through a USB cable.


Launching Program


👉 Check the Result 


🎉 Congratulations! You can now complete Lab102
Supported toolchains (make variable 'TOOLCHAIN')
GNU Arm® embedded compiler v10.3.1 (GCC_ARM) - Default value of TOOLCHAIN

Arm® compiler v6.16 (ARM)

IAR C/C++ compiler v9.30.1 (IAR)

Supported kits (make variable 'TARGET')
PSoC™ 62S2 Wi-Fi Bluetooth® pioneer kit (CY8CKIT-062S2-43012)

PSoC™ 62S1 Wi-Fi Bluetooth® pioneer kit (CYW9P62S1-43438EVB-01)

PSoC™ 62S1 Wi-Fi Bluetooth® pioneer kit (CYW9P62S1-43012EVB-01)

PSoC™ 62S3 Wi-Fi Bluetooth® prototyping kit (CY8CPROTO-062S3-4343W)

Related resources
Resources	Links
ModusToolbox™ Software Training

link

Other resources
Infineon provides a wealth of data at www.infineon.com to help you select the right device, and quickly and effectively integrate it into your design.

Document history
Document title: BILL_MTB-102 – GPIO-PDL LED Blink Template

Version	Description of change
1.0.0

Lab 102: Learn basic GPIO control with PSoC 6 using GPIO PDL and implement an LED blinker.

Authors:
Assoc. Prof. Wiroon Sriborrirux

Mr. Sriengchhun Chheang

Mr. Sabol Socare