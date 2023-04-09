# Industry 4.0@AIC: Animation Dashboard on Node-Red 
Moritoring System Project using PLC(Mitsubishi FX5U-32MR/ES), Modbus Protocol and SVG (Scalable Vector Graphics) to create a real-time Animation Dashboard on Node-RED for Process Monitoring in Industry 4.0 


![7B6690B1-C246-4D05-B531-0963463A7620](https://user-images.githubusercontent.com/81687385/230735958-67c18a5b-b558-4601-888c-ad535a7204b3.jpg)
by 62050216 Poomipat, A student in Embedded System Engineering at Burapha University.

*****This repository is intended for individuals who are interested in studying and further development projects related the Industry 4.0@AIC Center*****

# Component
### Hardware Component:
 * PLC fx5u-32mr/es
 * Demonstration Kit of an automated sorting system using PLC and Dobot Arm. 

### Software Component:
 * Node-Red
   Request Plugin
     * node-red-dashboard (ver 3.2.0 or latest version)
     * node-red-contrib-modbus(v5.23.1 or latest version)
     * node-red-contrib-ui-svg (v2.3.1 or latest version)
     * node-red-contrib-drawsvg (v1.3.0 or latest version)
 * GX Work3 (v1.076E or lastest version)
 * M1 Studio
 * inkscape
 
**** The PC in the robot room at AIC already has the necessary components for use. ****


# Intro for Demonstration Kit:
<h3 align="center">
   Components of the demonstration kit
</h3>
<p align="center">
  <img width="654" height="400" src="https://user-images.githubusercontent.com/81687385/230772294-ab6d88d9-659f-4887-b0fe-5f68f8c81a20.jpg">
</p>

<h3 align="center">
   PLC I/O table
</h3>


<div align="center">
   
   |   Input  |  Variables            | Output |  Variables  |
   | :--------:|:-------------:        | :------:|:------------:|
   |    X0    | S1 (Push button switch) |   Y0   | L1 (Green lamp) |
   |    X1    | S2 (Push button switch) |   Y1   | L2 (Red lamp)   |
   |    X2    | Reed1 (Reed switch)     |   Y2   | Sol(solenoid value) |
   |    X3    | Reed2 (Reed switch)     |   Y4   |STR (Conveyor)       |
   |    X4    | Ind (sensor)            |   Y5   | M1-Input1 (IN05 M1)|
   |    X5    | Cap (sensor)            |   Y6   | M1-Input2 (IN06 M1)|
   |    X6    | Opt (sensor)            |   Y7   | M1-Input3 (IN07 M1)|
   |    X7    | M1-Output (dobot)       |        |             |
   |    X10   | Fiber (sensor)          |        |             |

</div>
<h3 align="center">
   Dobot m1 I/O table
</h3>

<div align="center">
   
   |   Input  |  Variables      | Output |  Variables  |
   | :--------:|:-------------: | :------:|:------------:|
   |    IN01    | S1 (Push button switch) |  out01  | Dobot End Status(X7) |
   |    IN02    | S2 (Push button switch) |  out17  |  Gripper   |
   |    IN03    | S2 (Push button switch) |  out18  | Air Pump |
   |    IN05    | M1-Input1 (Y5)          |         |       |
   |    IN06    | M1-Input2 (Y6)          |         |       |
   |    IN07    | M1-Input3 (Y7)          |         |       |

</div>

# Getting Started
   ### Step 1) System Environment Set-UP
   * #### 1.1) System Power:ON
      <p align="center">
            <img width="800" height="400" src="https://user-images.githubusercontent.com/81687385/230781653-1ef186c0-ecd6-4d6a-b72e-cdcbe9a867f7.jpg">
      </p>
   * #### 1.2) pneumatic System:ON
      <p align="center">
            <img width="700" height="500" src="https://user-images.githubusercontent.com/81687385/230782876-db094cbb-7268-45d8-8546-2a8bd82ba052.jpg">
      </p>
   * #### 1.3) Dobot Power ON; Behind the Dobot Arm you will see The power button.
      <p align="center">
            <img width="700" height="500" src="https://user-images.githubusercontent.com/81687385/230785562-a83d2635-3abf-4474-a193-a533d0911092.jpg">
      </p>
      
   ### Step 2) Upload the Program Ladder code to PLC
   * #### 2.1) Connect PLC to PC(In robot room) or Your laptop with LAN Cable;
       
      ![messageImage_1681060398518](https://user-images.githubusercontent.com/81687385/230790304-6510c2de-0872-40e8-9584-c01b76f98b4f.jpg)
       
   * #### 2.2) Open The Program Ladder code "PLC_Animation",location on  Documents--> Industry4.0_Animation --> PLC Progam --> Open "PLC_Animation.GX3"; if you try on your laptop you can download file in my repository.
      <p align="center"> 
             ***** Note: The program  is already in PLC but you can try to upload by your self *****
      </p>
      
     ![wwww](https://user-images.githubusercontent.com/81687385/230794784-43e87f07-5d62-490a-9349-788f4701162c.jpg)

   * #### 2.3) Configure the Ethernet IPV4 settings of the PC to connect to the same network as the PLC(192.168.137.250); Go to Control Panel --> Network and Sharing Center --> Select "Change adpter Setting"
      <p align="center">
            <img width="736" height="266" src="https://user-images.githubusercontent.com/81687385/230788826-ca28d829-0e1a-4568-b51a-929cda49ab2a.jpg">
      </p>
   Right Cilck on Ethernet --> Select"(TCP/IPV4)" --> And set your IPV4 in "192.168.137.xxx"; And ensure that it is not the same as the PLC address(250)
   <p align="center">
            <img width="774" height="437" src="https://user-images.githubusercontent.com/81687385/230789299-783acee9-fa7d-4633-af89-2e98ff000ec9.jpg">
   </p>  
Verify that the PC can communicate with the PLC, Go back the GX work3 and Go to Manubar --> Online --> Select "Current Connection" --> And select yor Ethernet adpter --> Click "Communicatin Test"

![messageImage_1681064846307](https://user-images.githubusercontent.com/81687385/230790245-fbbeb2ad-fb87-43ab-b1d2-3d56e594b90d.jpg)

   * #### 2.4) Upload ladder code to PLC, Go to menu bar --> Online --> Write to PLC --> Select Parameter + Program(F)--> Excute 

![messageImage_1681065543636](https://user-images.githubusercontent.com/81687385/230790693-b108e00a-08ae-4d09-a644-688debbd5836.jpg)
* #### 2.5) After uploading; Reset PLC

![messageImage_1681066604911](https://user-images.githubusercontent.com/81687385/230791408-5b9cf542-b60c-43fc-88ff-d4c05b24f701.jpg)
   
### Step 3) Upload the Dobot Program to Dobot m1
  
  * #### 3.1) Open Program "M1 Studio" and Connect Dobot Arm to PC with USB form Dobot
  
![messageImage_1681070387325](https://user-images.githubusercontent.com/81687385/230793978-5c1ead64-0b13-4db8-b71b-f8e08231d5fb.jpg)

  * #### 3.2) Testing Dobot m1 program go to Documents--> Industry4.0_Animation --> Dobot m1

![messageImage_1681075219348](https://user-images.githubusercontent.com/81687385/230797062-1e45a8bf-8d82-42ac-a2ac-9c9ac4fd786c.jpg)

   <p align="center">
            <img width="678" height="400" src="https://user-images.githubusercontent.com/81687385/230797257-0a2fbb48-9c07-4119-b185-d4f695307648.jpg">
   </p>  
   

![messageImage_1681075914953](https://user-images.githubusercontent.com/81687385/230797440-2c0f4734-16ca-48fc-a7eb-667f544369e0.jpg)

Testing Dobot working "Push button S1(IN01)"
   <p align="center">
           <img width="422" height="523" src="https://user-images.githubusercontent.com/81687385/230797573-40932d8d-615f-485a-84bf-7ce56068fc5a.jpg">
   </p>
   ![messageImage_1681076395543](https://user-images.githubusercontent.com/81687385/230797725-52ef9361-4d20-4ab2-923c-c9b6539ab089.jpg)

  
   * #### 3.2) Upload Program main to Dobot m1





