# LINEAR INTEGRATED CIRCUITS
## EXPERIMENT 1 - ANALYSIS OF CS AMPLIFIER
### QUESTION:
To analyse the CS Amplifier circuit and conduct DC Analysis, Transient Analysis and AC Analysis and extract the following parameters:  DC Operating Point, Gain, Bandwidth, Power.

### 1. INTRODUCTION
An amplifier circuit is a widely used design for amplifying small signal applications. CS Amplifier is one of the most widely used amplifiers due to its high gain capabilities and various analog signal processing tasks. Today we will be using the software LTspice to analyse the DC, Transient and AC characteristics of the CS Amplifier to understand the operating point and working parameters such as gain, bandwidth and power. The given specifications are VDD=1.8v, power=50µW.
   ### 2. COMPONENTS USED
 | Components | Value/Model | Purpose |
 |------------|-------------|---------|
 |MOSFET (M1) | CMOSN (TSMC) | Main active element |
 | Resistor (R1) | 1kohm | Load Resistance |
 | Voltage source (V1) | 1.8V | Supply voltage |
 | Voltage source (V2) | SINE(0.9 50m 1k) | AC input signal(1kHz, 50mV AC + 0.9V DC) |
 | MOSFET model library |  .lib "tsmc018.lib" | Defines MOSFET characteristics |
### 3. CIRCUIT DIAGRAM
![Screenshot 2025-02-17 215720](https://github.com/user-attachments/assets/90460381-3199-4626-8b05-ea22212ce111)
We are using a MOSFET device namely NMOS4 which has four terminals. We are connecting a voltage source of 1.8v and giving gate voltage as 0.9v.
### 4. SIMULATION PROCEDURE
### DC Operating Point Analysis
Procedure:
First, we are going to select the .t option to select a spice directive and choose .lib tsmc018.lib. We consider the given power budget 50µW and calculate the current from the equation P=V*I. We get our current somewhere to be around 27µA. We can now select the appropriate L and W values for the MOSFET to conduct the current which we have got. We have set our L=400nm and w=372nm with 1kohm as the resistor value for the MOSFET to conduct 27µA current. Open the simulate tab and select the configure analysis option where a window will pop up. select the DC operating point option and set the .op option which pops up on the screen in the workspace. Click on run to analyse the DC operating parameters
![1 1](https://github.com/user-attachments/assets/42723a69-47ca-41e1-8f9c-a85f9186ee5c)
We can see that the current value is satisfactory. By selecting the gate voltage, we control the MOSFET to make it work in cut-off, triode or saturation region. Here by giving 0.9v as gate voltage which is considerably higher than the threshold voltage of 0.36v, we make the MOSFET to work in saturation region.
The working of the mosfet also depends on the L and W values of the MOSFET. According to the current equation, L is inversely proportional and W is directly proportional. For the increase in the value of L the current value decreases and the increasing value of W, the current increases. So, we need to set the L and W properly for the proper working of MOSFET. The Rd value also has a vital role in the working. If the resistance is high, the current is low and if the resistance is low, the current is high. But while designing for Rd, we should be careful as to not increase it by too much as it can make the MOSFET to shift out of saturation region which will make the MOSFET to not work properly.

  ### Transient response 
We will now introduce a sine source and conduct transient analysis by giving sine input at gate and observing the output at the drain terminal.   
- Amplitude: 50mV(peak)
- Frequency: 1kHz
- DC offset: 0.9V
![Screenshot 2025-02-17 225031](https://github.com/user-attachments/assets/4e6d9b9f-4e4e-4e57-95a5-8917c9d8d8f4)
Open the configure analysis menu and select the transient option. We have given the stop time to 5ms. After running the analysis, waveform window will pop-up where you need to select the point at which you need to do transient analysis. Hover over the designed circuit, a probe like structure will appear. Select the output point and input point to conduct the Transient analysis.
![Screenshot 2025-02-17 225800](https://github.com/user-attachments/assets/525d63da-19b3-4aa2-8b25-6c849baed51f)
![Screenshot 2025-02-17 225734](https://github.com/user-attachments/assets/decaa064-21a7-4540-ab4e-ec528f2d6541)
From the above pictures we can observe the 180 phase shift between input and output. We can also calculate the gain Av=Vo/Vi => Av=1.77/-0.945 => Av=-1.88.
### AC analysis
AC small signal is applied to the circuit to observe the frequency response of the circuit.
Select the input source and add 1 to amplitude of AC small signal analysis. Select the AC analysis under the configure analysis and choose decade as the type of sweep, 20 number of points, start frequency as 0.1 and stop frequency as 1t. Run the simulation and select the output input ports.
![Screenshot 2025-02-17 232614](https://github.com/user-attachments/assets/bc72e44c-e5c8-42e6-911e-fa4006666c59)
![Screenshot 2025-02-17 232558](https://github.com/user-attachments/assets/5259ff0e-8523-4c88-8908-c96cac86a7af)




### 5.SUMMARY
After analysing the circuit and and performing DC, Transient, AC analysis, we found that:
L=400nm
W=372nm
Rd=1k
Gain=-1.88

### 6. INFERENCE 
The MOSFET operates in the saturation region providing prescribed current and maintaining the power budget of the MOSFET. The Length and Width and Rd values help the MOSFET to keep working in the saturation region and provide the constant gain of -1.88.

### 7. CONCLUSION
The analysis of the Common-Source Amplifier using LTSpice provided valuable insights into its behavior under different conditions. The amplifier achieved the desired gain while staying within the power budget, demonstrating the effectiveness of the design. The results emphasize the importance of proper transistor sizing and component selection for optimal performance in analog circuits.

## CS Amplifier with current source load
### 1.CIRCUIT DIAGRAM
![Screenshot 2025-02-17 234041](https://github.com/user-attachments/assets/c8be77cb-b4ea-47f5-a939-f47e8cb82f52)

 ### 2. COMPONENTS USED
 | Components | Value/Model | Purpose |
 |------------|-------------|---------|
 |MOSFET (M1) | CMOSN | Main active element |
 | MOSFET (M2) | CMOSP | Main active element (replacing resistor (R1) |
 | Voltage source (V1) | 1.8V | Supply voltage |
 | Voltage source (V2) | SINE(0.9 50m 1k) | AC input signal(1kHz, 50mV AC + 0.9V DC) |
 | Voltage source (V3) | -2 | Gate voltage for CMOSP |
 | MOSFET model library | .lib "tsmc018.lib"| Defines MOSFET characteristics |   

  ### 3. SIMULATION PROCEDURE
We are conducting the same procedure and analysis but we are replacing the resistor with CMOSP. 
 ### 3.1 DC operating point analysis
 We provide the same working conditions for the CMOSP and do the DC, Transient and AC analysis. Set the gate voltage of PMOS so as to make sure that the PMOS is always ON. As we did in the part 1 of the experiment, by trial and error method, find the Length and Width of the MOSFET and do the DC Operating Point analysis
![Screenshot 2025-02-17 234759](https://github.com/user-attachments/assets/b5ad20ed-d2f0-42fe-8ca0-93baf5060d6b)
According to the power budget given, the current value is 27µA. The operating analysis makes sure that the PMOS is working in saturation region.

 ###  Transient Response
An alternating(sine) signal is given to the input source of 0.9v with 50m amplitude and 1k frequency.
![Screenshot 2025-02-17 235257](https://github.com/user-attachments/assets/59082fe7-700e-48f3-b503-0ab8b20a35e0)
![Screenshot 2025-02-17 235414](https://github.com/user-attachments/assets/4885d868-0f26-430a-b6bf-7b4e1f30d0f7)
![Screenshot 2025-02-17 235339](https://github.com/user-attachments/assets/17481fa4-8e63-44dd-80ee-5b127c72a3ca)
Here also we can observe the 180 phase shift with respect to input and output.
### AC Analysis
As in the part 1 experiment, apply small signal analysis to observe the frequency response of the circuit
![Screenshot 2025-02-17 235658](https://github.com/user-attachments/assets/18b5e7be-5a73-4ee2-9264-943224beac06)
![Screenshot 2025-02-17 235716](https://github.com/user-attachments/assets/a1aca382-bafd-4153-a230-cf2db424dc6f)

### 4. OBSERVATION
We can observe that the operating parameters doesnt change with the introduction of a PMOS as it acts as a linear resister or a current load which helps to regulate the current in the circuit and help to keep the NMOS in saturation region of operation
 
### 5. CONCLUSION
- The CMOS circuit simulated in LTSpice functions as an amplifier, operating in the saturation region with stable gain, phase shift and transient response.
-  The observed voltage gain and output characteristics validate its use in low-power amplification applications.
-  Further analysis, such as determining cut-off frequency and bandwidth, will help optimize the circuit for specific design requirements.

