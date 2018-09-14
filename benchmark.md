### Prioritize time difference
commit [4d11710efb249c56702a430e6fda0292015a1153](https://github.com/nep-pack/NonlinearEigenproblems.jl/commit/4d11710efb249c56702a430e6fda0292015a1153)
```diff
 ───────────────────────────────────────────────────────────────────────────────────────────────
 Test name                                                        Time               Memory
 ───────────────────────────────────────────────────────────────────────────────────────────────
 All tests                                                     243 s (  -2%)    63.5 GiB (  +0%)
   Nonlinear Arnoldi                                          60.3 s (  -2%)    12.7 GiB (  +0%)
   NLEIGS: Gun variant R2                                     40.1 s (  -2%)    6.75 GiB (  -0%)
   NLEIGS: Particle variant R2                                23.3 s (  -3%)    7.09 GiB (  +0%)
   NLEIGS: Particle variant S                                 17.1 s (  -3%)    8.40 GiB (  +0%)
   IAR Chebyshev version                                      16.9 s (  -2%)    2.93 GiB (  +0%)
     compute_y0_method for different types                    16.8 s (  -2%)    2.89 GiB (  +0%)
       DEP SHIFTED AND SCALED                                 6.06 s (  -0%)     556 MiB (  +0%)
       DEP WITH GENERIC Y0                                    4.23 s (  -5%)     514 MiB (  +0%)
       PEP in SPMF format                                     2.56 s (  -5%)     607 MiB (  +0%)
       DEP format with ComputeY0ChebSPMF_NEP                  1.78 s (  -1%)     758 MiB (  +0%)
       PEP format with ComputeY0ChebSPMF_NEP                  461 ms (  +3%)    83.0 MiB (  +0%)
       DEP WITH DELAYS>1                                      408 ms (  +4%)     155 MiB (  +0%)
       QDEP IN SPMF format                                    337 ms (  +0%)    77.6 MiB (  +0%)
       PEP SHIFTED AND SCALED                                 324 ms (  +6%)    63.1 MiB (  +0%)
       compute_y0 AS INPUT FOR QEP (naive)                    296 ms (  -5%)    70.4 MiB (  +0%)
       PEP                                                    283 ms (  +4%)    56.4 MiB (  +0%)
       compute_y0 AS INPUT FOR QDEP (combine DEP and PEP)    90.3 ms (  -1%)    21.6 MiB (  +0%)
     orthogonalization                                       65.0 ms (  +1%)    20.8 MiB (  +0%)
       ModifiedGramSchmidt                                   17.2 ms (  +6%)    5.17 MiB (  +0%)
       DGKS                                                  16.3 ms (  +0%)    5.16 MiB (  +0%)
       User provided doubleGS                                16.2 ms (  -1%)    5.34 MiB (  +0%)
       ClassicalGramSchmidt                                  15.3 ms (  -3%)    5.14 MiB (  +0%)
     Scale Cheb's to different interval w DEP                34.5 ms (  -1%)    9.12 MiB (  +0%)
     accuracy eigenpairs                                     16.0 ms (  +3%)    5.16 MiB (  +0%)
   WEP                                                        14.3 s (  -2%)    8.31 GiB (  +0%)
   NLEIGS: Gun variant R1                                     11.2 s (  -2%)    1.90 GiB (  +0%)
   NLEIGS: Gun variant P                                      11.0 s (  -2%)    1.88 GiB (  +0%)
   NLEIGS: Gun variant S                                      10.9 s (  -2%)    2.23 GiB (  +0%)
   linsolvers                                                 5.79 s (  -1%)     912 MiB (  +0%)
   TIAR                                                       5.69 s (  -1%)    2.50 GiB (  +0%)
     Solve by projection                                      3.93 s (  -2%)    1.61 GiB (  +0%)
     orthogonalization                                        1.03 s (  +2%)     544 MiB (  +0%)
       ClassicalGramSchmidt                                   259 ms (  +3%)     136 MiB (  +0%)
       ModifiedGramSchmidt                                    258 ms (  +3%)     136 MiB (  +0%)
       User provided doubleGS                                 257 ms (  +2%)     136 MiB (  +0%)
       DGKS                                                   256 ms (  +2%)     136 MiB (  +0%)
     equivalance with IAR                                     474 ms (  +3%)     228 MiB (  +0%)
     accuracy eigenpairs                                      255 ms (  +2%)     136 MiB (  +0%)
   Newton iterations                                          5.35 s (  +1%)    1.36 GiB (  +0%)
     implicitdet                                              3.16 s (  +1%)     864 MiB (  +0%)
     Resinv                                                   2.18 s (  +0%)     527 MiB (  +0%)
-    QuasiNewton                                             7.95 ms ( +26%)    1.67 MiB (  +0%)
+    Rayleigh Function Iteration                             3.23 ms ( -29%)    1.89 MiB (  +0%)
-    Newton QR                                               3.08 ms ( +44%)    1.82 MiB (  +0%)
     Newton and AugNewton                                    1.50 ms (  +0%)     428 KiB (  +0%)
   transformations                                            3.90 s (  -4%)     731 MiB (  +0%)
     Shift and scale                                          2.94 s (  -4%)     601 MiB (  +0%)
     Möbius transformation                                    962 ms (  -4%)     130 MiB (  +0%)
   PeriodicDDE                                                2.67 s (  +0%)     911 MiB (  +0%)
   Infbilanczos σ=0                                           2.12 s (  -1%)    1.42 GiB (  -0%)
   Jacobi–Davidson                                            1.96 s (  +3%)     460 MiB (  -0%)
     Effenberger                                              1.43 s (  +2%)     409 MiB (  -0%)
     Betcke-Voss                                              525 ms (  +5%)    51.4 MiB (  +0%)
   compute eigvec lopcg                                       1.90 s (  -4%)     559 MiB (  +0%)
     pep0                                                     1.45 s (  -5%)     272 MiB (  +0%)
     dep0_sparse                                              448 ms (  -1%)     287 MiB (  +0%)
   Companion Linearization                                    1.85 s (  -1%)     248 MiB (  +0%)
   GUN (native)                                               1.69 s (  -1%)     306 MiB (  +0%)
     Running algorithm                                        1.68 s (  -1%)     297 MiB (  +0%)
     Compute derivatives                                     12.5 ms (  -5%)    9.70 MiB (  +0%)
   Eigenvector extraction (medium/large scale)                913 ms (  -0%)     553 MiB (  +0%)
     Test problem: pep0_sparse_003                            447 ms (  -1%)     226 MiB (  +0%)
       backslash_linsolvercreator                             152 ms (  +1%)    76.3 MiB (  +0%)
       default_linsolvercreator                               149 ms (  -2%)    74.7 MiB (  +0%)
       Passing a linsolvercreator as argument                 146 ms (  -3%)    74.7 MiB (  +0%)
     Test problem: dep0                                       236 ms (  -0%)     170 MiB (  +0%)
       backslash_linsolvercreator                            86.5 ms (  +1%)    74.5 MiB (  +0%)
       Passing a linsolvercreator as argument                75.1 ms (  +1%)    47.8 MiB (  +0%)
       default_linsolvercreator                              74.5 ms (  -2%)    47.8 MiB (  +0%)
     Test problem: pep0                                       230 ms (  +0%)     157 MiB (  +0%)
       backslash_linsolvercreator                            83.5 ms (  +1%)    68.8 MiB (  +0%)
       default_linsolvercreator                              73.4 ms (  +1%)    44.0 MiB (  +0%)
       Passing a linsolvercreator as argument                72.9 ms (  +0%)    44.0 MiB (  +0%)
   NLEIGS: Scalar                                             780 ms (  -1%)     473 MiB (  +0%)
     Polynomial                                               390 ms (  -2%)     232 MiB (  +0%)
     Fully rational                                           390 ms (  -1%)     241 MiB (  -0%)
   Interpolation                                              653 ms (  -2%)     377 MiB (  +0%)
     Random pep (original pep of degree 2)                    453 ms (  -2%)     290 MiB (  +0%)
     Random sparse pep (original pep of degree 2)             153 ms (  -4%)    68.2 MiB (  +0%)
     Random sparse dep                                       44.9 ms (  -2%)    17.6 MiB (  +0%)
     Random dep                                              2.72 ms ( -18%)    1.07 MiB (  +0%)
   NLEIGS: NEP Types                                          502 ms (  +0%)     183 MiB (  +0%)
     Custom NEP type                                          183 ms (  +1%)     115 MiB (  +0%)
     PEP + LowRankFactorizedNEP                              80.3 ms (  +1%)    17.1 MiB (  +0%)
     SPMF_NEP                                                79.9 ms (  -1%)    17.0 MiB (  +0%)
     PEP + SPMF                                              79.3 ms (  -1%)    17.1 MiB (  +0%)
     PEP                                                     79.1 ms (  -1%)    17.0 MiB (  +0%)
   IAR                                                        439 ms (  +0%)    65.4 MiB (  +0%)
     orthogonalization                                        352 ms (  +0%)    52.4 MiB (  +0%)
       User provided doubleGS                                 104 ms (  +3%)    14.7 MiB (  +0%)
       DGKS                                                  88.1 ms (  -0%)    13.0 MiB (  +0%)
       ClassicalGramSchmidt                                  82.3 ms (  -3%)    12.5 MiB (  +0%)
       ModifiedGramSchmidt                                   78.3 ms (  +0%)    12.2 MiB (  +0%)
     accuracy eigenpairs                                     87.0 ms (  -0%)    12.9 MiB (  +0%)
   NLEIGS: Basic functionality                                416 ms (  -5%)    91.1 MiB (  +0%)
     return_details                                          82.2 ms (  -8%)    17.6 MiB (  +0%)
     Complex-valued matrices                                 81.4 ms (  -3%)    17.5 MiB (  +0%)
     Complex-valued start vector                             80.6 ms (  -9%)    17.5 MiB (  +0%)
     Polynomial only                                         79.1 ms (  -3%)    17.0 MiB (  +0%)
     Non-convergent linearization (return_details)           79.1 ms (  -2%)    17.1 MiB (  +0%)
     Non-convergent linearization                            6.57 ms (  +4%)    2.11 MiB (  +0%)
     Non-convergent linearization (static)                   6.50 ms (  -0%)    2.17 MiB (  +0%)
   Gallery                                                    378 ms (  -7%)     129 MiB (  +0%)
   Inner Solves                                               155 ms (  +7%)    43.7 MiB (  +0%)
+  Beyn contour                                               118 ms ( -47%)    27.8 MiB (  +0%)
+    disk at origin                                          59.5 ms ( -38%)    13.8 MiB (  +0%)
+    shifted disk                                            58.7 ms ( -55%)    14.0 MiB (  +0%)
   Eigenvector extraction (small scale)                      64.1 ms (  -3%)    54.8 MiB (  +0%)
     Test problem: pep0_sparse_003                           40.1 ms (  -3%)    29.5 MiB (  +0%)
       backslash_linsolvercreator                            13.6 ms (  -2%)    10.0 MiB (  +0%)
       default_linsolvercreator                              13.5 ms (  -0%)    9.74 MiB (  +0%)
       Passing a linsolvercreator as argument                13.0 ms (  -8%)    9.74 MiB (  +0%)
     Test problem: pep0                                      23.9 ms (  -3%)    25.2 MiB (  +0%)
       backslash_linsolvercreator                            8.57 ms (  -7%)    11.1 MiB (  +0%)
       Passing a linsolvercreator as argument                7.70 ms (  -0%)    7.09 MiB (  +0%)
       default_linsolvercreator                              7.60 ms (  -1%)    7.09 MiB (  +0%)
     Test problem: dep0                                      97.5 μs (  -1%)     111 KiB (  +0%)
       backslash_linsolvercreator                            33.4 μs (  -0%)    39.9 KiB (  +0%)
       Passing a linsolvercreator as argument                32.3 μs (  -0%)    35.5 KiB (  +0%)
       default_linsolvercreator                              31.9 μs (  -1%)    35.4 KiB (  +0%)
   Deflation (combined with MSLP)                            35.6 ms (  -1%)    17.5 MiB (  +0%)
   blocknewton                                               23.4 ms ( -13%)    4.78 MiB (  +0%)
   compute_types                                             10.7 ms ( -11%)    6.37 MiB (  +0%)
     PEP (BigFloat)                                          1.58 ms ( -17%)    1.35 MiB (  +0%)
     DEP (BigFloat)                                          1.45 ms (  -8%)    0.98 MiB (  +0%)
     DEP (Complex{BigFloat})                                 1.17 ms (  +4%)     874 KiB (  +0%)
+    DEP (Float64)                                           1.01 ms ( -25%)     529 KiB (  +0%)
+    SPMFSumNEP (Complex{Float64})                            931 μs ( -29%)     402 KiB (  +0%)
     DEP sparse (Float64)                                     847 μs (  +8%)     437 KiB (  +0%)
-    SPMF_NEP #1 (Float64)                                    803 μs ( +32%)     319 KiB (  +0%)
     SPMF_NEP #2 (Complex{Float64})                           672 μs (  -8%)     328 KiB (  +0%)
     SPMF_NEP #4 (Complex{Float64})                           668 μs ( -14%)     328 KiB (  +0%)
     PEP (Float64)                                            648 μs (  -2%)     353 KiB (  +0%)
+    PEP (Complex{Float32})                                   623 μs ( -28%)     322 KiB (  +0%)
     SPMF_NEP #3 (BigFloat)                                   266 μs (  +2%)     242 KiB (  +0%)
   broyden                                                   10.3 ms (  +1%)    4.95 MiB (  +0%)
   SPMF                                                      1.58 ms (  -2%)     939 KiB (  +0%)
     compute_Mder_from_MM                                     599 μs ( -17%)     331 KiB (  +0%)
-    compute_MM                                               414 μs ( +29%)     140 KiB (  +0%)
     Compute_Mlincomb                                         178 μs (  +2%)     106 KiB (  +0%)
     REP                                                      167 μs (  -0%)     187 KiB (  +0%)
     DEP                                                      115 μs (  -3%)    87.1 KiB (  +0%)
     PEP                                                      106 μs (  -1%)    88.0 KiB (  +0%)
   sgiter                                                    1.47 ms (  +0%)     290 KiB (  +0%)
   discretizepolygon                                         1.14 ms (  +1%)     633 KiB (  +0%)
     unit disk                                                702 μs (  -0%)     238 KiB (  +0%)
     concave polygon                                          254 μs (  +2%)     281 KiB (  +0%)
     too narrow Σ                                             107 μs (  +5%)    29.8 KiB (  +0%)
     narrow Σ                                                40.5 μs (  -0%)    34.2 KiB (  +0%)
     Chebyshev points                                        38.3 μs (  +1%)    50.2 KiB (  +0%)
   MSLP                                                       777 μs (  -2%)     476 KiB (  +0%)
     mslp + double                                            777 μs (  -2%)     476 KiB (  +0%)
   Core                                                       353 μs (  +8%)    65.3 KiB (  +0%)
-  cached_lu_solver                                           351 μs ( +39%)     203 KiB (  +0%)
-  Serialization                                              151 μs ( +12%)    82.7 KiB (  +6%)
   inpolygon                                                 43.9 μs (  -1%)    33.2 KiB (  +0%)
   Types (sumnep)                                            27.5 μs (  +0%)    32.8 KiB (  +0%)
 ───────────────────────────────────────────────────────────────────────────────────────────────
```
Previous context:
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
Current context:
```
UTC time: 2018-09-14 11:57:56
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
       #1  2600 MHz      75308 s          0 s      17622 s      34253 s          0 s
       #2  2600 MHz      67579 s          0 s      18022 s      41538 s          0 s
       
  Memory: 7.304546356201172 GB (4830.3203125 MB free)
  Uptime: 1278.0 sec
  Load Avg:  1.5048828125  1.54296875  1.15185546875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, sandybridge)
Environment:
  TRAVIS_JULIA_VERSION = 1.0
  JULIA_LOAD_PATH = @:/tmp/tmpn1j26m
```
