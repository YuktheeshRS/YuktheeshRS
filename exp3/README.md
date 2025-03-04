# LINEAR INTEGRATED CIRCUITS
## EXPERIMENT 3:- DIFFERENTIAL AMPLIFIER
### INTRODUCTION:
  A MOS Differential Amplifier is a device built using a MOSFET(NMOS Transistors) that amplifies the input signal, minimizing noise interference and rejecting signals common to both signals. The device consists of a pair of MOSFETs which is paired together which act as inputs and resistors to make sure the MOSFETs work in saturation region. The output is commonly taken from the drains of the FETs and voltage is given to both the gate terminals. The use of BJTs to work as amplifiers can also be done but the MOSFETs as Differential Amplifiers offer very high INPUT IMPEDANCE. Let us study the circuit
  ![Screenshot 2025-03-04 003509](https://github.com/user-attachments/assets/5990a798-2cbe-43cf-82b6-5d2158feefe9)
  This is an ample circuit to explain the MOS Differential Amplifier. The Circuit consists of 2 transistors Q1 and Q2 which are the input pair. Rd resistors are used to convert the drain currents to output currents. VDD and VSS act as input and output points. The Total current flowing in VSS is the sum of the current in both branches. When the differential inputs are, the current flowing in the branches is equal. When given the same inputs to the gate terminal of both the branches, it is called COMMON MODE Amplifier which has high noise interference rejection.
  Now, let us design a MOS Differential Amplifier circuit with the given parameters: VDD=2.2v, P<=2.2mW, Vicm=1.2v, Vocm=1.25V with node voltage Vp=0.4v.
### Design and Analyze the Differential Amplifier for the following specs: VDD=2.2v, P<=2.2mW, Vicm=1.2v, Vocm=1.25V with node voltage Vp=0.4v. Perform DC Analysis, Transient Analysis and Frequency response and extract the parameters.
 ![Screenshot 2025-03-04 003509](https://github.com/user-attachments/assets/5990a798-2cbe-43cf-82b6-5d2158feefe9)
 Observing the above circuit, to calculate the required parameters, we need to calculate the values of Rd and RSS to help the MOSFET function properly. 
 Given:- VDD=2.2v, P<=2.2mW, Vicm=1.2v, Vocm=1.25v, Vp=0.4v. 
 We know that P=VI. Using this, we can calculate the total current flowing in the circuit. I=P/VDD => I=2.2m/2.2 => I=1mA.
 Since ID1=ID2=I/2, I/2=0.5mA=ID1=ID2. After calculating the 
 
 
 total and branch current we can calculate the resistor values. Rd=VDD-Vocm/ID1 => 2.2-1.25/0.5M => Rd=1.9kΩ. RSS=Vp/ISS => RSS=0.4/1m => RSS=400Ω. 
 ![Screenshot 2025-03-03 200939](https://github.com/user-attachments/assets/f22b37ba-a89e-4da3-bcf7-4fa6cd368b30)
### DC ANALYSIS
  Now let us analyse the DC characteristics of the circuit. After calculating the Rd and RSS values, assign values to W and L of the MOSFETs to make sure that the prescribed current is flowing in each branch. We have considered the values L=180n and W=6.41246 for the optimal working of the FET. 
  ![Screenshot 2025-03-03 223203](https://github.com/user-attachments/assets/ce344b96-4bb3-4514-9f31-b34fe0305268)
![Screenshot 2025-03-03 200918](https://github.com/user-attachments/assets/45b41617-305d-4bd1-9d36-0b0669ebd413)
The above photo shows us that the MOSFETs are porking in the prescribed region and the desired output is obtained from them. The current obtained is 0.5mA passing through each transistor and the values of Vocm and Vp satisfy the design specifications. To cross-verify calculate the power of the present parameters P=VI => 2.2x1m => P=2.2mW which satisfies the given condition(Power rating should be 2.2mW or below). 
### TRANSIENT ANALYSIS
  Now let us perform transient analysis by giving Sine input with an offset voltage of 1.2v, amplitude of 50m and a frequency of 1kHz to both the gate voltage source and observe the changes. The graph is observed between the output Vocm and the input gate voltage to analyse the circuit. Conduct the transient analysis by giving the stop time as 5m.
  ![Screenshot 2025-03-03 201055](https://github.com/user-attachments/assets/b870657d-6d6b-4acf-b761-cb255f20821f)
  In the above shown photo, The blue sine wave indicates the input signal and the green sine wave indicates the output signal. We can observe that the amplifier circuit produces output with 180 phase shifts concerning input. Let us calculate the Gain of the circuit. We know that Av=Vout/Vin => Av=(1.4493-1.051)/(1.2496-1.1503) => Av=4.012. The dB conversion of the gain is dB=20xlog(Av) => 20xlog(4.012) => dB=12.067dB. This can be verified by conducting an AC analysis.
### AC Analysis
  The AC analysis is done to verify the gain calculated during the transient analysis and to find out the 3dB bandwidth of the differential amplifier circuit. We supply the circuit with the same sinusoidal signal to the gate terminals and we will set the AC Amplitude as 1. Let us run the analysis.
  ![Screenshot 2025-03-03 202036](https://github.com/user-attachments/assets/f2873f5d-584d-4c33-af4c-48cdb2973fe6)
  From the above photo, we can confirm our theoretical findings of the gain Av is very nearer the the actual finding at around 175°. This helps us to understand the working and the output of the circuit. Now let us analyse a variation of the current Differential Amplifier circuit.
#### REPLACING RESISTOR RSS WITH A CURRENT SOURCE
  Now, let us replace the resistor RSS with a current source and analyse the circuit. The current source is introduced to provide more stability to the circuit by maintaining constant current through the MOSFETs. The current source rejects the change in Vg1 and Vg2 which in turn does not change the differential output. This is used in the Common-Mode amplifier which helps in rejecting the noise and other interference which affects the output. This helps to provide better control over the tail current and helps to attain higher gain in the circuit since it has higher output impedance and improves the Common Mode Rejection Ratio.
  ![Screenshot 2025-03-03 201914](https://github.com/user-attachments/assets/103f0f91-3fcc-451d-b5b5-71309d6591eb)
Now, with the circuit ready, let us perform DC Analysis on the circuit.
### DC Analysis
![Screenshot 2025-03-03 201704](https://github.com/user-attachments/assets/114a5b6b-5310-4cba-a9a5-4dcc42dd70bd)
  Since there is not much change in the components of the circuit other than the current source, there is not much change in the DC Output. Since the Current source stabilizes the current through the MOSFETs, the overall stability increases. The current and the voltage across Vp remain the same.
  The power budget will be within the limit of 2.2 mW. Now let us Conduct a Transient analysis
### TRANSIENT ANALYSIS
![Screenshot 2025-03-03 201055](https://github.com/user-attachments/assets/5a06353e-bb72-436c-9397-ce7cd2204fed)
  Set the gate voltage sources with sinusoidal input of DC Offset 1.2, amplitude of 50m and frequency of 1kHz. observe the graph.
  The above photo shows that the output is in a 180-phase shift with the input. After calculating the gain, we get Av=Vout/Vin => Av=(1.4493-1.051)/(1.2496-1.1503) => Av=4.012. The dB conversion of the gain is dB=20xlog(Av) => 20xlog(4.012) => dB=12.067dB. We can verify this finding in the AC Analysis
### AC ANALYSIS
  To analyse the AC part of the circuit, let us set the sinusoidal input as before to the gate voltage sources and set the AC amplitude as 1. Now, Let us observe the frequency graph.
  ![Screenshot 2025-03-03 202036](https://github.com/user-attachments/assets/a68fea32-a2c9-4a2d-881f-65747e554af4)
As we can see, there is a negligible amount of variation in gain with the previous resistor circuit and the present current source. 
#### Replacing Current source with N-channel MOSFET
  Let us move to the final circuit. Replace the current source with an NMOS. The theory explanation for this is that the MOSFET acts as a CONSTANT CURRENT SOURCE when voltage is given to the gate terminal to make it work in the saturation region. After adjusting the W and L values to make sure that the MOSFET is conducting 1mA through it. After calculating, we found the W and L values to be L=180n and W=6.89912u. Now let us conduct a DC Analysis.
### DC Analysis
  ![Screenshot 2025-03-03 215327](https://github.com/user-attachments/assets/89fa7561-edfc-489c-a1d2-d58bf7551879)
  According to the definition of MOSFET, we need to provide voltage to the gate terminal so that it drives the MOSFET to work in saturation region. To consider the value of Vg, let us consider overdrive voltage. We know that Vd should be greater than Vov. The formula is Vds>Vov. We know that Vov=Vgs-Vt. Substituting that, we get Vds>Vgs-Vt. Rearranging that we get the formula Vgs>Vds+Vt. We know the value of Vds(Vd-Vs => Vp-0 => 0.4) which is 0.4 and the given value of Vt for the MOSFET is 0.366. Using this, we get Vgs>0.4+0.366 => Vgs>0.766. The approximate value to be give to Vg should be greater than 0.766. So let us provide voltage of 1v to Vg. After setting the value of Vg, we find the W and L values which are 6.89912u and 180n respectively. 
![Screenshot 2025-03-03 215757](https://github.com/user-attachments/assets/4cb970a5-f5bf-46b9-9131-b069c59e464e)
![Screenshot 2025-03-03 215305](https://github.com/user-attachments/assets/ff770a3b-2401-45dd-b322-d37edddfe8d5)
  We can observe that the sum of both the branch current of 1mA is available through the MOSFET M3 which makes it to act like a current source. According the value, we can calculate the POWER RATING of the circuit which will come out to be 2.2mW which is the prescribed and preferred value. After confirming the values, we can now proceed to so Transient Analysis to calculate the gain of the circuit.
### Transient Analysis
  Like before, we apply a sinusoidal input to the MOSFET M1 and M2 with offset 1.2v, amplitude 50m and frequency of 1k to calculate the gain. Let us study the graph.
  ![Screenshot 2025-03-03 201055](https://github.com/user-attachments/assets/1f00ff1e-1e81-4f5a-aab7-4581ea99c8bd)
  We can observe that the output is amplified with the output with just a slight variation. Calculating gain we get Av 4.03 which converted to dB is 12.10dB. We can verify the results by conducting AC Analysis.
### AC Analysis
  After calculating the dB gain of 12.10dB from the graph obtained from Transient analysis, let us confirm the finding by analysing the AC component of the circuit. Provide AC AMPLITUDE of 1 to the MOSFETs M1 and M2 and conduct the analysis.
  ![Screenshot 2025-03-03 202036](https://github.com/user-attachments/assets/cafc1f4d-423e-4595-8cac-ad8e81d80c77)
  We can observe that the calculated value of gain corresponds with the gain plotted from the graph of AC Analysis
## INFERENCE
  After conducting the simulation and studying the circuit, we can conclude that the biulding block of an op-amp is DIFFERENTIAL AMPLIFIER for its ability to reject the common mode signals and helps in amplifing the differential input of the MOSFETs. It ensures the credibility of the op-amp and helps it to have a very high gain properties. We also studied the effects of the working of the circuit with different configurations such as providing a current source or connecting a MOSFET to make it act as a CONSTANT CURRENT SOURCE. We can conclude that use of MOSFET as a current source can be done to increase the stability of the tail current. But the other parameters such as temperature, technical errors or tolerance errors make the use of MOSFET a risk as it can compromise the working of the op-amps. So, the use of a current source can be implemented as it provides more stability to the tail current and has fewer credibility issues compared to the MOSET
