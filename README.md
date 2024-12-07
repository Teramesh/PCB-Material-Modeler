# PCB-Material-Modeler
This spreadsheet calculates the PCB transmission line insertion loss versus frequency and temperature curves from the datasheet values of the dielectric constant and loss tangent, in addition to copper foil roughness parameters.

**User Guide**

1- Input the stripline dimensions, PCB process constants, and temperature coefficients.

![image](https://github.com/user-attachments/assets/88ebbb7f-f7b8-4cb0-b2f4-07aa9bbcc074)

2- Input the dielectric constant (DK) in-plane values versus frequency (GHz) for different thicknesses/resin contents. In-plane values are those that were characterized by SPC or Cylindrical resonator. When Dk is measured by an in-plane method (SPC or Cylindrical Resonator), effective Dk is linear to resin content for a given glass style. Then enter DF value as well, the DF value should be almost independent from the dielectric thickness.	

![image](https://github.com/user-attachments/assets/a4ff7e3b-5cc5-4ef5-b7b7-f624a6e8245b)

3- The tool will calculate the DK of the resin and the glass separately, then it will use them to calculate the in-plane effective dielectric constant and the out-of-plane value for the chosen dielectric thickness. These are the values that should be fed into field simulators. Calculation steps are detailed in the linked reference (PCB Laminate Anisotropy: The Impact on Advanced Via Modeling - https://www.signalintegrityjournal.com/articles/3422-pcb-laminate-anisotropy-the-impact-on-advanced-via-modeling)					

![image](https://github.com/user-attachments/assets/84787e3b-f191-4004-af9a-e67df1a4f00a)

4- The tool also calculates the stripline loss components (Dielectric loss, smooth metal, and loss due to roughness). Calculation equations are shown in the comments of each relevant cell.
    
![image](https://github.com/user-attachments/assets/37f45365-1161-4593-8bf9-89a0078f30f1)

5- Input up to 4 values of temperature to calculate the stripline loss vs temperature.
The tool takes into consideration the effect of temperature on DK, DF, and Copper conductivity.

![image](https://github.com/user-attachments/assets/f0e86406-c4d5-44c8-933e-87857968d76c)

