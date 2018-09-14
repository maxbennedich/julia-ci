### Prioritize time difference
commit [4d11710efb249c56702a430e6fda0292015a1153](https://github.com/nep-pack/NonlinearEigenproblems.jl/commit/4d11710efb249c56702a430e6fda0292015a1153)
```diff
 ───────────────────────────────────────────────────────────────────────────────────────────────
 Test name                                                        Time               Memory
 ───────────────────────────────────────────────────────────────────────────────────────────────
-All tests                                                     248 s ( +17%)    63.5 GiB (  +3%)
-  Nonlinear Arnoldi                                          61.7 s ( +30%)    12.7 GiB ( +19%)
-  NLEIGS: Gun variant R2                                     41.0 s ( +55%)    6.75 GiB (  +0%)
+  NLEIGS: Particle variant R2                                24.1 s (  -0%)    7.09 GiB (  -6%)
   NLEIGS: Particle variant S                                 17.6 s (  +2%)    8.40 GiB (  -0%)
   IAR Chebyshev version                                      17.3 s (  -1%)    2.93 GiB (  -0%)
     compute_y0_method for different types                    17.1 s (  -1%)    2.89 GiB (  -0%)
       DEP SHIFTED AND SCALED                                 6.07 s (  -5%)     556 MiB (  -0%)
       DEP WITH GENERIC Y0                                    4.44 s (  -2%)     514 MiB (  -0%)
       PEP in SPMF format                                     2.69 s (  -1%)     607 MiB (  -0%)
       DEP format with ComputeY0ChebSPMF_NEP                  1.79 s (  +5%)     758 MiB (  -0%)
       PEP format with ComputeY0ChebSPMF_NEP                  448 ms (  -1%)    83.0 MiB (  +0%)
       DEP WITH DELAYS>1                                      390 ms (  -3%)     155 MiB (  +0%)
-      QDEP IN SPMF format                                    336 ms ( +84%)    77.6 MiB (  +0%)
       compute_y0 AS INPUT FOR QEP (naive)                    313 ms (  -0%)    70.4 MiB (  +0%)
       PEP SHIFTED AND SCALED                                 307 ms (  -3%)    63.1 MiB (  -0%)
       PEP                                                    271 ms (  -2%)    56.4 MiB (  +0%)
       compute_y0 AS INPUT FOR QDEP (combine DEP and PEP)    91.1 ms ( -13%)    21.6 MiB (  +0%)
     orthogonalization                                       64.6 ms (  -4%)    20.8 MiB (  +0%)
       User provided doubleGS                                16.4 ms (  -1%)    5.34 MiB (  +0%)
       DGKS                                                  16.3 ms (  -2%)    5.16 MiB (  +0%)
       ModifiedGramSchmidt                                   16.1 ms (  -9%)    5.17 MiB (  +0%)
       ClassicalGramSchmidt                                  15.8 ms (  -4%)    5.14 MiB (  +0%)
+    Scale Cheb's to different interval w DEP                34.7 ms ( -15%)    9.12 MiB (  -4%)
     accuracy eigenpairs                                     15.5 ms (  -3%)    5.16 MiB (  +0%)
   WEP                                                        14.7 s (  +5%)    8.31 GiB (  +0%)
   NLEIGS: Gun variant R1                                     11.5 s ( +20%)    1.90 GiB (  -0%)
   NLEIGS: Gun variant P                                      11.2 s ( +17%)    1.88 GiB (  -0%)
-  NLEIGS: Gun variant S                                      11.1 s ( +23%)    2.23 GiB (  -0%)
-  linsolvers                                                 5.82 s ( +52%)     912 MiB (  +0%)
-  TIAR                                                       5.75 s (  +7%)    2.50 GiB (  +2%)
     Solve by projection                                      4.03 s (  +7%)    1.61 GiB (  -0%)
-    orthogonalization                                        1.01 s (  +7%)     544 MiB (  +7%)
-      User provided doubleGS                                 253 ms (  +6%)     136 MiB (  +7%)
-      ClassicalGramSchmidt                                   251 ms (  +7%)     136 MiB (  +7%)
-      DGKS                                                   251 ms (  +7%)     136 MiB (  +7%)
-      ModifiedGramSchmidt                                    250 ms (  +8%)     136 MiB (  +7%)
-    equivalance with IAR                                     462 ms (  +4%)     228 MiB (  +4%)
-    accuracy eigenpairs                                      251 ms (  +7%)     136 MiB (  +7%)
   Newton iterations                                          5.32 s (  -3%)    1.36 GiB (  -0%)
     implicitdet                                              3.14 s (  -2%)     864 MiB (  +0%)
     Resinv                                                   2.17 s (  -2%)     527 MiB (  -0%)
+    QuasiNewton                                             6.31 ms ( -49%)    1.67 MiB (  +0%)
+    Rayleigh Function Iteration                             4.56 ms ( -30%)    1.89 MiB (  +0%)
     Newton QR                                               2.13 ms ( -16%)    1.82 MiB (  +0%)
+    Newton and AugNewton                                    1.50 ms ( -90%)     428 KiB (  +0%)
   transformations                                            4.04 s ( +10%)     731 MiB (  +0%)
     Shift and scale                                          3.05 s ( +10%)     601 MiB (  +0%)
     Möbius transformation                                    998 ms (  +8%)     130 MiB (  -0%)
   PeriodicDDE                                                2.67 s (  -1%)     911 MiB (  +0%)
   Infbilanczos σ=0                                           2.13 s (  +1%)    1.42 GiB (  +0%)
   compute eigvec lopcg                                       1.98 s (  -4%)     559 MiB (  -0%)
     pep0                                                     1.53 s (  -5%)     272 MiB (  +0%)
     dep0_sparse                                              452 ms (  -3%)     287 MiB (  -0%)
-  Jacobi–Davidson                                            1.90 s ( +11%)     460 MiB (  +3%)
     Effenberger                                              1.41 s (  -5%)     409 MiB (  -0%)
-    Betcke-Voss                                              498 ms (+105%)    51.4 MiB ( +42%)
+  Companion Linearization                                    1.86 s ( -44%)     248 MiB (  -0%)
   GUN (native)                                               1.70 s ( +14%)     306 MiB (  +0%)
     Running algorithm                                        1.69 s ( +14%)     297 MiB (  +0%)
     Compute derivatives                                     13.1 ms (  +1%)    9.70 MiB (  +0%)
-  Eigenvector extraction (medium/large scale)                917 ms ( +36%)     553 MiB (  -0%)
-    Test problem: pep0_sparse_003                            453 ms ( +23%)     226 MiB (  -0%)
-      default_linsolvercreator                               152 ms ( +26%)    74.7 MiB (  -0%)
-      backslash_linsolvercreator                             151 ms ( +22%)    76.3 MiB (  -0%)
-      Passing a linsolvercreator as argument                 150 ms ( +21%)    74.7 MiB (  -0%)
-    Test problem: dep0                                       236 ms ( +47%)     170 MiB (  +0%)
-      backslash_linsolvercreator                            85.8 ms ( +39%)    74.5 MiB (  +0%)
-      default_linsolvercreator                              75.8 ms ( +54%)    47.8 MiB (  +0%)
-      Passing a linsolvercreator as argument                74.6 ms ( +52%)    47.8 MiB (  +0%)
-    Test problem: pep0                                       229 ms ( +53%)     157 MiB (  +0%)
-      backslash_linsolvercreator                            83.1 ms ( +46%)    68.8 MiB (  +0%)
-      Passing a linsolvercreator as argument                72.9 ms ( +52%)    44.0 MiB (  +0%)
-      default_linsolvercreator                              72.8 ms ( +63%)    44.0 MiB (  +0%)
   NLEIGS: Scalar                                             791 ms (  -2%)     473 MiB (  -0%)
     Polynomial                                               396 ms (  -1%)     232 MiB (  -0%)
     Fully rational                                           395 ms (  -3%)     241 MiB (  +0%)
   Interpolation                                              670 ms ( +16%)     377 MiB (  +0%)
     Random pep (original pep of degree 2)                    463 ms ( +20%)     290 MiB (  +0%)
     Random sparse pep (original pep of degree 2)             159 ms ( +15%)    68.2 MiB (  +0%)
     Random sparse dep                                       45.6 ms (  -7%)    17.6 MiB (  +0%)
+    Random dep                                              3.30 ms ( -51%)    1.07 MiB (  +0%)
   NLEIGS: NEP Types                                          501 ms (  -2%)     183 MiB (  -0%)
     Custom NEP type                                          182 ms (  -2%)     115 MiB (  +0%)
     SPMF_NEP                                                80.3 ms (  -0%)    17.0 MiB (  -0%)
     PEP                                                     80.1 ms (  -1%)    17.0 MiB (  -0%)
     PEP + SPMF                                              79.8 ms (  -2%)    17.1 MiB (  -0%)
     PEP + LowRankFactorizedNEP                              79.1 ms (  -4%)    17.1 MiB (  -0%)
+  IAR                                                        439 ms ( -31%)    65.4 MiB ( -12%)
+    orthogonalization                                        352 ms ( -36%)    52.4 MiB ( -16%)
       User provided doubleGS                                 101 ms (  -8%)    14.7 MiB (  +0%)
-      DGKS                                                  88.2 ms (  +1%)    13.0 MiB (  +4%)
+      ClassicalGramSchmidt                                  84.7 ms ( -15%)    12.5 MiB (  -7%)
+      ModifiedGramSchmidt                                   78.1 ms ( -69%)    12.2 MiB ( -43%)
-    accuracy eigenpairs                                     87.1 ms (  -0%)    12.9 MiB (  +4%)
   NLEIGS: Basic functionality                                437 ms (  +4%)    91.1 MiB (  -0%)
     return_details                                          89.2 ms (  +8%)    17.6 MiB (  +0%)
     Complex-valued start vector                             88.8 ms (  +8%)    17.5 MiB (  -0%)
     Complex-valued matrices                                 84.3 ms (  +5%)    17.5 MiB (  -0%)
     Polynomial only                                         81.5 ms (  +1%)    17.0 MiB (  -0%)
     Non-convergent linearization (return_details)           80.3 ms (  -1%)    17.1 MiB (  -0%)
     Non-convergent linearization (static)                   6.52 ms (  -2%)    2.17 MiB (  -0%)
     Non-convergent linearization                            6.31 ms (  -3%)    2.11 MiB (  -0%)
   Gallery                                                    406 ms (  +5%)     129 MiB (  +0%)
+  Beyn contour                                               225 ms ( -22%)    27.8 MiB (  +0%)
     shifted disk                                             129 ms ( +11%)    14.0 MiB (  +0%)
+    disk at origin                                          95.3 ms ( -44%)    13.8 MiB (  +0%)
   Inner Solves                                               144 ms (  -8%)    43.7 MiB (  -0%)
   Eigenvector extraction (small scale)                      66.3 ms ( +15%)    54.8 MiB (  +0%)
     Test problem: pep0_sparse_003                           41.5 ms (  +8%)    29.5 MiB (  +0%)
       Passing a linsolvercreator as argument                14.1 ms (  +8%)    9.74 MiB (  +0%)
       backslash_linsolvercreator                            13.8 ms (  +8%)    10.0 MiB (  +0%)
       default_linsolvercreator                              13.5 ms (  +7%)    9.74 MiB (  +0%)
-    Test problem: pep0                                      24.7 ms ( +31%)    25.2 MiB (  +0%)
-      backslash_linsolvercreator                            9.23 ms ( +28%)    11.1 MiB (  +0%)
-      Passing a linsolvercreator as argument                7.74 ms ( +31%)    7.09 MiB (  +0%)
-      default_linsolvercreator                              7.71 ms ( +34%)    7.09 MiB (  +0%)
     Test problem: dep0                                      98.3 μs (  +0%)     111 KiB (  +0%)
       backslash_linsolvercreator                            33.5 μs (  +0%)    39.9 KiB (  +0%)
       Passing a linsolvercreator as argument                32.4 μs (  +0%)    35.5 KiB (  +0%)
       default_linsolvercreator                              32.3 μs (  +0%)    35.4 KiB (  +0%)
   Deflation (combined with MSLP)                            36.1 ms (  +3%)    17.5 MiB (  +0%)
-  blocknewton                                               26.9 ms ( +39%)    4.78 MiB (  +0%)
   compute_types                                             11.9 ms (  -2%)    6.37 MiB (  +0%)
     PEP (BigFloat)                                          1.89 ms (  -6%)    1.35 MiB (  +0%)
     DEP (BigFloat)                                          1.58 ms (  -8%)    0.98 MiB (  +0%)
     DEP (Float64)                                           1.34 ms (  +5%)     529 KiB (  +0%)
-    SPMFSumNEP (Complex{Float64})                           1.31 ms ( +30%)     402 KiB (  +0%)
     DEP (Complex{BigFloat})                                 1.13 ms ( -17%)     874 KiB (  +0%)
-    PEP (Complex{Float32})                                   861 μs ( +35%)     322 KiB (  +0%)
     DEP sparse (Float64)                                     783 μs (  -2%)     437 KiB (  +0%)
     SPMF_NEP #4 (Complex{Float64})                           779 μs ( +12%)     328 KiB (  +0%)
     SPMF_NEP #2 (Complex{Float64})                           728 μs ( +14%)     328 KiB (  +0%)
+    PEP (Float64)                                            660 μs ( -29%)     353 KiB (  +0%)
+    SPMF_NEP #1 (Float64)                                    606 μs ( -27%)     319 KiB (  +0%)
     SPMF_NEP #3 (BigFloat)                                   260 μs (  +1%)     242 KiB (  +0%)
-  broyden                                                   10.3 ms ( +21%)    4.95 MiB ( +33%)
   SPMF                                                      1.61 ms (  -3%)     939 KiB (  +0%)
     compute_Mder_from_MM                                     720 μs (  +5%)     331 KiB (  +0%)
+    compute_MM                                               322 μs ( -24%)     140 KiB (  +0%)
     Compute_Mlincomb                                         174 μs (  -4%)     106 KiB (  +0%)
     REP                                                      167 μs ( +14%)     187 KiB (  +0%)
     DEP                                                      118 μs (  +1%)    87.1 KiB (  +0%)
     PEP                                                      107 μs (  -0%)    88.0 KiB (  +0%)
   sgiter                                                    1.47 ms (  -3%)     290 KiB (  +0%)
   discretizepolygon                                         1.13 ms (  -3%)     633 KiB (  +0%)
     unit disk                                                704 μs (  -5%)     238 KiB (  +0%)
     concave polygon                                          250 μs (  +1%)     281 KiB (  +0%)
     too narrow Σ                                             101 μs (  +1%)    29.8 KiB (  +0%)
     narrow Σ                                                40.7 μs (  +4%)    34.2 KiB (  +0%)
     Chebyshev points                                        38.0 μs (  +5%)    50.2 KiB (  +0%)
   MSLP                                                       789 μs (  +1%)     476 KiB (  +0%)
     mslp + double                                            789 μs (  +1%)     476 KiB (  +0%)
   Core                                                       325 μs ( +15%)    65.3 KiB (  +0%)
+  cached_lu_solver                                           253 μs ( -28%)     203 KiB (  +0%)
   Serialization                                              135 μs (  +0%)    77.8 KiB (  +0%)
   inpolygon                                                 44.3 μs (  +3%)    33.2 KiB (  +0%)
   Types (sumnep)                                            27.4 μs (  +3%)    32.8 KiB (  +0%)
 ───────────────────────────────────────────────────────────────────────────────────────────────
```
Previous context:
```
UTC time: 2018-09-14 10:45:15
Commit: 4d11710efb249c56702a430e6fda0292015a1153
Message: Prioritize time difference
Travis build: 699

Julia Version 1.0.0
Commit 5d4eaca0c9 (2018-08-08 20:58 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 14.04.5 LTS
  uname: Linux 4.4.0-101-generic #124~14.04.1-Ubuntu SMP Fri Nov 10 19:05:36 UTC 2017 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2300 MHz      75173 s          0 s      17853 s      32696 s          0 s
       #2  2300 MHz      58708 s          0 s      18152 s      48759 s          0 s
       
  Memory: 7.304546356201172 GB (4905.6171875 MB free)
  Uptime: 1264.0 sec
  Load Avg:  1.55126953125  1.47998046875  1.1103515625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, haswell)
Environment:
  TRAVIS_JULIA_VERSION = 1.0
  JULIA_LOAD_PATH = @:/tmp/tmpjPGh2v
```
Current context:
```
UTC time: 2018-09-14 11:09:51
Commit: 4d11710efb249c56702a430e6fda0292015a1153
Message: Prioritize time difference
Travis build: 699

Julia Version 1.0.0
Commit 5d4eaca0c9 (2018-08-08 20:58 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 14.04.5 LTS
  uname: Linux 4.4.0-101-generic #124~14.04.1-Ubuntu SMP Fri Nov 10 19:05:36 UTC 2017 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU @ 2.50GHz: 
              speed         user         nice          sys         idle          irq
       #1  2500 MHz      61104 s          0 s      20771 s      47444 s          0 s
       #2  2500 MHz      84762 s          0 s      15640 s      29393 s          0 s
       
  Memory: 7.304546356201172 GB (4936.01953125 MB free)
  Uptime: 1300.0 sec
  Load Avg:  1.66259765625  1.64599609375  1.21728515625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, ivybridge)
Environment:
  TRAVIS_JULIA_VERSION = 1.0
  JULIA_LOAD_PATH = @:/tmp/tmpaDKkyM
```
