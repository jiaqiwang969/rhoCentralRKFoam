# rhoCentralFoam_RK4_LTS


- Little modification of rhoCentralFoam with RK4 schme, also LTS exits.
- Ref: [dbns-port](https://github.com/ilyapopov/dbns-port), [cfd-online](https://www.cfd-online.com/Forums/openfoam-solving/125307-rhocentralfoam-runge-kutta.html), [rhoCentralRK4Foam](https://github.com/SiboLi666/rhoCentralRK4Foam), [using CFL to speed up:relax](https://www.youtube.com/watch?v=WBWY46ynRk0)
- Acknowledge：Du Lei


# Validation: 
### 01:shockTube
- 1 parameter: rhoCentralFoam,LTS,maxCo=0.2(not correct);rhoCentralFoamRK4,LTS,maxCo=0.2; 
<img src="https://cdn.mathpix.com/snip/images/uv6PHIduDdgebNMLStAkQu-fBUtouyjb3q4DvThCW94.original.fullsize.png" width="640px">

- 2 parameter: rhoCentralFoam,LTS,maxCo=0.01(correct);rhoCentralFoamRK4,LTS,maxCo=0.2; 
<img src="https://cdn.mathpix.com/snip/images/6ZDy-py7YWsX8s5hkb7QnwCfws2WwbgiyaPfLFZyrM8.original.fullsize.png" width="640px">

which means rhoCentralFoamRK4 is more effecient in same setting!

### 02:sineWave

<img src="https://cdn.mathpix.com/snip/images/hcCMGqyc3YfDs90Ht3FBW6v4QbyMsZWPIhB3JUtoUNg.original.fullsize.png" />



# CFL Selection
- Large Eddy Simulation $(0.5-1)$
- Free Surface Flows $(<1)$
- Compressible Flows (depends on speed of sound)
- Turbomachinery $(<80)$
- Explicit Time Stepping $(<1)$.

Most often the maximum Courant number should be below 1.0.

- Suggestion: set CFL=0.3\~0.5 at first, the enlarge it to CFL=0.5\~1.7 , 1.8 is broken up



# Quesion:
- use "bounded" or "unbounded" : most "bounded" is for steady flow, [为了使求解稳定](https://www.cfd-china.com/topic/2580/openfoam%E4%B8%ADbounded%E5%92%8Cunbounded%E7%9A%84%E5%8C%BA%E5%88%AB/7)
