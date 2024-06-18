# ZEDBOARD_setup


## Introduction

This is the tutorial to setup the Zedboard in a linux system using Matlab Simulink and complete the first Blinking Led Example. I have made a detailed step by step tutorial which will help you setup the Zedboard with ease.



![zedboard_looks](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/a4414c36-60f6-47cc-82b0-c588d909b697)



# COURSE CONTENT

</details>
<details>
<summary>STEP 1: Prerequisites </summary>
<br>


Before using this code example, make sure you have the following prerequisites:

- Matlab version:R2022b
- OS:Ubuntu 20.04.3 LTS
- Simulink
- HDL Coder
- Embedded Coder
- HDL Coder Support Package for Xilinx Zynq Platform (currently used version-22.2.0)
- Fixed-Point Designer
- Signal Processing Toolbox
- MATLAB Coder
- Simulink Coder
- Xilinx Vivado 2020.2

![packages req](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/52d3238f-d6bc-4abd-8744-1f2c57bf5433)

Ensure all the MATLAB packages are installed before proceeding with this example. In case you are new to matlab, use the images below as reference to download the packages:


![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/29f7917c-8235-44a6-ac13-5b76c759fa49)

![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/fa873711-845e-4e2c-b649-27fb1810cd35)

![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/ac492b86-ffa7-4675-9672-cd137aeb0751)


Use the search bar in order to download the required packages.


</details>
<details>
<summary>STEP 2: Vivado 2020.2 install for Linux </summary>
<br>
This is a step-by-step tutorial on how to install Xilinx Vivado 2020.2 for the above example

1) Go to https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/vivado-design-tools/archive.html
![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/2fa462a8-2f94-4e24-9026-3b15f29bd265)

click on the 2020.2 version and download the following file

![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/51fd1a65-acb4-4ca3-86df-8818e90e1e2e)

let the download finish [Note: this is a huge download ensure you have the required storage]


2)Once the download has finished, use the following commands in the linux terminal


i) This is to update the dependancies before starting
```bash
    sudo apt update
    sudo apt upgrade 
```

ii) This is to locate where the file has downloaded 
```bash
    cd Downloads/
    ls
```

iii)Locate the file named "Xilinx_Unified_2020.2_1118_1232.tar.gz" [Note: File name can be different but check for the keywords]

```bash
  tar -xvzf Xilinx_Unified_2020.2_1118_1232.tar.gz
```
If you are unable to do this command, find where the download has occured and extract manually

iv)After extraction, do this command

```bash
cd Xilinx_Unified_2020.2_1118_1232/
sudo ./xsetup
```
v)The setup of the rest of Vivado can be followed from this video so kindly do refer it.

https://youtu.be/1uJzjvgTQUk?si=_XHClMbm9bh_5uVM

Refer the video from 7:00 and follow accordingly.

By the end of the video you must have :
- Completed the install and downloads
- Aquired and setup the license
- Added vivado source to the bash
- Should be able to run vivado without any problems
- Only proceed if you have completed this step and are able to run it and if you face issues in setting up vivado,ensure the videos referred download the 2020.2 version and nothing else.



</details>
<details>
<summary>STEP 3: Hardware connections to the board </summary>
<br>
This image is a rough idea of how the connections have to look for a successfull connection.

Where 
    
- 1-->Ethernet port
- 2--> Power Supply
- 3--> USB-UART connection
- 4--> SD card

![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/3808f0fd-be29-4bbb-ac35-dc19a63be8e6)


## Setting Up The IP Configuration To Connect To The Board

1)Go to network settings in your settings option:
  ![ntw1](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/ba5850ae-961f-4d39-9406-9a94b1b7e47d)

2)Using the "+" on the top right create a new profile and add the following details
![ntw2](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/afb9cffe-3958-4c95-b83e-a97dec75a639)
This is done to ensure that we can communicate to the zedboard without any problems
![ntw3](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/1847e40e-d417-40f5-9d77-762c82a75b6f)

3)Confirm if we have connected and are able to communicate to the board 

Go to the terminal and type the following

```bash
ping 192.168.1.101

```
![b4a14735-2def-4497-b896-21b281577e10](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/c2aee97e-cec5-44e0-88bd-a8bf21df6c72)

A successful connection shows the packets being recieved as shown above. Congrats you have successfuully connected the zedboard through ethernet.



</details>
<details>
<summary>STEP 4: Running HDL Coder in Matlab To Establish The Connections </summary>
<br>


## NOTE : Please Do ensure that all the Prerequisites have been installed properly including the support packages in matlab


## Using HDL Coder To Setup The Board


1)Open MATLAB and find the support package "HDL Coder Support Package for Xilinx Zynq Platform (my version-22.2.0)"

- Here you will see a gear icon to the right hand side, Click on that 

![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/37ac01eb-89c2-4ef7-8f3e-efbe162e9bd7)



![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/d32c001a-b0b9-40af-92af-3b98995b4b37)
- We will get a similar prompt and from the drop-down menu choose "Zedboard".





2)Configure Network Card on Host Computer

- We will get this and do not worry if it's not the same as above picture. As we have already established connection to the zedboard manually this step can be procedded by entering "next". 

- Do note that this might show a warning but it can be ignored and we can move to the next step.

![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/6738143e-a563-4b55-84d7-f7dc15386bee)








3)Selecting the drive

- Insert the SD card from the zedboard into an SD-Card reader and select refresh.
- You will be able to see the card appear in the drop-down and then write the firmware onto the card. Proceed if it asks or provides a warning message of data being overwritten.

![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/d9d8392b-9efb-4ce7-8cf7-a960d6ef150b)



![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/436c9980-e4eb-4c0b-a6e4-23a7d3839376)


- After this step finishes, we can remove the card from the SD-Card reader and insert it back into the zedboard.




4)Verification/checking the connections


-After we insert the SD-Card back into the board, we can move to the final step. We will get a prompt to "Test Connection". Click on it and wait till we get the "Test successful" Message


![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/85c5355f-d719-49d1-9cf6-20a44c4c6827)

Check if the highlighted message is shown and we get the green tick for "test connection"


Congradulation You have completed the setup for HDL Coder.




</details>
<details>
<summary>STEP 5: Checking the Zedboard connection from Matlab </summary>
<br>

## These Are The Steps To Be Followed To Establish Connection To The Zedboard From MATLAB


## 1) Find the toolpath where you have downloaded Xilinx vivado 2020.2 (this basically means which folder/directory the tool is downloaded in). If you are new to linux do watch a video on how to locate the path of a file.

```bash
cd /tools/Xilinx/Vivado/2020.2/bin/vivado
```

For example if i follow the above command i can locate my vivado installation. It might not be the same for you so pay attention where the tool is downloaded.

Now go to MATLAB and type this command 
![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/45d9701b-0246-494e-9e78-8baf74ae25dd)

This is to setup the toolpath.

## 2) After you get the successful output from the previous step, Type these two commands

![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/1aa4f60b-f240-4111-9990-a5c52680406a)


You might get these Warnings but these are normal and due to the new version of matlab not supporting these commands. You can ignore them without any issues

## 3) Setup the compiler  

Use this command to setup the compiler (it is done by default unless there is no compiler present)
![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/cf47fd14-df0f-49b6-9ddd-07b0b3ed72ea)



This is the end of checking connections to the zedboard and if all the steps are being followed then this should have no problem and if successful till ths step we can proceed to the next example step. 



</details>
<details>
<summary>STEP 6: HDL Blinking Example Using HDL Coder </summary>
<br>


## 1) Type the following into matlab

![image](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/800c7afc-369f-49b6-b473-835b5a99a2f8)


This will open this Window 

![hdl5](https://github.com/rohithgopakumar/ZEDBOARD_Hardware_Setup_Linux_Matlab/assets/131611312/4f68612d-d152-4daf-ae51-75e5c9d848c9)


Click okay if any warnings pop up as they can be ignored.
