### Run all tests
commit [81a1f7f12cc7e0643779151e2696055f6a386c96](https://github.com/nep-pack/NonlinearEigenproblems.jl/commit/81a1f7f12cc7e0643779151e2696055f6a386c96)
```diff
 ───────────────────────────────────────────────────────────────────────────────────────────────
 Test name                                                        Time               Memory
 ───────────────────────────────────────────────────────────────────────────────────────────────
 All tests                                                     240 s (  -6%)    63.5 GiB (  -0%)
   Nonlinear Arnoldi                                          62.2 s (  -7%)    12.7 GiB (  +0%)
   NLEIGS: Gun variant R2                                     38.9 s (  -8%)    6.75 GiB (  +0%)
   NLEIGS: Particle variant R2                                21.6 s (  -9%)    7.09 GiB (  +0%)
   IAR Chebyshev version                                      17.1 s (  -5%)    2.93 GiB (  +0%)
     compute_y0_method for different types                    16.9 s (  -5%)    2.89 GiB (  +0%)
       DEP SHIFTED AND SCALED                                 5.80 s (  -9%)     556 MiB (  +0%)
       DEP WITH GENERIC Y0                                    4.45 s (  +0%)     514 MiB (  +0%)
       PEP in SPMF format                                     2.63 s (  -2%)     607 MiB (  +0%)
+      DEP format with ComputeY0ChebSPMF_NEP                  1.67 s ( -19%)     758 MiB (  +0%)
       PEP format with ComputeY0ChebSPMF_NEP                  518 ms (  +5%)    83.0 MiB (  +0%)
       DEP WITH DELAYS>1                                      430 ms (  +5%)     155 MiB (  +0%)
-      PEP SHIFTED AND SCALED                                 370 ms ( +13%)    63.1 MiB (  +0%)
       QDEP IN SPMF format                                    335 ms (  -3%)    77.6 MiB (  +0%)
       compute_y0 AS INPUT FOR QEP (naive)                    325 ms (  +7%)    70.4 MiB (  +0%)
       PEP                                                    314 ms (  +9%)    56.4 MiB (  +0%)
-      compute_y0 AS INPUT FOR QDEP (combine DEP and PEP)     108 ms ( +14%)    21.6 MiB (  +0%)
     orthogonalization                                       67.7 ms (  +2%)    20.8 MiB (  +0%)
-      ModifiedGramSchmidt                                   18.3 ms ( +11%)    5.17 MiB (  +0%)
       DGKS                                                  16.9 ms (  +0%)    5.16 MiB (  +0%)
       ClassicalGramSchmidt                                  16.8 ms (  +2%)    5.14 MiB (  +0%)
       User provided doubleGS                                15.7 ms (  -6%)    5.34 MiB (  +0%)
     Scale Cheb's to different interval w DEP                35.4 ms (  -6%)    9.12 MiB (  +0%)
     accuracy eigenpairs                                     16.8 ms (  +2%)    5.16 MiB (  +0%)
   NLEIGS: Particle variant S                                 15.9 s (  -9%)    8.40 GiB (  +0%)
   WEP                                                        13.6 s (  -8%)    8.31 GiB (  +0%)
   NLEIGS: Gun variant R1                                     10.6 s (  -8%)    1.90 GiB (  -0%)
   NLEIGS: Gun variant S                                      10.4 s (  -7%)    2.23 GiB (  +0%)
   NLEIGS: Gun variant P                                      10.4 s (  -8%)    1.88 GiB (  +0%)
-  Newton iterations                                          6.19 s ( +15%)    1.36 GiB (  +0%)
     implicitdet                                              3.37 s (  +6%)     864 MiB (  +0%)
-    Resinv                                                   2.80 s ( +27%)     527 MiB (  +0%)
-    QuasiNewton                                             12.1 ms ( +52%)    1.67 MiB (  +0%)
+    Rayleigh Function Iteration                             2.91 ms ( -31%)    1.89 MiB (  +0%)
+    Newton QR                                               2.64 ms ( -33%)    1.82 MiB (  +0%)
     Newton and AugNewton                                    1.60 ms (  +5%)     428 KiB (  +0%)
   TIAR                                                       5.81 s (  -0%)    2.50 GiB (  +0%)
     Solve by projection                                      3.97 s (  -2%)    1.61 GiB (  +0%)
     orthogonalization                                        1.07 s (  +4%)     544 MiB (  +0%)
       ModifiedGramSchmidt                                    270 ms (  +4%)     136 MiB (  +0%)
       DGKS                                                   269 ms (  +4%)     136 MiB (  +0%)
       ClassicalGramSchmidt                                   268 ms (  +5%)     136 MiB (  +0%)
       User provided doubleGS                                 267 ms (  +4%)     136 MiB (  +0%)
     equivalance with IAR                                     498 ms (  +6%)     228 MiB (  +0%)
     accuracy eigenpairs                                      271 ms (  +6%)     136 MiB (  +0%)
   linsolvers                                                 5.48 s (  -7%)     912 MiB (  +0%)
+  transformations                                            3.66 s ( -11%)     731 MiB (  +0%)
+    Shift and scale                                          2.73 s ( -12%)     601 MiB (  +0%)
     Möbius transformation                                    934 ms (  -9%)     130 MiB (  +0%)
-  PeriodicDDE                                                3.44 s ( +25%)     911 MiB (  +0%)
   Jacobi–Davidson                                            2.22 s (  +7%)     460 MiB (  +0%)
-    Effenberger                                              1.70 s ( +11%)     409 MiB (  +0%)
     Betcke-Voss                                              520 ms (  -4%)    51.4 MiB (  +0%)
   compute eigvec lopcg                                       2.09 s (  +6%)     559 MiB (  +0%)
     pep0                                                     1.62 s (  +8%)     272 MiB (  +0%)
     dep0_sparse                                              465 ms (  +1%)     287 MiB (  +0%)
+  Infbilanczos σ=0                                           2.00 s ( -11%)    1.42 GiB (  -0%)
   Companion Linearization                                    1.80 s ( -10%)     248 MiB (  +0%)
+  GUN (native)                                               1.61 s ( -11%)     306 MiB (  +0%)
+    Running algorithm                                        1.60 s ( -11%)     297 MiB (  +0%)
+    Compute derivatives                                     11.2 ms ( -15%)    9.70 MiB (  +0%)
   Eigenvector extraction (medium/large scale)                855 ms ( -10%)     553 MiB (  -0%)
+    Test problem: pep0_sparse_003                            390 ms ( -16%)     226 MiB (  -0%)
       Passing a linsolvercreator as argument                 153 ms (  -0%)    74.7 MiB (  -0%)
+      backslash_linsolvercreator                             119 ms ( -26%)    76.3 MiB (  +0%)
+      default_linsolvercreator                               119 ms ( -23%)    74.7 MiB (  +0%)
     Test problem: dep0                                       236 ms (  -4%)     170 MiB (  +0%)
       backslash_linsolvercreator                            85.2 ms (  -5%)    74.5 MiB (  +0%)
       default_linsolvercreator                              76.1 ms (  -1%)    47.8 MiB (  +0%)
       Passing a linsolvercreator as argument                74.2 ms (  -5%)    47.8 MiB (  +0%)
     Test problem: pep0                                       229 ms (  -3%)     157 MiB (  +0%)
       backslash_linsolvercreator                            82.8 ms (  -4%)    68.8 MiB (  +0%)
       default_linsolvercreator                              73.8 ms (  -2%)    44.0 MiB (  +0%)
       Passing a linsolvercreator as argument                72.7 ms (  -4%)    44.0 MiB (  +0%)
   NLEIGS: Scalar                                             783 ms (  -1%)     473 MiB (  +0%)
     Polynomial                                               392 ms (  -1%)     232 MiB (  +0%)
     Fully rational                                           391 ms (  -1%)     241 MiB (  +0%)
   Interpolation                                              694 ms (  +2%)     377 MiB (  -0%)
     Random pep (original pep of degree 2)                    486 ms (  +3%)     290 MiB (  +0%)
     Random sparse pep (original pep of degree 2)             151 ms (  -4%)    68.2 MiB (  -0%)
     Random sparse dep                                       50.9 ms (  -4%)    17.6 MiB (  +0%)
-    Random dep                                              5.72 ms ( +94%)    1.07 MiB (  +0%)
   NLEIGS: NEP Types                                          488 ms (  -4%)     183 MiB (  +0%)
     Custom NEP type                                          174 ms (  -6%)     115 MiB (  +0%)
     PEP + SPMF                                              79.0 ms (  -5%)    17.1 MiB (  +0%)
     PEP + LowRankFactorizedNEP                              78.4 ms (  -4%)    17.1 MiB (  +0%)
     PEP                                                     78.3 ms (  -2%)    17.0 MiB (  +0%)
     SPMF_NEP                                                78.2 ms (  -4%)    17.0 MiB (  +0%)
   IAR                                                        461 ms (  +0%)    65.4 MiB (  +0%)
     orthogonalization                                        370 ms (  +0%)    52.4 MiB (  +0%)
       User provided doubleGS                                 108 ms (  -0%)    14.7 MiB (  +0%)
       DGKS                                                  92.8 ms (  -0%)    13.0 MiB (  +0%)
       ClassicalGramSchmidt                                  86.8 ms (  +1%)    12.5 MiB (  +0%)
       ModifiedGramSchmidt                                   82.4 ms (  -0%)    12.2 MiB (  +0%)
     accuracy eigenpairs                                     91.2 ms (  +1%)    12.9 MiB (  +0%)
   Gallery                                                    412 ms (  -4%)     129 MiB (  +0%)
   NLEIGS: Basic functionality                                409 ms (  -5%)    91.0 MiB (  -0%)
     return_details                                          80.2 ms (  -3%)    17.6 MiB (  +0%)
     Complex-valued start vector                             79.9 ms (  -2%)    17.5 MiB (  -0%)
     Complex-valued matrices                                 79.9 ms (  -4%)    17.5 MiB (  +0%)
     Non-convergent linearization (return_details)           78.8 ms (  -6%)    17.1 MiB (  -0%)
     Polynomial only                                         77.4 ms (  -7%)    17.0 MiB (  +0%)
     Non-convergent linearization (static)                   6.70 ms (  -5%)    2.16 MiB (  -0%)
     Non-convergent linearization                            6.47 ms (  -3%)    2.11 MiB (  +0%)
-  Beyn contour                                               360 ms ( +21%)    27.8 MiB (  +0%)
-    shifted disk                                             241 ms ( +65%)    14.0 MiB (  +0%)
+    disk at origin                                           119 ms ( -22%)    13.8 MiB (  +0%)
-  Inner Solves                                               199 ms ( +31%)    43.7 MiB (  +0%)
+  Eigenvector extraction (small scale)                      58.1 ms ( -14%)    54.8 MiB (  +0%)
     Test problem: pep0_sparse_003                           39.7 ms (  -8%)    29.5 MiB (  +0%)
       backslash_linsolvercreator                            13.6 ms (  -5%)    10.0 MiB (  +0%)
       Passing a linsolvercreator as argument                13.2 ms ( -10%)    9.74 MiB (  +0%)
       default_linsolvercreator                              12.9 ms (  -8%)    9.74 MiB (  +0%)
+    Test problem: pep0                                      18.3 ms ( -25%)    25.2 MiB (  +0%)
       default_linsolvercreator                              7.14 ms (  -9%)    7.09 MiB (  +0%)
+      backslash_linsolvercreator                            6.11 ms ( -29%)    11.1 MiB (  +0%)
+      Passing a linsolvercreator as argument                5.03 ms ( -36%)    7.09 MiB (  +0%)
-    Test problem: dep0                                       141 μs ( +41%)     111 KiB (  +0%)
-      backslash_linsolvercreator                            48.7 μs ( +43%)    39.9 KiB (  +0%)
-      default_linsolvercreator                              46.2 μs ( +41%)    35.4 KiB (  +0%)
-      Passing a linsolvercreator as argument                45.6 μs ( +38%)    35.5 KiB (  +0%)
   Deflation (combined with MSLP)                            40.3 ms (  +6%)    17.5 MiB (  +0%)
-  blocknewton                                               34.5 ms ( +25%)    4.78 MiB (  +0%)
-  broyden                                                   12.6 ms ( +13%)    4.95 MiB (  +0%)
   compute_types                                             12.2 ms (  +1%)    6.37 MiB (  +0%)
     PEP (BigFloat)                                          1.81 ms (  -6%)    1.35 MiB (  +0%)
     DEP (BigFloat)                                          1.47 ms (  -7%)    0.98 MiB (  +0%)
-    DEP sparse (Float64)                                    1.31 ms ( +45%)     437 KiB (  +0%)
-    DEP (Float64)                                           1.20 ms ( +16%)     529 KiB (  +0%)
+    SPMFSumNEP (Complex{Float64})                           1.15 ms ( -12%)     402 KiB (  +0%)
     DEP (Complex{BigFloat})                                 1.14 ms (  -2%)     874 KiB (  +0%)
-    SPMF_NEP #4 (Complex{Float64})                           794 μs ( +14%)     328 KiB (  +0%)
     SPMF_NEP #2 (Complex{Float64})                           790 μs (  +5%)     328 KiB (  +0%)
+    PEP (Complex{Float32})                                   762 μs ( -15%)     322 KiB (  +0%)
     PEP (Float64)                                            758 μs (  +9%)     353 KiB (  +0%)
+    SPMF_NEP #1 (Float64)                                    735 μs ( -12%)     319 KiB (  +0%)
-    SPMF_NEP #3 (BigFloat)                                   317 μs ( +15%)     242 KiB (  +0%)
-  sgiter                                                    2.26 ms ( +42%)     290 KiB (  +0%)
   SPMF                                                      1.81 ms (  +7%)     939 KiB (  +0%)
+    compute_Mder_from_MM                                     609 μs ( -15%)     331 KiB (  +0%)
     compute_MM                                               431 μs (  +5%)     140 KiB (  +0%)
-    REP                                                      222 μs ( +33%)     187 KiB (  +0%)
-    Compute_Mlincomb                                         220 μs ( +24%)     106 KiB (  +0%)
-    DEP                                                      182 μs ( +59%)    87.1 KiB (  +0%)
-    PEP                                                      149 μs ( +42%)    88.0 KiB (  +0%)
-  discretizepolygon                                         1.43 ms ( +23%)     633 KiB (  +0%)
-    unit disk                                                866 μs ( +20%)     238 KiB (  +0%)
-    concave polygon                                          294 μs ( +12%)     281 KiB (  +0%)
-    too narrow Σ                                             175 μs ( +72%)    29.8 KiB (  +0%)
-    narrow Σ                                                54.0 μs ( +34%)    34.2 KiB (  +0%)
-    Chebyshev points                                        42.6 μs ( +12%)    50.2 KiB (  +0%)
-  MSLP                                                       983 μs ( +22%)     476 KiB (  +0%)
-    mslp + double                                            983 μs ( +22%)     476 KiB (  +0%)
-  Core                                                       407 μs ( +42%)    65.3 KiB (  +0%)
-  cached_lu_solver                                           306 μs ( +15%)     203 KiB (  +0%)
-  Serialization                                              177 μs ( +26%)    79.5 KiB (  -0%)
-  inpolygon                                                 52.1 μs ( +19%)    33.2 KiB (  +0%)
-  Types (sumnep)                                            35.4 μs ( +28%)    32.8 KiB (  +0%)
 ───────────────────────────────────────────────────────────────────────────────────────────────
```
Previous context:
```
UTC time: 2018-09-13 22:24:14
Commit: 81a1f7f12cc7e0643779151e2696055f6a386c96
Message: Run all tests
Travis build: 689

Julia Version 1.0.0
Commit 5d4eaca0c9 (2018-08-08 20:58 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 14.04.5 LTS
  uname: Linux 4.4.0-101-generic #124~14.04.1-Ubuntu SMP Fri Nov 10 19:05:36 UTC 2017 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU @ 2.50GHz: 
              speed         user         nice          sys         idle          irq
       #1  2500 MHz      68385 s          0 s      19172 s      48980 s          0 s
       #2  2500 MHz      83216 s          0 s      17584 s      35976 s          0 s
       
  Memory: 7.304546356201172 GB (4880.89453125 MB free)
  Uptime: 1374.0 sec
  Load Avg:  1.44775390625  1.46240234375  1.12890625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, ivybridge)
Environment:
  TRAVIS_JULIA_VERSION = 1.0
  JULIA_LOAD_PATH = @:/tmp/tmpaUcKVm
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
  JULIA_LOAD_PATH = @:/tmp/tmpaUcKVm
```
Current context:
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
