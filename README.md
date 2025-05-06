
# Experiment-6-currentmirror
<h1>CURRENT MIRROR</h1>     
<p> In the IC,the Mosfet amplifiers are baised using the CURRENT SOURCE. Typically in the IC's this current mirror is used as a current source. The main advantage of the baising the amplifier with the constant current is that it provides high voltage gain and it also improves the baising stability.</p>
<h3><b>CONTENTS</b></h3>
<br><b>THEORY</b>
<br><b>WORKING & APPLICATIONS</b>
<br><b>AIM OF THE CIRCUIT</b>
<br><b>REQUIRED COMPONENTS with there SPECIFICATION</b>
<br><b>LTSpice SIMULATION</b>
<br><b>CALCULATION AND COMPARION TABLE</b>
<br><b>Result, Inference, conclusion</b>

<h3><b>THEORY</b></h3>
<br>The current mirror is an analog circuit that senses the reference current and generates the copy or number of copies of the reference current, with the same characteristics. The replicated current is as stable as the reference current source. The replicated current could be the same as the reference current (Icopy = IREF), or it could be either multiple or fraction of the reference current.

<br>A current mirror can also be implemented using MOSFETs (Metal-Oxide-Semiconductor Field-Effect Transistors).
<br>Instead of BJTs, two identical MOSFETs (M1 and M2) are used.
<br>The drain of M1 is connected to its gate, forcing it into saturation mode, where it acts as a constant current source.
<br>The gate of M1 is connected to the gate of M2, ensuring that M2 also operates in the same conditions as M1. The output current I_OUT is then mirrored from I_REF.
<br>The reference current is given by the MOSFET saturation current equation:Iref=1/2kn(w/L)Vov^2


![image](https://github.com/user-attachments/assets/f7bc1780-deb8-42f6-8ee8-711e1b93b35d)


<h3><b>Why Current source</b></h3>
Current Mirrors are particularly useful in the integrated circuits, for biasing the amplifiers. The advantage of biasing the amplifiers with the current source is that it provides a high voltage gain and good biasing stability. This current source can be generated using a simple PMOS transistor or using a MOS transistor in cascode configuration (to achieve higher gain) as shown in figure

![image](https://github.com/user-attachments/assets/f6266441-6905-4fd3-b473-c9703af54836)



But this type of MOS current source  is susceptible to the change in the biasing voltage and the change in temperature. Moreover, the integrated circuit may contain hundred or thousand of such amplifiers. To bias all the amplifiers with precise biasing voltage is another challenge. So, to overcome all these problems, in integrated circuits, one stable current source is fabricated within IC, and using the current mirror the multiple copies of the stable current source is generated (which can be used to bias the amplifiers)

<h3><b>MOSFET- Current Mirror</b></h3>
It shows a current mirror circuit using the NMOS transistor. The reference current is converted to the voltage using diode connected transistor and the same is applied between the gate and the source of the another MOSFET.


![image](https://github.com/user-attachments/assets/70a75796-f56b-4378-8f57-924361d8297c)

<br>The relation between the ID1 and IREF can be given by the expression Id1=((w/l)1/(w/l)ref)Iref

By changing the W/L ratio of the two transistors, the current which is fraction or multiple of the reference current can be generated. The only thing which needs to be ensured is that, the MOSFET should operate in the saturation region.

<h3><b>Effect of Channel Length Modulation on Current Mirror</b></h3>
So far during the discussion, the effect of channel length modulation was neglected. If the channel length modulation effect is also considered, as the drain to source voltage (VDS) of the MOSFET increases, the drain current also slightly increases.

<br>Considering the channel length modulation effect, if VDS of MOSFET M1 changes by ΔVDS then the drain current ID1 also changes to ID1 + ΔID1. 

![image](https://github.com/user-attachments/assets/814fc7d4-47a7-40e1-b1cd-427b9027c39c)

<br>The effect of channel length modulation can be reduced by increasing the length of the channel for the given W/L ratio.

![image](https://github.com/user-attachments/assets/5584fcc9-f40d-4396-919b-5c47c0585e5c)

<h3><b>PMOS Current Mirror</b></h3>
It shows the implementation of current mirror using the PMOS transistors. In PMOS current mirror, the source terminals for both transistors are connected to Supply voltage Vdd.

![image](https://github.com/user-attachments/assets/9115b085-bc37-4da3-905d-9bcbe34ad911)

<h3><b>APPLICATIONS</b></h3>
<br>Biasing circuits
<br>Analog signal processing
<br>voltage references
<br>digital to analog converter
<br>operational amplifier
<br>sensor circuits



<h3>AIM</h3>
<b>Design and analyze current mirror circuit as active load in amplifier circuit</b>

<br><b>A)Circuit daigram1</b>

![image](https://github.com/user-attachments/assets/d78da15e-9d51-4c8b-b3c1-73b958d48fff)


<br><b>1.</b> Design for Av>-10v/v, VDD=1.8v, P<=1mw
<br>Itotal=P/VDD   and  Itotal=Iref+Ix
<br>design for the current mirror ratio----> 1:1 and 1:2 
<br><b>2.</b>Analyze the circuit current mirror--->DC analysis
<br><b>3. case1:a)</b>Lmin=180nm      (W/L)=x
           <br> <b>b)</b>l=500nm     (W/L)=x
          <br> <b>c)</b>L=1um       (W/L)=x
<br>Avalyze the current mirroring maintain (W/L) same as first design
<br><b>4.</b>Transient and AC analysis
<br> Maximum output swing
<br>BW

<br><b>Vary the current mirror ratio and analyze the current copying/mirroring</b>

<b>B)Circuit daigram 2</b>

![image](https://github.com/user-attachments/assets/2e480a47-2a14-4beb-bc18-3c8dadcbd15a)

Design the differential Amplifier using the same design specification as experiment 3 ---> differencial amplifier, Perform DC analysis, transient analysis and AC analysis

<h3><b>REQUIRED COMPONENTS with their SPECIFICATION</b></h3>

| *Component*   | *Label* | *Specification/Description* |
|---------------|----------|----------------------------|
| *MOSFETs*   | M1, M2  | Matched PMOSFETs for current mirroring |
| *MOSFET*    | M3      | Acts as an active load (common source amplifier) |
| *Power Supply* | VDD | 1.8V  |
| *Current Source* | I_ref | Reference current source |
| *Input voltage* | Vin 0.5V| Used for biasing (values depend on design) |

<h3><b>LTSpice simulation</b></h3>
<br><b>DESIGN FOR THE CURRENT MIRROR RATIO 1:1</b>

<h4><b>CIRCUIT DAIGRAM 01</b></h4>

![image](https://github.com/user-attachments/assets/2ea6a758-a22b-4153-b9ed-1cc18f0279d2)


   
<br>M1 Lenght= M2 Lenght= 180nm
<br>M1 Width=10um and M2 Width = 10um (bcz for 1:1 ratio)

<h4><b>DC Analysis</b></h4>

![image](https://github.com/user-attachments/assets/6695cb06-a86e-43a3-8bd2-5f4a84cf4ecf)



<br>Vout=VDD/2
<br>Vout =1.8/2=0.9V(Theoritically)
<br>From DC Analysis
<br>Vout=0.987608
<br>Vx=0.967276
<br>Vout= Vx(approxiamety)
<br>Itotal=Iref+Ix
<br>Iref=0.277m
<br>Ix=0.277m
<br>Iref=Ix
<br> we can observe that PMOS are diode connected so by inspection it is working in saturation region



<h4><b>TRANSIENT ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/d56792e4-4407-4b36-af3c-b8d29a13bfdd)


<br>The Vin is given as DC offset value that is 0.526,20m,1K hz frequency so for that values we can observe the <b>output voltage is 1.45V</b>

<h4><b>AC ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/214e61fe-bd11-49e1-baab-84e917dd1a4d)


<br>The GAIN from the LTSpice simulation of this circuit is 27dB
<br>27-3=24dB
<br>BANDWIDTH=FH-FL=756.67M-0
<br>BANDWIDTH=756.67MHz


<br><b>DESIGN FOR THE CURRENT MIRROR RATIO 1:2</b>
<h4><b>CIRCUIT DAIGRAM 02</b></h4>

![image](https://github.com/user-attachments/assets/1abeb4fb-559f-4e52-a017-0a2b06d036a3)


<br>M1 Lenght= M2 Lenght= 180nm
<br>M1 Width=10um and M2 Width = 20um (bcz for 1:2 ratio)

<h4><b>DC Analysis</b></h4>

![image](https://github.com/user-attachments/assets/aa6fb0e7-52a6-4244-aac7-d5369c105f0c)


<br>Vout=VDD/2
<br>   =1.8/2=0.9V(Theoritically)
<br>From DC Analysis
<br>Vout=0.99867V
<br>VX=1.03471

<br>here Vout is less than Vx
<br>Itotal=Iref+Ix
<br>Iref=0.0001833A
<br>Ix=0.000366661A




<h4><b>TRANSIENT ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/f0d77ef0-e99b-437d-81e8-7c05627ccf5b)



<br>The Vin is given as DC offset value that is 0.526,20m,1K hz frequency so for that values we can observe the <b>output voltage is 1.5V</b>

<h4><b>AC ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/10b9ae8e-18e8-4718-ba9e-1d44b403022e)



<br>The GAIN from the LTSpice simulation of this circuit is 29.5dB
<br>29.5-3=26.5dB
<br>BANDWIDTH=FH-FL
<br>BANDWIDTH=756.67MHz


<br><h3><b>Analyze the current mirroring maintaining (W/L) same as first design</h3>

<br>L=500nm
<h4><b>CIRCUIT DAIGRAM 03</b></h4>


![image](https://github.com/user-attachments/assets/db46f8c0-2af1-43c9-a2cd-946acc77adac)


   
<br>M1 Lenght= M2 Lenght= 500n
<br>M1 Width=10um and M2 Width = 10um 

<h4><b>DC Analysis</b></h4>

![image](https://github.com/user-attachments/assets/1bc816ad-5451-4dc1-92f8-726301488d12)


<br>Vout=VDD/2
<br>   =1.8/2=0.9V(Theoritically)
<br>From DC Analysis
<br>Vout=0.921105
<br>Itotal=Iref+Ix
<br>Iref=0.277mA
<br>Ix=0.271mA
<br>Iref=Ix(approxiametely)




<h4><b>TRANSIENT ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/8c848f66-2ef0-47b9-b9d8-5b58aeb33cdc)



<br>The Vin is given as DC offset value that is 0.526,20m,1K hz frequency so for that values we can observe the <b>output voltage is 1.4V</b>

<h4><b>AC ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/39e9f227-d3cd-4c02-b0c8-516db20dbd91)

<br>The GAIN from the LTSpice simulation of this circuit is 29.1dB
<br>29.1-3=26.1dB
<br>BANDWIDTH=FH-FL=756.67M-0
<br>BANDWIDTH=756.67MHz



<br>FOR L=1um
<h4><b>CIRCUIT DAIGRAM 04</b></h4>


![image](https://github.com/user-attachments/assets/4eeebfb8-df18-4c0b-ad67-3144ab922bd3)


   
<br>M1 Lenght= M2 Lenght= 1um
<br>M1 Width=10um and M2 Width = 10um 

<h4><b>DC Analysis</b></h4>

![image](https://github.com/user-attachments/assets/b571a153-b132-4742-bd6b-cd1fe1be81d9)


<br>Vout=VDD/2
<br>   =1.8/2=0.9V(Theoritically)
<br>From DC Analysis
<br>Vout=0.291503
<br>Itotal=Iref+Ix
<br>Iref=277uA
<br>Ix=0.27777
<br>Iref=Ix




<h4><b>TRANSIENT ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/af17edf9-6065-42f8-a303-d55d1222a42b)



<br>The Vin is given as DC offset value that is 0.526,20m,1K hz frequency so for that values we can observe the <b>output voltage is 1.1V</b>

<h4><b>AC ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/7808a723-493b-45c2-8493-59d57373c782)


<br>The GAIN from the LTSpice simulation of this circuit is 29.5dB
<br>30-3=27dB
<br>BANDWIDTH=FH-FL
<br>BANDWIDTH=756.67MHz

<br><b>Vary the current mirror ratio and analyze the current copying/mirroring</b>

<h4><b>DC Analysis</b></h4>
Current through M1 and M3 is same (0.37mA)
vout and vx has been incresed from the previous case.(1:2)

![image](https://github.com/user-attachments/assets/46156751-455d-4765-9b18-a220a4cbda56)


The gain is 15dB. For 1:3 ratio current Mirror
let I_REF=0.138mA and I_X=3I_REF =0.4166mA

since the I_TOTAL is remines same P_TOTAL also remains same. Here ,The aspect ratio of MOSFET M1 is thrice of M3. (W/L) of MOSFET 1= 300u/180n.
(W/L) of MOSFET 2= 100u/180n
<br>Vout=1.19361V
<br>Itotal=Iref+Ix
<br>Iref=0.185m
<br>Ix=0.3703mA


<h4><b>TRANSIENT ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/a6ffa32b-948e-44fd-9447-6f6385027d05)

<br>The Vin is given as DC offset value that is 0.526,20m,1K hz frequency so for that values we can observe the <b>output voltage is 710mV</b>


<h4><b>AC ANALYSIS</b></h4>

![image](https://github.com/user-attachments/assets/553b02e9-0906-4236-8f22-f33f69fa5c53)

<br>The GAIN from the LTSpice simulation of this circuit is 12dB
 For 1:3 ratio current Mirror
I_REF=0.138mA and I_X=3I_REF =0.4166mA





<b>B)Circuit daigram 2 Differencial pair with current source</b>

![image](https://github.com/user-attachments/assets/e7be475f-1ce0-46cf-8f0e-87ffb3f8be5b)



<h3>DC ANALYSIS</h3>

![image](https://github.com/user-attachments/assets/e32fabc3-7f87-4bb0-94f1-a7d8640c1c9a)


<h3>TRANSIENT ANALYSIS</h3>

![image](https://github.com/user-attachments/assets/a87be8bc-7db8-4f47-a118-09a458903958)
<br>The Vin is given as DC offset value that is 0.526,20m,1K hz frequency so for that values we can observe the <b>output voltage is 1.9V</b>



<h3>AC ANALYSIS</h3>

![image](https://github.com/user-attachments/assets/9db4f418-0185-4105-a534-2aed9265adc3)

<br>The GAIN from the LTSpice simulation of this circuit is 30dB






<h3><b> Comparison Between 1:1 and 1:2 Current Mirrors</b></h3>

| Feature              | **1:1 Current Mirror** | **1:2 Current Mirror** |
|----------------------|----------------------|----------------------|
| **Current Ratio (Iout/Iref)** | 1:1 (Iout = Iref) | 1:2 (Iout = 2 × Iref) |
| **Number of Output Branches** | 1 | 1 (but with 2× current) |
| **Vout** | 0.987608|0.9986  |
| **Vx**| 0.967276| 1.03471|
| **Iref** | 0.277mA | 0.183mA |
| **Ix** | 0.277mA | 0.36667mA |
| **Gain** | 24dB | 26.5dB |



<h3><b>Comparison of MOSFETs with Different Channel Lengths in AC & Transient Analysis</b> </h3>

| **Parameter**               | **L = 180 nm**    | **L = 500 nm**    | **L = 1 µm**      |
|----------------------------|------------------|------------------|------------------|
| **Width (W)**              | 10 µm           | 10 µm           | 10 µm           |
| **Length (L)**             | 180 nm          | 500 nm          | 1 µm            |
| **W/L Ratio**              | 55.56           | 20              | 10              |
| **VOUT** |    0.987608V       | Medium          | High            |
| **Vx** | 0.967276V     | Medium          | Low             |

<h3>INFERENCE</h3>
<br>1.Here we can observe that Iref is exactly equal to ID IN CASE OF 1:1 RAatio in some cases current mirroring doesnt happened accurately due to channel length modulation
<br>2Current Matching: The output current follows the reference current, ensuring accurate current replication.
<br>3.Output voltage swing increases as the channel length increases.
<br>4.The gain increases and decreasing  with higher current mirror ratios, reaching a maximum of 31.344 dB for a 2:1 ratio, demonstrating the impact of active load selection in amplifier circuits.
<br>5.Differential pair with current source amplifier  implementation using a current mirror as an active load, with a gain is 30dB.
<br>6.Despite different current mirror ratios, the total power dissipation remains within the 1mW design constraint, validating the circuit’s low-power operation.
<br>7. Lower supply voltages limit output voltage swing and overall circuit performance.



  
