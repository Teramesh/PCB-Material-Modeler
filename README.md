# PCB-Material-Modeler
Teramesh's [PCB Material Modeler spreadsheet](https://github.com/Teramesh/PCB-Material-Modeler/blob/main/PCB_Material_Modeler.xlsx) calculates the PCB transmission line insertion loss versus frequency and temperature curves from the datasheet values of the dielectric constant and loss tangent, in addition to copper foil roughness parameters.

**User Guide**

1- Input the stripline dimensions, PCB process constants, and temperature coefficients in the **Material Database** tab, then select the material and desired copper foil process, and observe the values being read in the **Material Modeler** tab.

<img width="1107" height="105" alt="image" src="https://github.com/user-attachments/assets/16ca43e6-04d5-4501-ba16-fd841698c3c3" />


2- The dielectric constant (DK) in-plane values versus frequency (GHz) for different thicknesses/resin contents. In-plane values are those that were characterized by SPC or Cylindrical resonator. When Dk is measured by an in-plane method (SPC or Cylindrical Resonator), effective Dk is linear to resin content for a given glass style. Then enter DF value as well, the DF value should be almost independent from the dielectric thickness.	

<img width="652" height="270" alt="image" src="https://github.com/user-attachments/assets/539a147f-470b-4b7f-9480-a2c446fd515e" />


3- The tool will calculate the DK of the resin and the glass separately, then it will use them to calculate the in-plane effective dielectric constant and the out-of-plane value for the chosen dielectric thickness. These are the values that should be fed into field simulators. Calculation steps are detailed in the linked article [Signal Integrity Analysis Methodology for Printed Circuit Boards](https://www.teramesh.tech/Resources/Knowledge-Base/Signal-Integrity-Analysis-Methodology-for-Printed-Circuit-Boards).

<img width="873" height="314" alt="image" src="https://github.com/user-attachments/assets/b45518ff-408b-4102-94e7-c437929770c6" />


4- The tool also assumes a linear dependence of DK and DF values over temperature as per the Tc_DK (1/°C) and Tc_DF (1/°C) values entered in the Material Database.

<img width="861" height="277" alt="image" src="https://github.com/user-attachments/assets/24d19de6-8513-4f5c-8ea2-02325a8efc36" />


5- The tool also calculates the stripline loss components (Dielectric loss, smooth metal, and loss due to roughness). Calculation equations are shown in the comments of each relevant cell.
    
<img width="548" height="509" alt="image" src="https://github.com/user-attachments/assets/39a857bf-ccbc-4168-8e8b-74349ac8686d" />


6- Input up to 4 values of temperature to calculate the stripline loss vs temperature.
The tool takes into consideration the effect of temperature on DK, DF, and Copper conductivity.
These are the 4 temperature points at which DK and Df were plotted in the charts in section 4.

<img width="1139" height="503" alt="image" src="https://github.com/user-attachments/assets/745f6d4c-dfab-49d0-b580-9e5768be385a" />


7- Input stripline geometric parameters in the Transmission Line Design tab, along with their manufacturing tolerances. Transmission line impedance, attenuation, and RLGC parameters are calculated for the odd and even modes, with statistical variances (from manufacturing tolerances). Numerical accuracy can be improved by utilizing 2D field solver results for the grey-highlighted cells. The user can also change the temperature at which the parameters are being calculated.

<img width="883" height="1343" alt="image" src="https://github.com/user-attachments/assets/7086db76-e691-4a29-b4cd-4a5ccfc32c61" />
