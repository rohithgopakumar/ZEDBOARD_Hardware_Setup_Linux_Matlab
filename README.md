# ZEDBOARD_Hardware_setup


## Introduction

This is the tutorial to setup the Zedboard in a linux system using Matlab Simulink and complete the first Blinking Led Example. I have made a detailed step by step tutorial which will help you setup the Zedboard with eaze.






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
