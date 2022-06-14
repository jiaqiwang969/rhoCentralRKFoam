# rhoCentralRK4Foam
- Original code is from https://github.com/SiboLi666/rhoCentralRK4Foam , https://www.cfd-online.com/Forums/openfoam-solving/125307-rhocentralfoam-runge-kutta.html
- Only Modify to compile with openfoam v2012

    
rhoCentralRK4Foam is derived from rhoCentralFoam by replacing its first-order time advancement scheme with a third-order, four stage Runge-Kutta scheme. The main purpose of developing this solver is to improve the scaling performance of rhoCentralFoam, especially in large-scale simulations.
