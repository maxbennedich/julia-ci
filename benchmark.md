### Prioritize time difference
commit [4d11710efb249c56702a430e6fda0292015a1153](https://github.com/nep-pack/NonlinearEigenproblems.jl/commit/4d11710efb249c56702a430e6fda0292015a1153)
```diff
 ───────────────────────────────────────────────────────────────────────────────────────────────
 Test name                                                        Time               Memory
 ───────────────────────────────────────────────────────────────────────────────────────────────
+All tests                                                     211 s ( -13%)    61.8 GiB (  -3%)
+  Nonlinear Arnoldi                                          47.3 s ( -25%)    10.7 GiB ( -16%)
+  NLEIGS: Gun variant R2                                     26.5 s ( -33%)    6.75 GiB (  -0%)
-  NLEIGS: Particle variant R2                                24.2 s ( +10%)    7.51 GiB (  +6%)
   IAR Chebyshev version                                      17.5 s (  +3%)    2.93 GiB (  +0%)
     compute_y0_method for different types                    17.4 s (  +3%)    2.89 GiB (  +0%)
       DEP SHIFTED AND SCALED                                 6.36 s ( +14%)     556 MiB (  +0%)
       DEP WITH GENERIC Y0                                    4.55 s (  +1%)     514 MiB (  +0%)
       PEP in SPMF format                                     2.72 s (  +1%)     607 MiB (  +0%)
       DEP format with ComputeY0ChebSPMF_NEP                  1.71 s (  -1%)     758 MiB (  +0%)
       PEP format with ComputeY0ChebSPMF_NEP                  452 ms ( -14%)    83.0 MiB (  +0%)
       DEP WITH DELAYS>1                                      402 ms (  -9%)     155 MiB (  +0%)
       PEP SHIFTED AND SCALED                                 317 ms ( -14%)    63.1 MiB (  +0%)
       compute_y0 AS INPUT FOR QEP (naive)                    314 ms (  -2%)    70.4 MiB (  +0%)
       PEP                                                    277 ms ( -14%)    56.4 MiB (  +0%)
+      QDEP IN SPMF format                                    182 ms ( -46%)    77.6 MiB (  +0%)
       compute_y0 AS INPUT FOR QDEP (combine DEP and PEP)     105 ms (  -4%)    21.6 MiB (  -0%)
     orthogonalization                                       67.4 ms (  -5%)    20.8 MiB (  +0%)
       ModifiedGramSchmidt                                   17.8 ms (  -4%)    5.17 MiB (  +0%)
       DGKS                                                  16.6 ms (  -5%)    5.16 MiB (  +0%)
       User provided doubleGS                                16.6 ms (  -5%)    5.34 MiB (  +0%)
       ClassicalGramSchmidt                                  16.4 ms (  -4%)    5.14 MiB (  +0%)
-    Scale Cheb's to different interval w DEP                40.6 ms ( +13%)    9.53 MiB (  +5%)
     accuracy eigenpairs                                     16.0 ms (  -6%)    5.16 MiB (  +0%)
   NLEIGS: Particle variant S                                 17.2 s (  +6%)    8.40 GiB (  +0%)
   WEP                                                        13.9 s (  +0%)    8.30 GiB (  -0%)
   NLEIGS: Gun variant R1                                     9.57 s ( -11%)    1.90 GiB (  +0%)
   NLEIGS: Gun variant P                                      9.54 s ( -10%)    1.88 GiB (  +0%)
   NLEIGS: Gun variant S                                      9.00 s ( -15%)    2.23 GiB (  +0%)
   Newton iterations                                          5.46 s ( -17%)    1.36 GiB (  +0%)
     implicitdet                                              3.21 s ( -12%)     864 MiB (  +0%)
+    Resinv                                                   2.22 s ( -23%)     527 MiB (  +0%)
-    Newton and AugNewton                                    15.0 ms (+869%)     428 KiB (  +0%)
     QuasiNewton                                             12.3 ms (  +2%)    1.67 MiB (  +0%)
-    Rayleigh Function Iteration                             6.48 ms ( +75%)    1.89 MiB (  +0%)
+    Newton QR                                               2.53 ms ( -43%)    1.82 MiB (  +0%)
+  TIAR                                                       5.37 s (  -9%)    2.45 GiB (  -2%)
     Solve by projection                                      3.75 s (  -7%)    1.61 GiB (  +0%)
+    orthogonalization                                        939 ms ( -14%)     510 MiB (  -6%)
+      User provided doubleGS                                 238 ms ( -13%)     128 MiB (  -6%)
+      DGKS                                                   235 ms ( -13%)     128 MiB (  -6%)
+      ClassicalGramSchmidt                                   234 ms ( -15%)     128 MiB (  -6%)
+      ModifiedGramSchmidt                                    233 ms ( -14%)     128 MiB (  -6%)
+    equivalance with IAR                                     445 ms ( -11%)     219 MiB (  -4%)
+    accuracy eigenpairs                                      234 ms ( -14%)     128 MiB (  -6%)
+  linsolvers                                                 3.82 s ( -31%)     912 MiB (  +0%)
   transformations                                            3.69 s (  -2%)     729 MiB (  -0%)
     Shift and scale                                          2.77 s (  -1%)     599 MiB (  -0%)
     Möbius transformation                                    924 ms (  -4%)     130 MiB (  +0%)
-  Companion Linearization                                    3.29 s ( +81%)     248 MiB (  +0%)
+  PeriodicDDE                                                2.68 s ( -24%)     911 MiB (  +0%)
   Infbilanczos σ=0                                           2.10 s (  +3%)    1.42 GiB (  -0%)
   compute eigvec lopcg                                       2.08 s (  -2%)     559 MiB (  +0%)
     pep0                                                     1.61 s (  -2%)     272 MiB (  +0%)
     dep0_sparse                                              468 ms (  -1%)     287 MiB (  +0%)
+  Jacobi–Davidson                                            1.72 s ( -25%)     446 MiB (  -3%)
     Effenberger                                              1.48 s ( -13%)     409 MiB (  +0%)
+    Betcke-Voss                                              243 ms ( -58%)    36.3 MiB ( -29%)
   GUN (native)                                               1.50 s (  -8%)     306 MiB (  +0%)
     Running algorithm                                        1.49 s (  -8%)     297 MiB (  +0%)
     Compute derivatives                                     13.0 ms (  +2%)    9.70 MiB (  +0%)
   NLEIGS: Scalar                                             809 ms (  +6%)     473 MiB (  +0%)
     Fully rational                                           408 ms (  +8%)     241 MiB (  +0%)
     Polynomial                                               400 ms (  +4%)     232 MiB (  +0%)
+  Eigenvector extraction (medium/large scale)                677 ms ( -27%)     553 MiB (  +0%)
     Test problem: pep0_sparse_003                            367 ms ( -20%)     226 MiB (  +0%)
+      backslash_linsolvercreator                             124 ms ( -21%)    76.3 MiB (  +0%)
       Passing a linsolvercreator as argument                 123 ms ( -18%)    74.8 MiB (  +0%)
+      default_linsolvercreator                               120 ms ( -20%)    74.8 MiB (  +0%)
+    Test problem: dep0                                       160 ms ( -33%)     170 MiB (  +0%)
+      backslash_linsolvercreator                            61.9 ms ( -28%)    74.5 MiB (  +0%)
+      default_linsolvercreator                              49.3 ms ( -36%)    47.8 MiB (  +0%)
+      Passing a linsolvercreator as argument                49.1 ms ( -36%)    47.8 MiB (  +0%)
+    Test problem: pep0                                       150 ms ( -36%)     157 MiB (  +0%)
+      backslash_linsolvercreator                            57.0 ms ( -32%)    68.8 MiB (  +0%)
+      Passing a linsolvercreator as argument                48.0 ms ( -35%)    44.0 MiB (  +0%)
+      default_linsolvercreator                              44.5 ms ( -40%)    44.0 MiB (  +0%)
-  IAR                                                        637 ms ( +36%)    74.5 MiB ( +14%)
-    orthogonalization                                        550 ms ( +47%)    62.1 MiB ( +18%)
-      ModifiedGramSchmidt                                    253 ms (+200%)    21.3 MiB ( +75%)
       User provided doubleGS                                 110 ms (  +2%)    14.7 MiB (  +0%)
-      ClassicalGramSchmidt                                   100 ms ( +12%)    13.5 MiB (  +8%)
+      DGKS                                                  87.6 ms (  -6%)    12.5 MiB (  -4%)
+    accuracy eigenpairs                                     87.2 ms (  -7%)    12.5 MiB (  -4%)
   Interpolation                                              580 ms ( -15%)     377 MiB (  +0%)
+    Random pep (original pep of degree 2)                    387 ms ( -21%)     290 MiB (  +0%)
     Random sparse pep (original pep of degree 2)             138 ms ( -12%)    68.2 MiB (  +0%)
-    Random sparse dep                                       48.9 ms ( +41%)    17.6 MiB (  +0%)
     Random dep                                              6.73 ms ( +18%)    1.07 MiB (  +0%)
   NLEIGS: NEP Types                                          510 ms (  +5%)     183 MiB (  +0%)
     Custom NEP type                                          186 ms (  +7%)     115 MiB (  -0%)
     PEP + LowRankFactorizedNEP                              82.2 ms (  +5%)    17.1 MiB (  +0%)
     PEP + SPMF                                              81.7 ms (  +5%)    17.1 MiB (  +0%)
     PEP                                                     80.5 ms (  +3%)    17.0 MiB (  +0%)
     SPMF_NEP                                                80.3 ms (  +3%)    17.0 MiB (  +0%)
   NLEIGS: Basic functionality                                420 ms (  +3%)    91.1 MiB (  +0%)
     return_details                                          82.3 ms (  +4%)    17.6 MiB (  -0%)
     Complex-valued start vector                             81.9 ms (  +3%)    17.5 MiB (  +0%)
     Non-convergent linearization (return_details)           81.3 ms (  +4%)    17.1 MiB (  +0%)
     Polynomial only                                         80.7 ms (  +1%)    17.0 MiB (  +0%)
     Complex-valued matrices                                 80.7 ms (  +1%)    17.5 MiB (  +0%)
     Non-convergent linearization (static)                   6.66 ms (  +2%)    2.18 MiB (  +1%)
     Non-convergent linearization                            6.51 ms (  +1%)    2.12 MiB (  +0%)
+  Gallery                                                    385 ms ( -30%)     129 MiB (  +0%)
+  Beyn contour                                               288 ms ( -43%)    27.8 MiB (  -0%)
+    disk at origin                                           171 ms ( -34%)    13.8 MiB (  +0%)
+    shifted disk                                             117 ms ( -53%)    14.0 MiB (  -0%)
   Inner Solves                                               157 ms ( -17%)    43.7 MiB (  +0%)
   Eigenvector extraction (small scale)                      57.4 ms ( -14%)    54.8 MiB (  -0%)
     Test problem: pep0_sparse_003                           38.5 ms ( -10%)    29.5 MiB (  -0%)
       Passing a linsolvercreator as argument                13.1 ms (  -7%)    9.74 MiB (  -0%)
       backslash_linsolvercreator                            12.8 ms ( -10%)    10.0 MiB (  -0%)
       default_linsolvercreator                              12.6 ms ( -11%)    9.74 MiB (  -0%)
+    Test problem: pep0                                      18.9 ms ( -22%)    25.2 MiB (  +0%)
       backslash_linsolvercreator                            7.21 ms ( -16%)    11.1 MiB (  +0%)
+      Passing a linsolvercreator as argument                5.89 ms ( -24%)    7.09 MiB (  +0%)
+      default_linsolvercreator                              5.77 ms ( -27%)    7.09 MiB (  +0%)
+    Test problem: dep0                                      97.9 μs ( -35%)     111 KiB (  +0%)
+      backslash_linsolvercreator                            33.4 μs ( -35%)    39.9 KiB (  +0%)
+      default_linsolvercreator                              32.3 μs ( -35%)    35.4 KiB (  +0%)
+      Passing a linsolvercreator as argument                32.3 μs ( -34%)    35.5 KiB (  +0%)
   Deflation (combined with MSLP)                            35.1 ms ( -12%)    17.5 MiB (  +0%)
+  blocknewton                                               19.3 ms ( -44%)    4.78 MiB (  +0%)
   compute_types                                             12.2 ms ( -19%)    6.37 MiB (  +0%)
     PEP (BigFloat)                                          2.00 ms ( +11%)    1.35 MiB (  +0%)
     DEP (BigFloat)                                          1.73 ms (  -2%)    0.98 MiB (  +0%)
     DEP (Complex{BigFloat})                                 1.36 ms (  +0%)     874 KiB (  +0%)
     DEP (Float64)                                           1.27 ms (  +2%)     529 KiB (  +0%)
+    SPMFSumNEP (Complex{Float64})                           1.01 ms ( -39%)     402 KiB (  +0%)
     PEP (Float64)                                            930 μs ( -12%)     353 KiB (  +0%)
     SPMF_NEP #1 (Float64)                                    833 μs ( -16%)     319 KiB (  +0%)
+    DEP sparse (Float64)                                     797 μs ( -53%)     437 KiB (  +0%)
+    SPMF_NEP #4 (Complex{Float64})                           694 μs ( -42%)     328 KiB (  +0%)
+    SPMF_NEP #2 (Complex{Float64})                           640 μs ( -40%)     328 KiB (  +0%)
     PEP (Complex{Float32})                                   638 μs ( -18%)     322 KiB (  +0%)
     SPMF_NEP #3 (BigFloat)                                   257 μs ( -17%)     242 KiB (  +0%)
+  broyden                                                   8.50 ms ( -35%)    3.71 MiB ( -25%)
   SPMF                                                      1.66 ms ( -19%)     939 KiB (  +0%)
+    compute_Mder_from_MM                                     687 μs ( -21%)     331 KiB (  +0%)
     compute_MM                                               423 μs (  +1%)     140 KiB (  +0%)
     Compute_Mlincomb                                         181 μs ( -18%)     106 KiB (  +0%)
+    REP                                                      147 μs ( -36%)     187 KiB (  +0%)
+    DEP                                                      117 μs ( -34%)    87.1 KiB (  +0%)
+    PEP                                                      107 μs ( -28%)    88.0 KiB (  +0%)
+  sgiter                                                    1.51 ms ( -23%)     290 KiB (  +0%)
   discretizepolygon                                         1.17 ms ( -20%)     633 KiB (  +0%)
     unit disk                                                742 μs ( -15%)     238 KiB (  +0%)
     concave polygon                                          248 μs ( -18%)     281 KiB (  +0%)
+    too narrow Σ                                             100 μs ( -42%)    29.8 KiB (  +0%)
+    narrow Σ                                                39.1 μs ( -31%)    34.2 KiB (  +0%)
+    Chebyshev points                                        36.2 μs ( -21%)    50.2 KiB (  +0%)
+  MSLP                                                       785 μs ( -26%)     476 KiB (  +0%)
+    mslp + double                                            785 μs ( -26%)     476 KiB (  +0%)
   cached_lu_solver                                           352 μs ( -17%)     203 KiB (  +0%)
+  Core                                                       282 μs ( -34%)    65.3 KiB (  +0%)
-  Serialization                                              134 μs (  -2%)    77.8 KiB ( +36%)
+  inpolygon                                                 43.2 μs ( -22%)    33.2 KiB (  +0%)
+  Types (sumnep)                                            26.8 μs ( -27%)    32.8 KiB (  +0%)
 ───────────────────────────────────────────────────────────────────────────────────────────────
```
Previous context:
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
Current context:
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
