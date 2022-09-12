## Spatial temporal simulation for early pancreatic development
These codes are for investigating the cell fate segregation during the early pancreatic development from the mathematical model perspective.
Dynamics of gene expression in hundreds of cells in a three-dimensional cell-cell interacting structure are simulated simultaneously. 
Visualization and statistic analysis of cell fate segregation are performed based on the simulated gene expression.
The codes are written with MATLAB (R2019a, 64-bit) and delay differential equations solver (dde23) is required.
## Functions and capabilities
### Construct a three-dimensional interaction structure with a given number of cells
`Main_0_Construct_3D_structure.m`

This script adapts method in Silas Boye Nissen, et al (2018) to asign locations of a given number of cells in a three-dimensional structure.
Given a number of cells (400 is used), the same number of particles starting from random locations ([x, y, z]) move around based on the repulsive 
and attractive forces acting between them. The interactions between particles depend on distances are updated at each iteration step. With enough iteration steps, the particles do not move anymore. Then the final locations of the particles are
regarded as the centers for the cells. 

Meanwhile, the cells are divided into two groups, mesenchymal cells and epithelial cells. Mesenchymal cells are cells
belonging to convex hull and their numbers in the spatial structure. The other cells surrounded by mesenchymal cells are epithelial cells.
The final interactions between particles indicate cell-cell interactions in the following simulations.

### Simulate cell differentiation with the two-cell system 
`Main_1_Fig2_SuppFig2.m`

The script is for results presented in Figure 2 and Supplementary Figure 2: Use the simple two-cell system to study the role of 
cell-cell communication in cell fate segregation. With this two-cell model, we simulate cells with: 1. Different strengths of *cis*-interaction and *trans*-interaction;
2. Deficiency of Dll1 or Jag1; 3. Delay in Dll1 transcription.

### Simulate different conditions with multi-cell organ model 
`Main_2_Multi_cell_organ_simulations.m`
 
 Pancreatic development in e10.0 ~ e12.5 is simulated within different mutants and treatments by changing corresponding parameters. 
 The simulated gene expression is saved for following analysis.
 
`Main_3_Fig3_4_5_SuppFigs_Dynamics_on_3D.m`
Results of analysis are mainly presented in Figure 3–5 and Supplementary Figure 4–5.
 1) Visualization and statistic plots of pancreatic phenotypes in wildtype, Dll1 deficient, Jag1 deficient, DAPT, MLN4927
 2) Simulate time delay in Dll1 transcription with the multi-cell model
 3) Compare dynamics with removing *cis*- or *trans*- interaction of Dll1 and Jag1 

### Compare dynamics with different time scales of Ptf1a
`Main_4_SuppFig6_slow_fast_Ptf1a.m`

This script is for the discussion about how time scale of Ptf1a determines the timing of cell fate segregation. 
Results are presented in Supplementary Figure 6.
 
### Analyze sensitivity of parameters with the two-cell model
`Main_5_SuppFig7_8_sensitivity_analysis.m`
 1) Analyze cell fate segregation with two-cell model by changing each parameter from 1% to 200% 
 2) Analyze period of oscillation with two-cell model by changing each parameter from 1% to 200%

### Make movies of wildtype, Dll1 deficient, Jag1 deficient, DAPT, MLN4927
`Main_6_Supp_Movies.m`

Supplementary movies are made with simulated gene expression under different conditions.

## LICENSE
This project is under **MIT License**.
