CitcomS_SC is built upon CitcomS (Zhong et al., 2008), contributed by Jiaxin Zhang. According to CitcomS manual, CitcomS is a parallel finite element code written in C that solves thermochemical convection problems related to Earth's mantle. This version (CitcomS_SC) of the code enables the code to solve such problems that incorporate secular cooling of the mantle. Specifically, it can solve problems with time-dependent bottom boundary temperature condition and internal heating rate. For the time-dependent bottom boundary temperature condition, it can solve both prescribed temperature profiles or the bottom temperature boundary condition that is self-consistent with the heat flow across the core-mantle boundary (CMB), based on a simplified core energy balance relation. For the time-dependent internal heating rate, the internal heating rate is computed based on radiogenic heat decay in the mantle.

To install this package:
1. Decompress the zip file.
2. Under citcoms_tq2/src, run:
   $ make distclean
3. Under the same folder, run:
   $ ./configure
4. Under the same folder, run:
   $ make
5. Running the above commands will generate two executables (CitcomSFull and CitcomSRegional) under folder citcoms_tq2/src/bin, just as the original public version of CitcomS.
6. To run the program, call the executables using mpirun.

Updates compared to the published CitcomS:

For the use of CitcomS in general, please refer to CitcomS manual ("citcoms-manual.pdf",downloaded from CIG website: geodynamics.org) included in the root directory.
An example input file ("ccg16.input") is provided under the root directory.

The variable to enable CitcomS to read time-dependent CMB temperature from a prescribed file is "file_tcmb" (1 to switch on). The path of the temperature file can be entered to parameter "tempcmbfile".

The parameter to enable CitcomS to read time-dependent internal heating rate from a prescribed file is "file_Qt" (1 to switch on). The path of the internal heating rate file can be entered to parameter "Qtfile".

The parameter to turn on self-consistent CMB temperature is "self_consistent_tcmb" (1 to switch on). The rate of the secular cooling is controlled by c_efective, which is the effective heat capacity of the Earth's core.

Reference
Zhong, S., McNamara, A., Tan, E., Moresi, L., & Gurnis, M. (2008). A benchmark study on mantle convection in a 3‐D spherical shell using CitcomS. Geochemistry, Geophysics, Geosys-tems, 9(10). https://doi.org/10.1029/2008gc002048 <img width="468" height="81" alt="image" src="https://github.com/user-attachments/assets/e784be36-2542-43b3-9c41-0e53eccdb866" />
