### Report fewer environment variables, and add onlybench macro
commit [3630cd1fadeb02a7d03f2afc38a826280b82edd4](https://github.com/nep-pack/NonlinearEigenproblems.jl/commit/3630cd1fadeb02a7d03f2afc38a826280b82edd4)
```diff
 ───────────────────────────────────────────────────────────────────────────────────────────────
 Test name                                                        Time               Memory
 ───────────────────────────────────────────────────────────────────────────────────────────────
+All tests                                                     208 s ( -13%)    61.8 GiB (  -3%)
+  Nonlinear Arnoldi                                          47.2 s ( -24%)    10.7 GiB ( -16%)
+  NLEIGS: Gun variant R2                                     26.3 s ( -32%)    6.75 GiB (  +0%)
-  NLEIGS: Particle variant R2                                23.0 s (  +7%)    7.51 GiB (  +6%)
   IAR Chebyshev version                                      17.0 s (  -0%)    2.93 GiB (  +0%)
     compute_y0_method for different types                    16.9 s (  -0%)    2.89 GiB (  +0%)
       DEP SHIFTED AND SCALED                                 6.14 s (  +6%)     556 MiB (  +0%)
       DEP WITH GENERIC Y0                                    4.46 s (  +0%)     514 MiB (  +0%)
       PEP in SPMF format                                     2.67 s (  +1%)     607 MiB (  +0%)
       DEP format with ComputeY0ChebSPMF_NEP                  1.63 s (  -2%)     758 MiB (  +0%)
       PEP format with ComputeY0ChebSPMF_NEP                  448 ms ( -13%)    83.0 MiB (  +0%)
       DEP WITH DELAYS>1                                      390 ms (  -9%)     155 MiB (  +0%)
       PEP SHIFTED AND SCALED                                 317 ms ( -14%)    63.1 MiB (  +0%)
       compute_y0 AS INPUT FOR QEP (naive)                    309 ms (  -5%)    70.4 MiB (  +0%)
       PEP                                                    275 ms ( -12%)    56.4 MiB (  +0%)
+      QDEP IN SPMF format                                    180 ms ( -46%)    77.6 MiB (  +0%)
       compute_y0 AS INPUT FOR QDEP (combine DEP and PEP)    95.8 ms ( -11%)    21.6 MiB (  -0%)
     orthogonalization                                       65.7 ms (  -3%)    20.8 MiB (  +0%)
       ModifiedGramSchmidt                                   17.2 ms (  -6%)    5.17 MiB (  +0%)
       User provided doubleGS                                16.3 ms (  +4%)    5.34 MiB (  +0%)
       DGKS                                                  16.3 ms (  -4%)    5.16 MiB (  +0%)
       ClassicalGramSchmidt                                  15.9 ms (  -5%)    5.14 MiB (  +0%)
-    Scale Cheb's to different interval w DEP                44.5 ms ( +26%)    10.0 MiB (  +9%)
     accuracy eigenpairs                                     15.9 ms (  -6%)    5.16 MiB (  +0%)
   NLEIGS: Particle variant S                                 16.6 s (  +4%)    8.40 GiB (  +0%)
   WEP                                                        13.8 s (  +1%)    8.30 GiB (  -0%)
   NLEIGS: Gun variant R1                                     9.60 s (  -9%)    1.90 GiB (  +0%)
   NLEIGS: Gun variant P                                      9.38 s ( -10%)    1.88 GiB (  +0%)
   NLEIGS: Gun variant S                                      8.84 s ( -15%)    2.23 GiB (  +0%)
   Newton iterations                                          5.55 s ( -10%)    1.36 GiB (  +0%)
     implicitdet                                              3.24 s (  -4%)     864 MiB (  +0%)
     Resinv                                                   2.29 s ( -18%)     527 MiB (  +0%)
+    QuasiNewton                                             6.30 ms ( -48%)    1.67 MiB (  +0%)
-    Rayleigh Function Iteration                             5.70 ms ( +96%)    1.89 MiB (  +0%)
-    Newton and AugNewton                                    3.30 ms (+106%)     428 KiB (  +0%)
     Newton QR                                               2.52 ms (  -4%)    1.82 MiB (  +0%)
+  TIAR                                                       5.27 s (  -9%)    2.45 GiB (  -2%)
     Solve by projection                                      3.70 s (  -7%)    1.61 GiB (  +0%)
+    orthogonalization                                        920 ms ( -14%)     510 MiB (  -6%)
+      ClassicalGramSchmidt                                   232 ms ( -13%)     128 MiB (  -6%)
+      ModifiedGramSchmidt                                    230 ms ( -15%)     128 MiB (  -6%)
+      DGKS                                                   230 ms ( -15%)     128 MiB (  -6%)
+      User provided doubleGS                                 229 ms ( -14%)     128 MiB (  -6%)
+    equivalance with IAR                                     439 ms ( -12%)     219 MiB (  -4%)
+    accuracy eigenpairs                                      212 ms ( -22%)     128 MiB (  -6%)
+  linsolvers                                                 3.83 s ( -30%)     912 MiB (  +0%)
   transformations                                            3.58 s (  -2%)     729 MiB (  -0%)
     Shift and scale                                          2.68 s (  -2%)     599 MiB (  -0%)
     Möbius transformation                                    903 ms (  -3%)     130 MiB (  +0%)
-  Companion Linearization                                    3.34 s ( +86%)     248 MiB (  +0%)
   PeriodicDDE                                                2.76 s ( -20%)     911 MiB (  +0%)
   Infbilanczos σ=0                                           2.07 s (  +4%)    1.42 GiB (  +0%)
   compute eigvec lopcg                                       2.04 s (  -2%)     559 MiB (  +0%)
     pep0                                                     1.57 s (  -3%)     272 MiB (  +0%)
     dep0_sparse                                              467 ms (  +0%)     287 MiB (  +0%)
+  Jacobi–Davidson                                            1.76 s ( -21%)     446 MiB (  -3%)
     Effenberger                                              1.50 s ( -12%)     409 MiB (  +0%)
+    Betcke-Voss                                              257 ms ( -51%)    36.3 MiB ( -29%)
   GUN (native)                                               1.45 s ( -10%)     306 MiB (  +0%)
     Running algorithm                                        1.44 s ( -10%)     297 MiB (  +0%)
     Compute derivatives                                     13.0 ms ( +16%)    9.70 MiB (  +0%)
   NLEIGS: Scalar                                             788 ms (  +1%)     473 MiB (  -0%)
     Fully rational                                           399 ms (  +2%)     241 MiB (  -0%)
     Polynomial                                               389 ms (  -1%)     232 MiB (  -0%)
+  Eigenvector extraction (medium/large scale)                649 ms ( -24%)     553 MiB (  +0%)
     Test problem: pep0_sparse_003                            351 ms ( -10%)     226 MiB (  +0%)
+      Passing a linsolvercreator as argument                 119 ms ( -22%)    74.8 MiB (  +0%)
       default_linsolvercreator                               117 ms (  -1%)    74.8 MiB (  +0%)
       backslash_linsolvercreator                             115 ms (  -3%)    76.3 MiB (  +0%)
+    Test problem: dep0                                       152 ms ( -35%)     170 MiB (  +0%)
+      backslash_linsolvercreator                            58.3 ms ( -32%)    74.5 MiB (  +0%)
+      default_linsolvercreator                              48.0 ms ( -37%)    47.8 MiB (  +0%)
+      Passing a linsolvercreator as argument                45.8 ms ( -38%)    47.8 MiB (  +0%)
+    Test problem: pep0                                       147 ms ( -36%)     157 MiB (  +0%)
+      backslash_linsolvercreator                            55.9 ms ( -32%)    68.8 MiB (  +0%)
+      default_linsolvercreator                              46.5 ms ( -37%)    44.0 MiB (  +0%)
+      Passing a linsolvercreator as argument                44.3 ms ( -39%)    44.0 MiB (  +0%)
-  IAR                                                        625 ms ( +36%)    74.5 MiB ( +14%)
-    orthogonalization                                        540 ms ( +46%)    62.1 MiB ( +18%)
-      ModifiedGramSchmidt                                    239 ms (+190%)    21.3 MiB ( +75%)
       User provided doubleGS                                 110 ms (  +2%)    14.7 MiB (  +0%)
-      ClassicalGramSchmidt                                   103 ms ( +19%)    13.5 MiB (  +8%)
+      DGKS                                                  87.5 ms (  -6%)    12.5 MiB (  -4%)
+    accuracy eigenpairs                                     85.6 ms (  -6%)    12.5 MiB (  -4%)
   Interpolation                                              603 ms ( -13%)     377 MiB (  +0%)
     Random pep (original pep of degree 2)                    403 ms ( -17%)     290 MiB (  +0%)
     Random sparse pep (original pep of degree 2)             140 ms (  -7%)    68.2 MiB (  +0%)
     Random sparse dep                                       52.1 ms (  +2%)    17.6 MiB (  +0%)
-    Random dep                                              7.27 ms ( +27%)    1.07 MiB (  +0%)
   NLEIGS: NEP Types                                          500 ms (  +2%)     183 MiB (  +0%)
     Custom NEP type                                          181 ms (  +4%)     115 MiB (  -0%)
     SPMF_NEP                                                80.3 ms (  +3%)    17.0 MiB (  +0%)
     PEP + LowRankFactorizedNEP                              79.9 ms (  +2%)    17.1 MiB (  +0%)
     PEP                                                     79.7 ms (  +2%)    17.0 MiB (  +0%)
     PEP + SPMF                                              79.3 ms (  +0%)    17.1 MiB (  +0%)
   NLEIGS: Basic functionality                                418 ms (  +2%)    91.1 MiB (  +0%)
     Complex-valued start vector                             82.8 ms (  +4%)    17.5 MiB (  +0%)
     return_details                                          81.6 ms (  +2%)    17.6 MiB (  -0%)
     Complex-valued matrices                                 81.4 ms (  +2%)    17.5 MiB (  +0%)
     Non-convergent linearization (return_details)           79.8 ms (  +1%)    17.1 MiB (  +0%)
     Polynomial only                                         78.8 ms (  +2%)    17.0 MiB (  +0%)
     Non-convergent linearization (static)                   7.23 ms (  +8%)    2.18 MiB (  +1%)
     Non-convergent linearization                            6.52 ms (  +1%)    2.12 MiB (  +1%)
   Gallery                                                    363 ms ( -12%)     129 MiB (  +0%)
+  Beyn contour                                               282 ms ( -22%)    27.8 MiB (  -0%)
+    shifted disk                                             146 ms ( -40%)    14.0 MiB (  -0%)
     disk at origin                                           136 ms ( +15%)    13.8 MiB (  +0%)
+  Inner Solves                                               159 ms ( -20%)    43.7 MiB (  +0%)
   Eigenvector extraction (small scale)                      56.7 ms (  -2%)    54.8 MiB (  -0%)
     Test problem: pep0_sparse_003                           37.8 ms (  -5%)    29.5 MiB (  -0%)
       backslash_linsolvercreator                            12.8 ms (  -6%)    10.0 MiB (  -0%)
       Passing a linsolvercreator as argument                12.8 ms (  -3%)    9.74 MiB (  -0%)
       default_linsolvercreator                              12.3 ms (  -5%)    9.74 MiB (  -0%)
     Test problem: pep0                                      18.7 ms (  +3%)    25.2 MiB (  +0%)
       backslash_linsolvercreator                            6.77 ms ( +11%)    11.1 MiB (  +0%)
       default_linsolvercreator                              6.02 ms ( -16%)    7.09 MiB (  +0%)
       Passing a linsolvercreator as argument                5.96 ms ( +18%)    7.09 MiB (  +0%)
+    Test problem: dep0                                      97.8 μs ( -30%)     111 KiB (  +0%)
+      backslash_linsolvercreator                            33.6 μs ( -31%)    39.9 KiB (  +0%)
+      default_linsolvercreator                              32.2 μs ( -30%)    35.4 KiB (  +0%)
+      Passing a linsolvercreator as argument                32.1 μs ( -30%)    35.5 KiB (  +0%)
   Deflation (combined with MSLP)                            37.3 ms (  -8%)    17.5 MiB (  +0%)
+  blocknewton                                               27.1 ms ( -22%)    4.78 MiB (  +0%)
   compute_types                                             11.5 ms (  -6%)    6.37 MiB (  +0%)
     DEP (BigFloat)                                          1.66 ms ( +13%)    0.98 MiB (  +0%)
     PEP (BigFloat)                                          1.64 ms ( -10%)    1.35 MiB (  +0%)
     DEP (Float64)                                           1.31 ms (  +9%)     529 KiB (  +0%)
     SPMFSumNEP (Complex{Float64})                            955 μs ( -17%)     402 KiB (  +0%)
     DEP (Complex{BigFloat})                                  910 μs ( -20%)     874 KiB (  +0%)
     SPMF_NEP #4 (Complex{Float64})                           890 μs ( +12%)     328 KiB (  +0%)
     SPMF_NEP #2 (Complex{Float64})                           881 μs ( +12%)     328 KiB (  +0%)
     SPMF_NEP #1 (Float64)                                    811 μs ( +10%)     319 KiB (  +0%)
+    DEP sparse (Float64)                                     808 μs ( -38%)     437 KiB (  +0%)
     PEP (Float64)                                            697 μs (  -8%)     353 KiB (  +0%)
     PEP (Complex{Float32})                                   653 μs ( -14%)     322 KiB (  +0%)
     SPMF_NEP #3 (BigFloat)                                   262 μs ( -17%)     242 KiB (  +0%)
+  broyden                                                   8.30 ms ( -34%)    3.71 MiB ( -25%)
   SPMF                                                      1.62 ms ( -11%)     939 KiB (  +0%)
     compute_Mder_from_MM                                     672 μs ( +10%)     331 KiB (  +0%)
     compute_MM                                               408 μs (  -5%)     140 KiB (  +0%)
+    Compute_Mlincomb                                         174 μs ( -21%)     106 KiB (  +0%)
+    REP                                                      147 μs ( -34%)     187 KiB (  +0%)
+    DEP                                                      113 μs ( -38%)    87.1 KiB (  +0%)
+    PEP                                                      106 μs ( -29%)    88.0 KiB (  +0%)
+  sgiter                                                    1.42 ms ( -37%)     290 KiB (  +0%)
   discretizepolygon                                         1.16 ms ( -19%)     633 KiB (  +0%)
     unit disk                                                740 μs ( -15%)     238 KiB (  +0%)
     concave polygon                                          245 μs ( -16%)     281 KiB (  +0%)
+    too narrow Σ                                            99.3 μs ( -43%)    29.8 KiB (  +0%)
+    narrow Σ                                                39.2 μs ( -27%)    34.2 KiB (  +0%)
     Chebyshev points                                        37.6 μs ( -12%)    50.2 KiB (  +0%)
   MSLP                                                       800 μs ( -19%)     476 KiB (  +0%)
     mslp + double                                            800 μs ( -19%)     476 KiB (  +0%)
+  Core                                                       292 μs ( -28%)    65.3 KiB (  +0%)
   cached_lu_solver                                           253 μs ( -17%)     203 KiB (  +0%)
+  Serialization                                              136 μs ( -23%)    77.7 KiB (  -2%)
   inpolygon                                                 43.6 μs ( -16%)    33.2 KiB (  +0%)
+  Types (sumnep)                                            27.4 μs ( -23%)    32.8 KiB (  +0%)
 ───────────────────────────────────────────────────────────────────────────────────────────────
```
Previous context:
```
UTC time: 2018-09-13 22:47:23
Commit: 81a1f7f12cc7e0643779151e2696055f6a386c96
Message: Run all tests
Travis build: 689

Julia Version 1.0.0
Commit 5d4eaca0c9 (2018-08-08 20:58 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 14.04.5 LTS
  uname: Linux 4.4.0-101-generic #124~14.04.1-Ubuntu SMP Fri Nov 10 19:05:36 UTC 2017 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2600 MHz      73278 s          0 s      17003 s      35098 s          0 s
       #2  2600 MHz      65477 s          0 s      20360 s      39230 s          0 s
       
  Memory: 7.304546356201172 GB (4962.58203125 MB free)
  Uptime: 1260.0 sec
  Load Avg:  1.49755859375  1.54736328125  1.1552734375
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, sandybridge)
Environment:
  TRAVIS_JULIA_VERSION = 1.0
  JULIA_LOAD_PATH = @:/tmp/tmp3TeHhN
  MANPATH = /home/travis/.nvm/versions/node/v6.12.0/share/man:/home/travis/.kiex/elixirs/elixir-1.3.2/man:/home/travis/.rvm/rubies/ruby-2.4.1/share/man:/usr/local/man:/usr/local/cmake-3.9.2/man:/usr/local/clang-5.0.0/share/man:/usr/local/share/man:/usr/share/man:/home/travis/.rvm/man
  NVM_CD_FLAGS = 
  GEM_HOME = /home/travis/.rvm/gems/ruby-2.4.1
  TERM = xterm
  MY_RUBY_HOME = /home/travis/.rvm/rubies/ruby-2.4.1
  PYTHON_CFLAGS = -g -fstack-protector --param=ssp-buffer-size=4 -Wformat -Werror=format-security
  PATH = /home/travis/bin:/home/travis/.local/bin:/opt/pyenv/shims:/home/travis/.phpenv/shims:/home/travis/perl5/perlbrew/bin:/home/travis/.nvm/versions/node/v6.12.0/bin:/home/travis/.kiex/elixirs/elixir-1.3.2/bin:/home/travis/.kiex/bin:/home/travis/.rvm/gems/ruby-2.4.1/bin:/home/travis/.rvm/gems/ruby-2.4.1@global/bin:/home/travis/.rvm/rubies/ruby-2.4.1/bin:/home/travis/gopath/bin:/home/travis/.gimme/versions/go1.7.4.linux.amd64/bin:/usr/local/phantomjs/bin:/usr/local/phantomjs:/usr/local/neo4j-3.2.7/bin:/usr/local/cmake-3.9.2/bin:/usr/local/clang-5.0.0/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/opt/ghc/bin:/home/travis/.rvm/bin:/home/travis/.phpenv/bin:/opt/pyenv/bin:/home/travis/.yarn/bin:/home/travis/julia/bin
  JAVA_HOME = /usr/lib/jvm/java-8-oracle
  PERLBREW_HOME = /home/travis/.perlbrew
  TRAVIS_HOME = /home/travis
  HOME = /home/travis
  GEM_PATH = /home/travis/.rvm/gems/ruby-2.4.1:/home/travis/.rvm/gems/ruby-2.4.1@global
  GOPATH = /home/travis/gopath
  JULIA_LOAD_PATH = @:/tmp/tmp3TeHhN
```
Current context:
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
