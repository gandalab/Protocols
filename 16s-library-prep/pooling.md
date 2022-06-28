# Pooling Library

*This protocol has been adapted from the protocols of Jordan Bisanz Laboratory at the Pennsylvania State University.*

## Gather Materials

- [ ] Quant-It Picogreen dsDNA Assay Kit
- [ ] Black flat bottom microplates
- [ ] Reagent Reservoir
- [ ] Multichannel Pipette (P300, P100, P10)
- [ ] Pipette Tips (300uL, 100uL, 10uL)
- [ ] Fluorescent Plate Reader


- [ ] Qubit dsDNA High Sensitivity Working Solution
- [ ] Qubit dsDNA High Sensitivity Standards #1 and #2
- [ ] Qubit tubes
- [ ] Micropipette (P200, P10, P100)
- [ ] Pipette Tips (200uL, 10uL, 100uL)
- [ ] Sterile 2.0mL Centrifuge tube

## Quantification

***Using Quant-It Picogreen***
1. Prepare 110 reactions of Quant-It Picogreen solution by mixing 11mL dsDNA HS Buffer and 55uL dsDNA HS reagent dye. 
2. Add 100uL of reaction mix to each well in the plate. 
3. Using an empty lane of a partial plate, or a new plate if necessary, fill 1 column with 100uL of reaction mix in each well for the standard curve. 
4. Transfer 1uL of indexed PCR product to each corresponding well and mix by pipetting. 
5. Prepare a 2-fold dilution series using the 100ng/uL lambda DNA standard provided in the Quant-It kit. Standard curve should be 100, 50, 25, 12.5, 6.25, 3.125, 1.56, and 0 ng/uL. 
6. Transfer 1uL of each standard to its corresponding well. 
7. Start by measuring fluorescence on the standard plate by setting the gain to automatic (Excitation = 480nm, Emmission = 530nm). Set the gain to 80 or 85. 
8. Repeat measurement on full plate(s) if necessary. 
9. Save the measurement values. 
10. Using the standard curve values, plot a standard curve on a scatterplot in Excel, using the 16S-Library-Prep.xlsx file. Plot a trendline with equation and R-squared values. *These values are used to calculate the concentration from fluorescence.*
11. Enter fluorescent values for each plate into the corresponding plate in the 'Fluorescence' section of the 16S-Library-Prep.xlsx file. This will give volumes to pool for 400ng. Any volumes >20uL should be manually set to 20uL. 

***Using Qubit High Sensitivity Kit***
1. Count out number of tubes for each sample + 2 standards. Label each tube.
2. Add 198uL of Qubit Working solution to each tube. Add 190uL to 2 tubes for the standards.
3. Add 10uL Standard to each standard tube. 
4. Add 2uL of indexed PCR product to the corresponding tubes. Vortex and let set at room temperature for 1 minute. 
5. Power on Qubit instrument and select the dsDNA, 1X dsDNA High Sensitivity kit. 
6. Read standards, starting with standard #1. 
7. Set samples to 2uL/sample and the output in ng/uL. 
8. Read each sample and record value directly into the 'Concentration' section of the 16S-Library-Prep.xlsx file. This will give volumes to pool for 400ng. Any volumes >20uL should be manually set to 20uL. 

## Pooling

1. Using the volumes given in the 16S-Library-Prep.xlsx file, pool each sample into a sterile 2.0mL microcentrifuge tube. This is your pooled library. If your total pool volume is greater than 2.0mL, you can pool samples into a 15mL conical tube. 
