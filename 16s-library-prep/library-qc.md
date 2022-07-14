# Library QC

*This protocol has been adapted from the protocols of Jordan Bisanz Laboratory at the Pennsylvania State University.*

## Prepare Your Workspace

- [ ] Turn on the PCR Clean Hood blower and white light. 
- [ ] Clean the cabinet with 70% ethanol including work surface and walls. 
- [ ] Turn the dial and run the UV light for at least 10 minutes. 

⚠️ You cannot expect the glass to protect you from UV exposure. You can be in a different part of the lab while the light is running, but do not loiter in front of the cabinet.

- [ ] Once the timer is up and the UV light turns off, you are ready to begin. 

*Remember, before placing any objects in the hood, they must be sprayed with 70% ethanol.*

## Gather Materials
- [ ] KAPA Library Quantification Kit for Illumina Platforms (KAPA KK4824), standards can be ordered separately as they are limiting reagent of kit (KAPA KK4903)
- [ ] 384-well or 96-well plates for qPCR
- [ ] Optically clear plate seals
- [ ] Dilution buffer (10mM Tris-HCl pH 8, 0.05% Tween, note: can be prepared from Qiagen EB + Tween)

## qPCR

1.	If first time using the kit, add the 10X primer premix to the KAPA SYBRFast qPCR Master Mix (2X).
2.	Add 6uL of Master Mix to 30 wells of the plate [this is for (6 standards x 3 replicates) + (3 dilutions of library + 3 negative controls)]
3.	Transfer 4uL of the 6 standards into triplicate wells.
4.	Create a dilution series of your library in dilution buffer with the following dilutions:  
      a. 2uL of library into 198uL buffer (100x)  
      b. 2uL of 1:100 dilution into 198uL buffer (10,000x)  
      c. 20uL of 1:10,000 dilution into 180uL buffer (100,000x)  
      d. 20uL of 1:100,000 dilution into 180uL buffer (1,000,000x)  
5.	Transfer 4uL of dilutions b, c, and d in triplicate to appropriate wells.
6.	Seal plate with optically clear seal and centrifuge briefly.
7.	Amplify according to the parameters below: 

## qPCR Analysis

1. After completing the run, export the data. 
2. From the Cq results: plate view, transfer appropriate values to the excel spreadsheet, 16S-Library-Prep.xlsx file into the highlighted boxes in the LibraryNorm tab. Use the average fragment length appropriate for your amplicon.  
       a. For the region we use most commonly, it should be 291.  
       b. You can also run the sample on Bioanalyzer to determine the appropriate amplicon length.   
3. Amplicon efficiency should be between 90-110% and the R2 value should be greater than 0.99. 


