### Prioritize time difference
commit [4d11710efb249c56702a430e6fda0292015a1153](https://github.com/nep-pack/NonlinearEigenproblems.jl/commit/4d11710efb249c56702a430e6fda0292015a1153)
```diff
 ───────────────────────────────────────────────────────────────────────────────────────────────
 Test name                                                        Time               Memory
 ───────────────────────────────────────────────────────────────────────────────────────────────
-All tests                                                     244 s ( +17%)    63.5 GiB (  +3%)
-  Nonlinear Arnoldi                                          62.9 s ( +33%)    12.7 GiB ( +19%)
-  NLEIGS: Gun variant R2                                     39.3 s ( +50%)    6.75 GiB (  -0%)
+  NLEIGS: Particle variant R2                                22.0 s (  -4%)    7.09 GiB (  -6%)
   IAR Chebyshev version                                      17.0 s (  +0%)    2.93 GiB (  -0%)
     compute_y0_method for different types                    16.9 s (  +0%)    2.89 GiB (  -0%)
       DEP SHIFTED AND SCALED                                 5.58 s (  -9%)     556 MiB (  -0%)
       DEP WITH GENERIC Y0                                    4.51 s (  +1%)     514 MiB (  -0%)
       PEP in SPMF format                                     2.69 s (  +1%)     607 MiB (  -0%)
       DEP format with ComputeY0ChebSPMF_NEP                  1.72 s (  +6%)     758 MiB (  -0%)
       PEP format with ComputeY0ChebSPMF_NEP                  523 ms ( +17%)    83.0 MiB (  +0%)
       DEP WITH DELAYS>1                                      441 ms ( +13%)     155 MiB (  +0%)
       PEP SHIFTED AND SCALED                                 369 ms ( +16%)    63.1 MiB (  -0%)
-      QDEP IN SPMF format                                    336 ms ( +87%)    77.6 MiB (  +0%)
       compute_y0 AS INPUT FOR QEP (naive)                    322 ms (  +4%)    70.4 MiB (  +0%)
       PEP                                                    321 ms ( +17%)    56.4 MiB (  +0%)
       compute_y0 AS INPUT FOR QDEP (combine DEP and PEP)     110 ms ( +15%)    21.6 MiB (  +0%)
     orthogonalization                                       70.8 ms (  +8%)    20.8 MiB (  +0%)
       ModifiedGramSchmidt                                   18.7 ms (  +9%)    5.17 MiB (  +0%)
       DGKS                                                  17.6 ms (  +8%)    5.16 MiB (  +0%)
       User provided doubleGS                                17.5 ms (  +8%)    5.34 MiB (  +0%)
       ClassicalGramSchmidt                                  17.0 ms (  +7%)    5.14 MiB (  +0%)
+    Scale Cheb's to different interval w DEP                36.0 ms ( -19%)    9.12 MiB (  -8%)
     accuracy eigenpairs                                     17.0 ms (  +7%)    5.16 MiB (  +0%)
   NLEIGS: Particle variant S                                 16.2 s (  -2%)    8.40 GiB (  -0%)
   WEP                                                        13.8 s (  +0%)    8.31 GiB (  +0%)
   NLEIGS: Gun variant R1                                     10.8 s ( +13%)    1.90 GiB (  +0%)
   NLEIGS: Gun variant P                                      10.6 s ( +13%)    1.88 GiB (  -0%)
   NLEIGS: Gun variant S                                      10.5 s ( +19%)    2.23 GiB (  -0%)
   Newton iterations                                          6.57 s ( +18%)    1.36 GiB (  +0%)
     implicitdet                                              3.67 s ( +13%)     864 MiB (  +0%)
-    Resinv                                                   2.88 s ( +26%)     527 MiB (  +0%)
-    QuasiNewton                                             12.1 ms ( +92%)    1.67 MiB (  +0%)
-    Newton QR                                               4.46 ms ( +77%)    1.82 MiB (  +0%)
+    Rayleigh Function Iteration                             3.70 ms ( -35%)    1.89 MiB (  +0%)
+    Newton and AugNewton                                    1.54 ms ( -53%)     428 KiB (  +0%)
-  TIAR                                                       5.89 s ( +12%)    2.50 GiB (  +2%)
     Solve by projection                                      4.02 s (  +9%)    1.61 GiB (  -0%)
-    orthogonalization                                        1.09 s ( +18%)     544 MiB (  +7%)
-      ClassicalGramSchmidt                                   275 ms ( +19%)     136 MiB (  +7%)
-      User provided doubleGS                                 273 ms ( +20%)     136 MiB (  +7%)
-      DGKS                                                   271 ms ( +18%)     136 MiB (  +7%)
-      ModifiedGramSchmidt                                    270 ms ( +17%)     136 MiB (  +7%)
-    equivalance with IAR                                     502 ms ( +14%)     228 MiB (  +4%)
-    accuracy eigenpairs                                      273 ms ( +29%)     136 MiB (  +7%)
-  linsolvers                                                 5.57 s ( +45%)     912 MiB (  +0%)
   transformations                                            3.75 s (  +5%)     731 MiB (  +0%)
     Shift and scale                                          2.79 s (  +4%)     601 MiB (  +0%)
     Möbius transformation                                    960 ms (  +6%)     130 MiB (  -0%)
-  PeriodicDDE                                                3.51 s ( +27%)     911 MiB (  +0%)
-  Jacobi–Davidson                                            2.28 s ( +30%)     460 MiB (  +3%)
     Effenberger                                              1.70 s ( +13%)     409 MiB (  -0%)
-    Betcke-Voss                                              577 ms (+125%)    51.4 MiB ( +42%)
   compute eigvec lopcg                                       2.11 s (  +3%)     559 MiB (  -0%)
     pep0                                                     1.63 s (  +4%)     272 MiB (  +0%)
     dep0_sparse                                              475 ms (  +2%)     287 MiB (  -0%)
   Infbilanczos σ=0                                           2.05 s (  -1%)    1.42 GiB (  +0%)
+  Companion Linearization                                    1.82 s ( -46%)     248 MiB (  -0%)
   GUN (native)                                               1.63 s ( +12%)     306 MiB (  -0%)
     Running algorithm                                        1.62 s ( +12%)     297 MiB (  -0%)
     Compute derivatives                                     12.8 ms (  -2%)    9.70 MiB (  +0%)
-  Eigenvector extraction (medium/large scale)                930 ms ( +43%)     553 MiB (  -0%)
-    Test problem: pep0_sparse_003                            457 ms ( +30%)     226 MiB (  -0%)
-      backslash_linsolvercreator                             156 ms ( +36%)    76.3 MiB (  -0%)
-      default_linsolvercreator                               151 ms ( +29%)    74.7 MiB (  -0%)
-      Passing a linsolvercreator as argument                 150 ms ( +26%)    74.7 MiB (  -0%)
-    Test problem: dep0                                       241 ms ( +58%)     170 MiB (  +0%)
-      backslash_linsolvercreator                            86.5 ms ( +49%)    74.5 MiB (  +0%)
-      default_linsolvercreator                              77.3 ms ( +61%)    47.8 MiB (  +0%)
-      Passing a linsolvercreator as argument                76.7 ms ( +68%)    47.8 MiB (  +0%)
-    Test problem: pep0                                       232 ms ( +58%)     157 MiB (  +0%)
-      backslash_linsolvercreator                            84.1 ms ( +50%)    68.8 MiB (  +0%)
-      Passing a linsolvercreator as argument                74.2 ms ( +68%)    44.0 MiB (  +0%)
-      default_linsolvercreator                              73.8 ms ( +59%)    44.0 MiB (  +0%)
   NLEIGS: Scalar                                             761 ms (  -3%)     473 MiB (  +0%)
     Polynomial                                               384 ms (  -1%)     232 MiB (  +0%)
     Fully rational                                           377 ms (  -5%)     241 MiB (  +0%)
   Interpolation                                              684 ms ( +14%)     377 MiB (  -0%)
-    Random pep (original pep of degree 2)                    487 ms ( +21%)     290 MiB (  +0%)
     Random sparse pep (original pep of degree 2)             157 ms ( +12%)    68.2 MiB (  -0%)
+    Random sparse dep                                       34.6 ms ( -33%)    17.6 MiB (  +0%)
+    Random dep                                              5.72 ms ( -21%)    1.07 MiB (  +0%)
-  Gallery                                                    554 ms ( +53%)     129 MiB (  +0%)
-  Beyn contour                                               506 ms ( +79%)    27.8 MiB (  +0%)
-    disk at origin                                           260 ms ( +91%)    13.8 MiB (  +0%)
-    shifted disk                                             246 ms ( +69%)    14.0 MiB (  +0%)
   NLEIGS: NEP Types                                          486 ms (  -3%)     183 MiB (  -0%)
     Custom NEP type                                          174 ms (  -4%)     115 MiB (  +0%)
     PEP + LowRankFactorizedNEP                              78.1 ms (  -2%)    17.1 MiB (  -0%)
     PEP + SPMF                                              78.0 ms (  -2%)    17.1 MiB (  -0%)
     PEP                                                     77.9 ms (  -2%)    17.0 MiB (  -0%)
     SPMF_NEP                                                77.8 ms (  -3%)    17.0 MiB (  -0%)
+  IAR                                                        468 ms ( -25%)    65.4 MiB ( -12%)
+    orthogonalization                                        374 ms ( -31%)    52.4 MiB ( -16%)
       User provided doubleGS                                 108 ms (  -2%)    14.7 MiB (  +0%)
-      DGKS                                                  93.6 ms (  +7%)    13.0 MiB (  +4%)
+      ClassicalGramSchmidt                                  88.7 ms ( -14%)    12.5 MiB (  -7%)
+      ModifiedGramSchmidt                                   84.2 ms ( -65%)    12.2 MiB ( -43%)
-    accuracy eigenpairs                                     93.3 ms (  +9%)    12.9 MiB (  +4%)
   NLEIGS: Basic functionality                                409 ms (  -2%)    91.0 MiB (  -0%)
     Polynomial only                                         79.6 ms (  +1%)    17.0 MiB (  -0%)
     Complex-valued matrices                                 79.5 ms (  -2%)    17.5 MiB (  -0%)
     return_details                                          79.4 ms (  -3%)    17.6 MiB (  +0%)
     Complex-valued start vector                             79.3 ms (  -4%)    17.5 MiB (  -0%)
     Non-convergent linearization (return_details)           78.0 ms (  -2%)    17.1 MiB (  -0%)
     Non-convergent linearization (static)                   6.54 ms (  -9%)    2.16 MiB (  -1%)
     Non-convergent linearization                            6.48 ms (  -1%)    2.11 MiB (  -0%)
   Inner Solves                                               190 ms ( +19%)    43.7 MiB (  -0%)
   Eigenvector extraction (small scale)                      67.0 ms ( +18%)    54.8 MiB (  +0%)
     Test problem: pep0_sparse_003                           42.6 ms ( +12%)    29.5 MiB (  +0%)
       default_linsolvercreator                              14.2 ms ( +16%)    9.74 MiB (  +0%)
       backslash_linsolvercreator                            14.2 ms ( +11%)    10.0 MiB (  +0%)
       Passing a linsolvercreator as argument                14.1 ms ( +10%)    9.74 MiB (  +0%)
-    Test problem: pep0                                      24.3 ms ( +30%)    25.2 MiB (  +0%)
-      backslash_linsolvercreator                            8.62 ms ( +27%)    11.1 MiB (  +0%)
-      default_linsolvercreator                              7.90 ms ( +31%)    7.09 MiB (  +0%)
-      Passing a linsolvercreator as argument                7.77 ms ( +30%)    7.09 MiB (  +0%)
-    Test problem: dep0                                       150 μs ( +53%)     111 KiB (  +0%)
-      backslash_linsolvercreator                            51.2 μs ( +53%)    39.9 KiB (  +0%)
-      default_linsolvercreator                              49.6 μs ( +54%)    35.4 KiB (  +0%)
-      Passing a linsolvercreator as argument                49.0 μs ( +53%)    35.5 KiB (  +0%)
   Deflation (combined with MSLP)                            39.8 ms (  +7%)    17.5 MiB (  +0%)
-  blocknewton                                               34.7 ms ( +28%)    4.78 MiB (  +0%)
-  compute_types                                             15.0 ms ( +30%)    6.37 MiB (  +0%)
     PEP (BigFloat)                                          1.81 ms ( +10%)    1.35 MiB (  +0%)
     DEP (BigFloat)                                          1.77 ms (  +7%)    0.98 MiB (  +0%)
-    DEP sparse (Float64)                                    1.71 ms (+111%)     437 KiB (  +0%)
-    SPMFSumNEP (Complex{Float64})                           1.66 ms ( +74%)     402 KiB (  +0%)
-    DEP (Complex{BigFloat})                                 1.35 ms ( +49%)     874 KiB (  +0%)
     DEP (Float64)                                           1.25 ms (  -5%)     529 KiB (  +0%)
-    SPMF_NEP #4 (Complex{Float64})                          1.19 ms ( +34%)     328 KiB (  +0%)
-    SPMF_NEP #2 (Complex{Float64})                          1.08 ms ( +22%)     328 KiB (  +0%)
-    PEP (Float64)                                           1.06 ms ( +53%)     353 KiB (  +0%)
-    SPMF_NEP #1 (Float64)                                    993 μs ( +22%)     319 KiB (  +0%)
     PEP (Complex{Float32})                                   774 μs ( +19%)     322 KiB (  +0%)
     SPMF_NEP #3 (BigFloat)                                   312 μs ( +19%)     242 KiB (  +0%)
-  broyden                                                   13.0 ms ( +57%)    4.95 MiB ( +33%)
-  SPMF                                                      2.06 ms ( +27%)     939 KiB (  +0%)
-    compute_Mder_from_MM                                     865 μs ( +29%)     331 KiB (  +0%)
     compute_MM                                               421 μs (  +3%)     140 KiB (  +0%)
-    REP                                                      231 μs ( +57%)     187 KiB (  +0%)
-    Compute_Mlincomb                                         220 μs ( +26%)     106 KiB (  +0%)
-    DEP                                                      178 μs ( +58%)    87.1 KiB (  +0%)
-    PEP                                                      150 μs ( +41%)    88.0 KiB (  +0%)
-  sgiter                                                    1.96 ms ( +38%)     290 KiB (  +0%)
-  discretizepolygon                                         1.46 ms ( +25%)     633 KiB (  +0%)
     unit disk                                                878 μs ( +19%)     238 KiB (  +0%)
-    concave polygon                                          301 μs ( +23%)     281 KiB (  +0%)
-    too narrow Σ                                             174 μs ( +75%)    29.8 KiB (  +0%)
-    narrow Σ                                                56.9 μs ( +45%)    34.2 KiB (  +0%)
-    Chebyshev points                                        45.8 μs ( +22%)    50.2 KiB (  +0%)
-  MSLP                                                      1.06 ms ( +32%)     476 KiB (  +0%)
-    mslp + double                                           1.06 ms ( +32%)     476 KiB (  +0%)
-  Core                                                       426 μs ( +46%)    65.3 KiB (  +0%)
-  cached_lu_solver                                           423 μs ( +67%)     203 KiB (  +0%)
+  Serialization                                              136 μs (  +0%)    57.3 KiB ( -26%)
-  inpolygon                                                 55.4 μs ( +27%)    33.2 KiB (  +0%)
-  Types (sumnep)                                            36.6 μs ( +34%)    32.8 KiB (  +0%)
 ───────────────────────────────────────────────────────────────────────────────────────────────
```
Previous context:
```
UTC time: 2018-09-14 09:54:54
Commit: 3630cd1fadeb02a7d03f2afc38a826280b82edd4
Message: Report fewer environment variables, and add onlybench macro
Travis build: 695

Julia Version 1.0.0
Commit 5d4eaca0c9 (2018-08-08 20:58 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 14.04.5 LTS
  uname: Linux 4.4.0-101-generic #124~14.04.1-Ubuntu SMP Fri Nov 10 19:05:36 UTC 2017 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2300 MHz      49616 s          0 s      19641 s      52498 s          0 s
       #2  2300 MHz      81481 s          0 s      16352 s      24440 s          0 s
       
  Memory: 7.304546356201172 GB (4939.46875 MB free)
  Uptime: 1227.0 sec
  Load Avg:  1.48681640625  1.46240234375  1.0791015625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, haswell)
Environment:
  TRAVIS_JULIA_VERSION = 1.0
  JULIA_LOAD_PATH = @:/tmp/tmpTb8S5B
```
Current context:
```
UTC time: 2018-09-14 10:22:45
Commit: 4d11710efb249c56702a430e6fda0292015a1153
Message: Prioritize time difference
Travis build: 699

Julia Version 1.0.0
Commit 5d4eaca0c9 (2018-08-08 20:58 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 14.04.5 LTS
  uname: Linux 4.4.0-101-generic #124~14.04.1-Ubuntu SMP Fri Nov 10 19:05:36 UTC 2017 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2600 MHz      69746 s          0 s      19924 s      37484 s          0 s
       #2  2600 MHz      72681 s          0 s      17874 s      37098 s          0 s
       
  Memory: 7.304546356201172 GB (4886.9453125 MB free)
  Uptime: 1281.0 sec
  Load Avg:  1.55322265625  1.56884765625  1.17919921875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, sandybridge)
Environment:
  TRAVIS_JULIA_VERSION = 1.0
  JULIA_LOAD_PATH = @:/tmp/tmpYlcrKT
```
