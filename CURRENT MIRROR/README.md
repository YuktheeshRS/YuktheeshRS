![1](https://github.com/user-attachments/assets/562abb29-4b67-4f01-8dce-5e61f0493051)
#  Current Mirroring Experiment
Given :

V<sub>dd</sub>=1.8 V.\
P <=1 mW.\
A<sub>v</sub>>-10 V/V.
### Circuit diagram :
![2](https://github.com/user-attachments/assets/5d780558-a792-4e9f-8d01-5b316661cd55)
# FOR L = 180 nm
# **1:1 Ratio :**
# **DC Analysis:**
I<sub>Total</sub> = P/V<sub>DD</sub>\
Since the ratio is 1:1 I<sub>ref</sub> = I<sub>x</sub>\
I<sub>ref</sub> = I<sub>Total</sub>/2\
I<sub>Total</sub> = 1 mW/1.8 V\
I<sub>Total</sub> = 0.555 mA\
I<sub>ref</sub> = 0.555 m/2\
I<sub>ref</sub> = 0.2778 mA.\
The W/L values for M1, M2, and M3 are 10	µm/180nm, 10	µm/180nm, and 10	µm/180nm, respectively.
![3](https://github.com/user-attachments/assets/66070b61-b1da-4b22-9379-c57f1196a553)
![4](https://github.com/user-attachments/assets/44befd1b-aabd-4570-9d2a-85daf25d2d93)
# **Transient Analysis :**
- Change the input voltage to sine and change the amplitude to 50 mV , frequency to 1 kHz and offset voltage to 0.6275 V.
- ![5](https://github.com/user-attachments/assets/9e84e496-5185-4747-850e-bec9dcc1db79)
# **AC Analysis :**
![6](https://github.com/user-attachments/assets/d41579fb-880e-400d-9697-2e284ff0185f)
The Expected gain in dB is 20 and the obtained gain is 26.23 dB.
 # **1:2 Ratio :**
 # **DC Analysis :**
 ![7](https://github.com/user-attachments/assets/4b1a73dc-85f7-4a0d-a29f-050c3901f2ec)
In order to determine the current value based on the specified ratio, the W/L values for  M2 and M3 are 6	µm/180nm and 6	µm/180nm, nd M1 is 3	µm/180nm respectively. 
# **Transient Analysis :**
![8](https://github.com/user-attachments/assets/66eecc3c-4b12-4a8d-b379-d698e854d394)
 The expected gain was greater than or equal to 10 V/V and the obtained gain is 12.11 V/V.
 # **AC Analysis :**
 ![9](https://github.com/user-attachments/assets/d6906c9d-6b26-4b03-905d-ef837fda3e26)


# **2:1 Ratio :**

## **DC Analysis :**
![10](https://github.com/user-attachments/assets/3bf123a0-d58f-45a1-8212-61f96f33fd7f)
I<sub>ref</sub> = 0.555 mA.
In order to determine the current value based on the specified ratio, the W/L values for  M2 and M3 are 6	µm/180nm and 6	µm/180nm, nd M1 is 3	µm/180nm respectively.
## **Transient Analysis :**
![11](https://github.com/user-attachments/assets/62b800ae-665f-4cb8-ae03-25380b8c2b11)
 The expected gain was greater than or equal to 10 V/V and the obtained gain is 9.86 V/V.\
 ## **AC Analysis :**
 ![12](https://github.com/user-attachments/assets/66a39208-28b2-42a2-bcf0-39de27cf17ed)

# FOR L = 1 	µm

|Ratio|  Av(in dB)    | Av(in V/V) | 
|-----|---------------|------------|
|1:1  |12.60          |15.3        |    
|1:2  |9.55           |15.98       |   
|2:1  |12.56          |16.87       |

# **Inference :**
- The current mirror circuit accurately copies the reference current with very little variation, ensuring reliable current mirroring across different W/L ratios.
- Even when the W/L ratio changes while keeping the same proportion, the drain current (I<sub>D</sub>) stays nearly the same, confirming the circuit's effectiveness.
- The amplifier gain is slightly higher than expected due to small differences in transistor properties or minor simulation effects.
- When the mirror ratio increases (from 1:1 to 1:2), the gain also increases as expected.
- Overall, the results closely match theoretical predictions, proving that the simulation and circuit design are working correctly.



# *PART-B*
**Aim :**
Design the differential amplifier using the same design specification as Experiment-3. Perform DC analysis,trasient and AC analysis.
![13](https://github.com/user-attachments/assets/72ec144c-cf3b-4bf9-8208-bea9db702c95)
# **DC Analysis :**
1.Case 1: 180nm
![14](https://github.com/user-attachments/assets/b0ceac3d-b2e4-4f5e-b790-071252c3eb12)
PMOSFET 1,2 = width is 70um \
M3, M4  = width is 238.7um\
M5 = width is 70um\
M6 = width is 140um\
V<sub>out</sub>=  1.4V\
I<sub>ref</sub> = 0.277mA\

2.Case 2: 500nm
![15](https://github.com/user-attachments/assets/dd6c5a70-c60a-4bdd-b7b4-dc464b01e95b)
PMOSFET 1,2 = width is 70um \
M3, M4  = width is 693.6um\
M5 = width is 70um\
M6 = width is 140um\
V<sub>out</sub>=  1.41V\
I<sub>ref</sub> = 0.277mA\

### Transient analysis:
1.Case 1: 180nm
![16](https://github.com/user-attachments/assets/8afb0383-9dff-4b73-9d45-2799bc48615a)

2.Case 2: 500nm
![17](https://github.com/user-attachments/assets/d580af08-4ecd-40bb-a0c1-fd5bcae92c2c)

# **Inference :**
- The circuit operates as a differential amplifier based on a current mirror, with the output (Vout) being controlled by the difference between V2 and V3.
- Stable current replication is guaranteed by the PMOS current mirror (M1-M2).
- This circuit is helpful for signal processing and amplification in analog designs because it uses the NMOS differential pair (M3-M4) for amplification.
