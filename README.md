# Olivine-Orthopyroxene-Spinel geothermo-oxybarometer V15

Welcome! This project uses the olivine-spinel geothermometer (Jianping et al., 1995) and olivine-orthopyroxene-spinel geo-oxybarometer (Sack and Ghiorso, 1991a,b; Wood, 1990). The calculators in the Jupyter notebook are built upon the ThermoEngine package from the ENKI project.


To use the geothermo-barometer app, click the 'launch binder' tab near the bottom of this file, which will take you to repository interface. If you use the results derived from this app in publications, please cite it using the DOI badge indicated.


The olivine-spinel geothermometer is used to calculate the temperature, the pressure of formation is inputted by the user, and the oxygen fugacity is calculated using the Olivine-Orthopyroxene-Spinel geo-oxybarometer.

The equations used in this notebook include:

Olivine-Spinel geothermometer (Jianping et al., 1995)

T°K=((4250×Y_Cr^Spl )+1343)/((ln_Kd^0)+(1.825×Y_Cr^Spl)+0.571) (Eq. 10)

  Where:
  
      T°K = Temperature in Kelvin
    
      Y_Cr^Spl = mole fraction of Cr in spinel [Cr/Cr+Al+Fe^3+]

      ln_Kd^0 = ln_Kd - 2(Y_Fe3+^Spl) (Eq. 9)

        Where: 
    
          ln_Kd = ln(((X_Mg^Ol)(X_Fe^Spl))/((X_Fe^Ol)(X_Mg^Spl))) (Eq. 2 from Fabries, 1979)
    
          X_Mg^Ol = mole fraction of Mg in olivine [Mg/Mg+Fe]
    
          X_Fe^Ol = mole fraction of Fe in olivine [Fe/Mg+Fe]
 
          X_Mg^Spl = mole fraction of Mg in spinel [Mg/Mg+Fe]
 
          X_Fe^Spl = mole fraction of Fe in spinel [Fe/Mg+Fe]
 
          Y_Fe3+^Spl = mole fraction of Fe3+ in spinel [Fe3+/Cr+Al+Fe3+]
    
    
    
Olivine-Orthopyroxene-Spinel oxybarometer (Wood, 1990)
    
log⁡(fO2)=[log⁡fO2 (QFM)_(P,T)+220/T+0.35-0.0369P/T] - [12(log⁡(X_Fe^Ol))-(2620/T)((X_Mg^Ol)^2)] + [3(log⁡(X_Fe^M1*X_Fe^M2 )^opx]+ [2(log(a_Fe3O4^spl))]

  Where: 
  
    P = pressure in bars --> inputted by the user
    
    log⁡(fO2)= -2441.9/T°K+8.29
    
    [12(log⁡(X_Fe^Ol))-(2620/T)((X_Mg^Ol)^2)] --> X_Mg^Ol = mole fraction of forsterite, and  X_Fe^Ol = mole fraction of fayalite
    
    [3(log⁡(X_Fe^M1*X_Fe^M2 )^opx] 
      where... after the code calculates the individual cation values, including Al(IV), Al(VI), Cr, and Ti are placed into the M1 position of the opx formula, while   Ca and Mn cations are placed in M2. After this, Fe and Mg cations are evenly distributed between the M1 and M2 postions, and thus X_Fe^M1 and X_Fe^M2 can be calculated, where they represent the atomic fractions of Fe in the M1 and M2 positions.
    
    [2(log(a_Fe3O4^spl))]
      where... a_Fe3O4^spl represents the activity of magnetite in spinel, which is calculated using the quinary model for cubic oxides from Sack and Ghioso (1991a, b)
    
[![Binder](https://mybinder.org/badge_logo.svg)]((https://hub.gke2.mybinder.org/user/sophiebena-oos14-izezqvqk/notebooks/Ol-Opx-SplV4.ipynb))
