# LocalPeaksSearchMethod
  **Introduction to the Program: Matlab Version required below R2014a**
**********************************************************************************
## Program: 
   **Local-Peaks Search Method (LPS Method) - Dispersion equation solving method.**
   **for the following Models:**
* (1) Free or Fluid-loaded, Single- or Double-Layer, Elastic or Viscoelastic Plates;
* (2) Free or Fluid-loaded, Single- or Double-Layer, Elastic or Viscoelastic Cylindrical Shells.

## Developers: Jiayuan Gong,
* (1) Orginally programmed at Harbin Engineering University(HEU), hrbin, PRC, 2009;
* (2) Revised at Insititute of Acoustics, Chinese Academy of Sciences(IACAS),QingDao, PRC, 2011-2016
* (3) Modified at Hubei University of Automotive Technology(HUAT), Shiyan, PRC, 2018

## Copyright(c) 2009-2018, Jiayuan Gong, at HEU, IACAS and HUAT.

## References: 
Jiayuan Gong. Study on Leaky Lamb Waves Propagating in Elastic Plates
and Cylindrical Shells Coated with a Viscoelastic Damping Material in Water. 
Graduation Thesis of Master's Degree, Harbin Engineering University, 2010. (in Chinese)

## Notes:  
The Code for cylindrical shells has some bugs. Anyone who optimizes
the program, please share wtih the developer, thanks a lot.

## Email: rorypeck@126.com

 ## Model Scheme
* -----------------------------------------------------------------
           Fluid 1 [Fl, Va]: row1,c1
* -----------------------------------------------------------------
       Material 2 [So]: rowvm, Evm0, ytavm, sigmavm      
*  ----------------------------------------------------------------
       Material 1 [So]: rowem, Eem0, ytaem, sigmaem
*  ----------------------------------------------------------------
           Fluid 2 [Fl, Va]: row2, c2
* -----------------------------------------------------------------

## GUI interface Description
**1. Problem Selection**
* (1) Model Selection
(a) PlanarPlate; (b) CylindricalShell
* (2) BCs
Va-free or vacuum; So-solid; Fl-fluid
* (3) Mode
(a) PlanarPlate: S-symmetrical; A-asymmetrical
(b) CylindricalShell: L-longitudinal; T-tortional; F-flexural
* (4) ncs 
flexural modal order of cylindrical shells
	
**2. Model Size**
* (1) Plates
dem-thickness of material 1; dvm-thickness of material 2
* (2) Cylindrical Shells
a-inner radius; b-middle radius; c-outer radius

**3. Material Parameters**
* (1) Fluid 1
row1, c1 - acoustic parameters of fluid 1
* (2) Material 1: elastic
rowem, Eem0, ytaem, sigmaem - parameters of material 1, elastic default
* (3) Material 2: viscoelastic
rowvm, Evm0, ytavm, sigmavm - parameters of material 2, viscoelastic default
* (4) Fluid 2
row2, c2 - acoustic parameters of fluid 2

**4. Computation Parameters**
* (1)  Frequency Range 
     f = [fa:df:fb]
* (2)  Phase Velocity
     cp = [cpa:dcp:cpb]
* (3)  Attenuation Coefficient
     ki = [kia:dki:kib]
* (4)  Control Parameters
    (a) kur - used to determine a local-peak
    (b) err - roots' precision
Notes: wavenumber k = w/cp+i*ki

**5. Inialize & Save**
* (1) Initialize
     initialize the parameters using 'Initializer.mat' file saved last time
* (2) Save
     save the parameters set currently to 'Initializer.mat' file
	 
**6. Run**
  run the program
  

## Additional Notes
  When the program is running, some dialog boxes will pop-up, which is intended to 
  check the roots obtained through observation by yourself. 
* (1) Choice: to check roots manually?
    please click 'Yes' or 'No' to determine whether check roots yourself.
* (2) Check roots: Begin to check roots?
     'Yes'-check; 'No'-not check; 'Never'-not check any more
* (3) Is this a root?
     through observation to determine a root or not, press "ctrl+C" to changer the current figure
          'Yes'-is a root; 'No'-not a root; 'Cancel? not sure

