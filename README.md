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
   I/O table
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

# Getting Started
   ### Step 1) System Environment Set-UP
   * #### 1.1) System Power:ON
      <p align="center">
            <img width="800" height="400" src="https://user-images.githubusercontent.com/81687385/230781653-1ef186c0-ecd6-4d6a-b72e-cdcbe9a867f7.jpg">
      </p>
   * #### 1.2) pneumatic system:ON
      <p align="center">
            <img width="700" height="500" src="https://user-images.githubusercontent.com/81687385/230782876-db094cbb-7268-45d8-8546-2a8bd82ba052.jpg">
      </p>
   * #### 1.3) Dobot Power ON; Behind the Dobot Arm you will The power button.
      <p align="center">
            <img width="700" height="500" src="https://user-images.githubusercontent.com/81687385/230785562-a83d2635-3abf-4474-a193-a533d0911092.jpg">
      </p>
      
   ### Step 2) Upload the Program to PLC and Dobot m1
   * #### 2.1) Connect PLC to PC/Your laptop with LAN Cable;
       <p align="center">
            <img width="1070" height="472" src="https://user-images.githubusercontent.com/81687385/230786694-35fa983e-77a4-4ea4-811d-b01759280f8c.jpg">
       </p>
   * #### 2.2) Upload The program Ladder code "PLC_Animation" location on Documents--> Industry4.0_Animation --> PLC Progam --> "PLC_Animation.GX3"
      <p align="center">
            <img width="960" height="396" src="https://user-images.githubusercontent.com/81687385/230787847-3328a072-a51c-4521-8ff9-ca363deb547c.jpg">
      </p>
*****This repository is intended for individuals who are interested in studying and further development projects related the Industry 4.0@AIC Center*****





















