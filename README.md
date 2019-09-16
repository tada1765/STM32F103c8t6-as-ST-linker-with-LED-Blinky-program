# STM32F103c8t6-as-ST-linker-with-LED-Blinky-program

Objective:
----------------
- To program STM32F103c8t6 MCU with ST-Link connection.
- To setup circuit connection and select suitable STM IDE for simple LED Blinky program.

Software & Hardware:
-----------------------------
- Software :
 - Flash Loader Demonstrator, [download here](https://www.st.com/en/development-tools/flasher-stm32.html)
 - ST-LINK Utility, [download here](https://www.st.com/en/development-tools/stsw-link004.html)
 - STM32CubeIDE, [download here](https://blog.st.com/stm32cubeide-free-ide/)
- Hardware :
 - any FTDI or USB to TTL devices, [references](https://shopee.com.my/FT232RL-FTDI-USB-adapter-to-TTL-Converter-Module-5V-3.3V-For-Arduino-Blue-TE321-i.119159849.1942296920)
 - STM32F103c8t6 blue-pill or black pill, [references](https://shopee.com.my/product/119159849/1952461096)
 -  Or stm32f103 smart v2.0, [references](https://shopee.com.my/STM32F103C8T6-ARM-STM32-Minimum-System-Development-Board-STM32-Core-Board-i.119159849.1948146478)

Circuit Diagram:
----------------------
- USB-TTL Connection:
![USB-TTL](https://trello-attachments.s3.amazonaws.com/5cfb2a7f4ca2765857569561/5cfb8538a516a963889e6b74/c3f390c7bc40071c61d83519f47004eb/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

- ST-Link Connection:
![ST-Link](https://trello-attachments.s3.amazonaws.com/5cfb8538a516a963889e6b74/730x410/8fe23f1b2b72a9cc1bda804c848c4e59/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

Procedure:
------------
This procedure is to make your own ST-LINK V2 from STM32 Blue-Pill or STM32 Black-Pill. 

Why making this device?

 Because to Program STM32 ARM micro controller is required a ST linker device, however some of the low-cost Cortex-M3 MCU, STM32F103C8T6 (Blue Pill) from China, ~RM7/piece does not come with programmer, so the cheapest way is to buy two pieces, and program the first one to function as a programmer.

 OR you can buy a ST-Link V2 for example [picture here](https://shopee.com.my/ST-Link-V2-Mini-STM8-STM8STM32-Simulator-Download-Color-Random-i.133282937.2424131306), so that you can skip this entire ST-LINK V2 making procedure.

1. download all the necessary software and prepare the hardware that mention above which require at least two STM32F103c8t6 and one FTDI or usb to ttl device.

2. Connect follow circuit diagram and set jumper BOOT0 to 1 then connect USB cable to FTDI and your PC. 
![USB-TTL](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/e4c92258c73028613f4fdb939cb2021f/image.png)
*NOTE: Use 3.3V voltage, do not apply 5V voltage.

3. Open and run Flash Loader Demo and configure as diagram below:
![FLD1](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/94534fe058ac37553d53f89affefafcb/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

4. Click remove protection if your MCU have program before.
 ![FLD2](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/779879d273bfcfaded2105864df26f5c/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

5. Just clink Next.
![FLD3](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/bdfa413d607d0d06292579675175643b/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

6. clink green mark then select the Hex file, download the Hex file here, [click here](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/c8cf474669aaf68266874c717dab1d2a/hex.hex).
![FLD4](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/bf4823053fe3ee68e2a48796d55c4ee7/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

7. And then click Next and the Loader will start to download program the micro controller:
![FLD5](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/9fc47373b4ddb3bf199d7247bd34dc1e/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

8. And then it will also start to verify it:
![FLD6](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/7ba9fa2ee97b27d2b3b917665fb8b94a/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

9. when is done close it:
![FLD7](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/151e9d83321c51f55c3165c4a4c2578d/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

10. Now we disconnect everything and connect our board to computer with micro USB cable and also move the BOOT0 jumper back to 0. Now we start ST-LINK Utility, select ST-LINK -> Firmware update:
![FLD8](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/3b5b3893c6b14fc86bceee3e29be8929/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

11. New window opens and here we click on Device Connect and it will connect to our new ST-LINK:
![FLD9](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/d5bfba5c252155d40b10334b3ed71870/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

12. click on Yes and it will start to upgrade:
![FLD10](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/7009f196683b80e7aae1fff13df39bf6/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

13. When it’s done it will let us know:
![FLD11](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/1a51af92d15fbfcf62cc8afafbc2a9ce/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

14. Now all we need to do is test it. I am testing it according to diagram below with another Blue Pill (don’t miss that short connection between PB12 and PB14!!!):
![cir1](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d7f01c7cb26a91ef2c681dd/68c1ce389b35a5ce95d869dfbb74bcdb/image.png)
diagram came form http://slemi.info/2018/08/14/making-your-own-st-link-v2/

OR 
![cir2](https://trello-attachments.s3.amazonaws.com/5cfb8a844ca27658575ca5ea/1033x489/c2aea311fc181d6d204bea7987f02bad/stm32_to_stm32v2.png)


1.1 : NOW STAR PROGRAM STM32F103c8t6 (LED Blinky)
--------------------------------------------------------------
Objective: use of STM32CubeIDE to set GPIO PINC13 as GPIO output, then use _HAL function for LED to blink.

1.2 Testes Function:
------------------
- HAL_WritePin();
- HAL_GPIO_TogglePin();

1.3 Configuration
---------------------
- CubeMx pin config:
![mx](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d0af556149fa852bd0886fb/2fe0f9c455c862bf4137b9fb37b904c7/image.png)

- GPIO config:
![gpio](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5d0af556149fa852bd0886fb/cc852dd70684be5b27bcf0dbe223587a/image.png)

1.4 coding:
-------------
at line 102 add the program inside USER CODE BEGIN 3 until USER CODE END 3.

```
 /* USER CODE BEGIN WHILE */
  while (1)
  {
    /* USER CODE END WHILE */

    /* USER CODE BEGIN 3 */
	  HAL_GPIO_WritePin(LD2_GPIO_Port, LD2_Pin, GPIO_PIN_SET);
	  HAL_Delay(500);
	  HAL_GPIO_WritePin(LD2_GPIO_Port, LD2_Pin, GPIO_PIN_RESET);
	  HAL_Delay(500);
	  HAL_GPIO_TogglePin(GPIOC, GPIO_PIN_13);
	  HAL_GPIO_TogglePin(GPIOA, GPIO_PIN_2);
	  HAL_Delay(100);	//delay 500ms
  }
  /* USER CODE END 3 */
```

1.5 circuit connection:
-------------------------
- connect GPIO pin that set early which is PA2 or PA3 or PA5 to LED with 220 ohm resistor and the other side of the resistor go to ground.

1.6 Summary:
---------------
- To program a STM32 ARM MCU need a ST linker, In this tutorial a ST link device has being make with another stm32f103c8t6 to program a stm32f103c8t6.
- Both HAL function "HAL_WritePin()" and "HAL_GPIO_TogglePin()" is able to set GPIO high and low.
- NOTE: In this case GPIO is set as push pull , and not open drain. 


References:
--------------
1. from Semi, [link: http://slemi.info/2018/08/14/making-your-own-st-link-v2/]
2. Other useful reference from Milan Karakas, [video: https://www.youtube.com/watch?v=Sa48sPObmJ0]

Reference Manual:
--------------------
- To download a PDF version, [click here](https://www.st.com/content/ccc/resource/technical/document/reference_manual/59/b9/ba/7f/11/af/43/d5/CD00171190.pdf/files/CD00171190.pdf/jcr:content/translations/en.CD00171190.pdf).

- To download the stm32f1 hal reference manual, [click here](https://bit.ly/2PHIAH5)

PIN and GPIO:
----------------
2. STM32f103c8t6 v2: ![gpio diagram1](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5cf4a21627f4f931c585e8fd/d14a5eace200fc72b90fe5845f53c1cc/image.png)
![gpio diagram2](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5cf4a21627f4f931c585e8fd/3770dd892a9bb4a3c7d90edb82de6fb3/image.png)
2. STM32f103c8t6: ![gpio diagram](https://trello-attachments.s3.amazonaws.com/5cee4774d8fcdd32c2d51358/5cf4a21627f4f931c585e8fd/68ff78b49de364ca3c22cc8120dff629/image.png)
