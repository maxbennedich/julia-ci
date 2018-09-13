### Run all tests
commit [81a1f7f12cc7e0643779151e2696055f6a386c96](https://github.com/nep-pack/NonlinearEigenproblems.jl/commit/81a1f7f12cc7e0643779151e2696055f6a386c96)
```diff
 ───────────────────────────────────────────────────────────────────────────────────────────────
 Test name                                                        Time               Memory
 ───────────────────────────────────────────────────────────────────────────────────────────────
-All tests                                                     256 s (+22112570%)    63.5 GiB (+9992754%)
   Nonlinear Arnoldi                                          67.0 s ( --- )    12.7 GiB ( --- )
   NLEIGS: Gun variant R2                                     42.3 s ( --- )    6.75 GiB ( --- )
   NLEIGS: Particle variant R2                                23.8 s ( --- )    7.09 GiB ( --- )
   IAR Chebyshev version                                      17.9 s ( --- )    2.93 GiB ( --- )
     compute_y0_method for different types                    17.8 s ( --- )    2.89 GiB ( --- )
       DEP SHIFTED AND SCALED                                 6.40 s ( --- )     556 MiB ( --- )
       DEP WITH GENERIC Y0                                    4.43 s ( --- )     514 MiB ( --- )
       PEP in SPMF format                                     2.68 s ( --- )     607 MiB ( --- )
       DEP format with ComputeY0ChebSPMF_NEP                  2.05 s ( --- )     758 MiB ( --- )
       PEP format with ComputeY0ChebSPMF_NEP                  494 ms ( --- )    83.0 MiB ( --- )
       DEP WITH DELAYS>1                                      409 ms ( --- )     155 MiB ( --- )
       QDEP IN SPMF format                                    344 ms ( --- )    77.6 MiB ( --- )
       PEP SHIFTED AND SCALED                                 328 ms ( --- )    63.1 MiB ( --- )
       compute_y0 AS INPUT FOR QEP (naive)                    305 ms ( --- )    70.4 MiB ( --- )
       PEP                                                    287 ms ( --- )    56.4 MiB ( --- )
       compute_y0 AS INPUT FOR QDEP (combine DEP and PEP)    94.3 ms ( --- )    21.6 MiB ( --- )
     orthogonalization                                       66.5 ms ( --- )    20.8 MiB ( --- )
       DGKS                                                  16.9 ms ( --- )    5.16 MiB ( --- )
       User provided doubleGS                                16.7 ms ( --- )    5.34 MiB ( --- )
       ModifiedGramSchmidt                                   16.5 ms ( --- )    5.17 MiB ( --- )
       ClassicalGramSchmidt                                  16.4 ms ( --- )    5.14 MiB ( --- )
     Scale Cheb's to different interval w DEP                37.7 ms ( --- )    9.12 MiB ( --- )
     accuracy eigenpairs                                     16.6 ms ( --- )    5.16 MiB ( --- )
   NLEIGS: Particle variant S                                 17.6 s ( --- )    8.40 GiB ( --- )
   WEP                                                        14.8 s ( --- )    8.31 GiB ( --- )
   NLEIGS: Gun variant R1                                     11.5 s ( --- )    1.90 GiB ( --- )
   NLEIGS: Gun variant P                                      11.3 s ( --- )    1.88 GiB ( --- )
   NLEIGS: Gun variant S                                      11.3 s ( --- )    2.23 GiB ( --- )
   linsolvers                                                 5.93 s ( --- )     912 MiB ( --- )
   TIAR                                                       5.82 s ( --- )    2.50 GiB ( --- )
     Solve by projection                                      4.06 s ( --- )    1.61 GiB ( --- )
     orthogonalization                                        1.03 s ( --- )     544 MiB ( --- )
       ModifiedGramSchmidt                                    259 ms ( --- )     136 MiB ( --- )
       DGKS                                                   258 ms ( --- )     136 MiB ( --- )
       User provided doubleGS                                 257 ms ( --- )     136 MiB ( --- )
       ClassicalGramSchmidt                                   256 ms ( --- )     136 MiB ( --- )
     equivalance with IAR                                     471 ms ( --- )     228 MiB ( --- )
     accuracy eigenpairs                                      255 ms ( --- )     136 MiB ( --- )
   Newton iterations                                          5.40 s ( --- )    1.36 GiB ( --- )
     implicitdet                                              3.17 s ( --- )     864 MiB ( --- )
     Resinv                                                   2.21 s ( --- )     527 MiB ( --- )
     QuasiNewton                                             7.96 ms ( --- )    1.67 MiB ( --- )
     Rayleigh Function Iteration                             4.20 ms ( --- )    1.89 MiB ( --- )
     Newton QR                                               3.94 ms ( --- )    1.82 MiB ( --- )
     Newton and AugNewton                                    1.52 ms ( --- )     428 KiB ( --- )
   transformations                                            4.14 s ( --- )     731 MiB ( --- )
     Shift and scale                                          3.11 s ( --- )     601 MiB ( --- )
     Möbius transformation                                    1.02 s ( --- )     130 MiB ( --- )
   PeriodicDDE                                                2.75 s ( --- )     911 MiB ( --- )
   Infbilanczos σ=0                                           2.24 s ( --- )    1.42 GiB ( --- )
   Jacobi–Davidson                                            2.07 s ( --- )     460 MiB ( --- )
     Effenberger                                              1.53 s ( --- )     409 MiB ( --- )
     Betcke-Voss                                              540 ms ( --- )    51.4 MiB ( --- )
   Companion Linearization                                    1.99 s ( --- )     248 MiB ( --- )
   compute eigvec lopcg                                       1.97 s ( --- )     559 MiB ( --- )
     pep0                                                     1.51 s ( --- )     272 MiB ( --- )
     dep0_sparse                                              460 ms ( --- )     287 MiB ( --- )
   GUN (native)                                               1.80 s ( --- )     306 MiB ( --- )
     Running algorithm                                        1.79 s ( --- )     297 MiB ( --- )
     Compute derivatives                                     13.2 ms ( --- )    9.70 MiB ( --- )
   Eigenvector extraction (medium/large scale)                950 ms ( --- )     553 MiB ( --- )
     Test problem: pep0_sparse_003                            467 ms ( --- )     226 MiB ( --- )
       backslash_linsolvercreator                             160 ms ( --- )    76.3 MiB ( --- )
       default_linsolvercreator                               154 ms ( --- )    74.7 MiB ( --- )
       Passing a linsolvercreator as argument                 153 ms ( --- )    74.7 MiB ( --- )
     Test problem: dep0                                       245 ms ( --- )     170 MiB ( --- )
       backslash_linsolvercreator                            90.1 ms ( --- )    74.5 MiB ( --- )
       Passing a linsolvercreator as argument                78.2 ms ( --- )    47.8 MiB ( --- )
       default_linsolvercreator                              77.2 ms ( --- )    47.8 MiB ( --- )
     Test problem: pep0                                       237 ms ( --- )     157 MiB ( --- )
       backslash_linsolvercreator                            86.3 ms ( --- )    68.8 MiB ( --- )
       Passing a linsolvercreator as argument                75.6 ms ( --- )    44.0 MiB ( --- )
       default_linsolvercreator                              75.0 ms ( --- )    44.0 MiB ( --- )
   NLEIGS: Scalar                                             791 ms ( --- )     473 MiB ( --- )
     Polynomial                                               397 ms ( --- )     232 MiB ( --- )
     Fully rational                                           393 ms ( --- )     241 MiB ( --- )
   Interpolation                                              683 ms ( --- )     377 MiB ( --- )
     Random pep (original pep of degree 2)                    470 ms ( --- )     290 MiB ( --- )
     Random sparse pep (original pep of degree 2)             157 ms ( --- )    68.2 MiB ( --- )
     Random sparse dep                                       53.0 ms ( --- )    17.6 MiB ( --- )
     Random dep                                              2.95 ms ( --- )    1.07 MiB ( --- )
   NLEIGS: NEP Types                                          511 ms ( --- )     183 MiB ( --- )
     Custom NEP type                                          185 ms ( --- )     115 MiB ( --- )
     PEP + SPMF                                              83.1 ms ( --- )    17.1 MiB ( --- )
     SPMF_NEP                                                81.6 ms ( --- )    17.0 MiB ( --- )
     PEP + LowRankFactorizedNEP                              81.5 ms ( --- )    17.1 MiB ( --- )
     PEP                                                     79.8 ms ( --- )    17.0 MiB ( --- )
   IAR                                                        460 ms ( --- )    65.4 MiB ( --- )
     orthogonalization                                        370 ms ( --- )    52.4 MiB ( --- )
       User provided doubleGS                                 108 ms ( --- )    14.7 MiB ( --- )
       DGKS                                                  92.8 ms ( --- )    13.0 MiB ( --- )
       ClassicalGramSchmidt                                  85.8 ms ( --- )    12.5 MiB ( --- )
       ModifiedGramSchmidt                                   82.6 ms ( --- )    12.2 MiB ( --- )
     accuracy eigenpairs                                     90.4 ms ( --- )    12.9 MiB ( --- )
   Gallery                                                    431 ms ( --- )     129 MiB ( --- )
   NLEIGS: Basic functionality                                429 ms ( --- )    91.0 MiB ( --- )
     Non-convergent linearization (return_details)           83.7 ms ( --- )    17.1 MiB ( --- )
     Complex-valued matrices                                 83.5 ms ( --- )    17.5 MiB ( --- )
     Polynomial only                                         83.4 ms ( --- )    17.0 MiB ( --- )
     return_details                                          83.0 ms ( --- )    17.6 MiB ( --- )
     Complex-valued start vector                             81.7 ms ( --- )    17.5 MiB ( --- )
     Non-convergent linearization (static)                   7.03 ms ( --- )    2.16 MiB ( --- )
     Non-convergent linearization                            6.65 ms ( --- )    2.11 MiB ( --- )
   Beyn contour                                               298 ms ( --- )    27.8 MiB ( --- )
     disk at origin                                           152 ms ( --- )    13.8 MiB ( --- )
     shifted disk                                             146 ms ( --- )    14.0 MiB ( --- )
   Inner Solves                                               152 ms ( --- )    43.7 MiB ( --- )
   Eigenvector extraction (small scale)                      67.4 ms ( --- )    54.8 MiB ( --- )
     Test problem: pep0_sparse_003                           43.0 ms ( --- )    29.5 MiB ( --- )
       Passing a linsolvercreator as argument                14.6 ms ( --- )    9.74 MiB ( --- )
       backslash_linsolvercreator                            14.3 ms ( --- )    10.0 MiB ( --- )
       default_linsolvercreator                              14.1 ms ( --- )    9.74 MiB ( --- )
     Test problem: pep0                                      24.4 ms ( --- )    25.2 MiB ( --- )
       backslash_linsolvercreator                            8.60 ms ( --- )    11.1 MiB ( --- )
       default_linsolvercreator                              7.88 ms ( --- )    7.09 MiB ( --- )
       Passing a linsolvercreator as argument                7.87 ms ( --- )    7.09 MiB ( --- )
     Test problem: dep0                                       100 μs ( --- )     111 KiB ( --- )
       backslash_linsolvercreator                            34.2 μs ( --- )    39.9 KiB ( --- )
       Passing a linsolvercreator as argument                33.0 μs ( --- )    35.5 KiB ( --- )
       default_linsolvercreator                              32.7 μs ( --- )    35.4 KiB ( --- )
   Deflation (combined with MSLP)                            38.2 ms ( --- )    17.5 MiB ( --- )
   blocknewton                                               27.7 ms ( --- )    4.78 MiB ( --- )
   compute_types                                             12.1 ms ( --- )    6.37 MiB ( --- )
     PEP (BigFloat)                                          1.92 ms ( --- )    1.35 MiB ( --- )
     DEP (BigFloat)                                          1.59 ms ( --- )    0.98 MiB ( --- )
     SPMFSumNEP (Complex{Float64})                           1.30 ms ( --- )     402 KiB ( --- )
     DEP (Complex{BigFloat})                                 1.15 ms ( --- )     874 KiB ( --- )
     DEP (Float64)                                           1.04 ms ( --- )     529 KiB ( --- )
     DEP sparse (Float64)                                     903 μs ( --- )     437 KiB ( --- )
     PEP (Complex{Float32})                                   895 μs ( --- )     322 KiB ( --- )
     SPMF_NEP #1 (Float64)                                    839 μs ( --- )     319 KiB ( --- )
     SPMF_NEP #2 (Complex{Float64})                           754 μs ( --- )     328 KiB ( --- )
     SPMF_NEP #4 (Complex{Float64})                           699 μs ( --- )     328 KiB ( --- )
     PEP (Float64)                                            697 μs ( --- )     353 KiB ( --- )
     SPMF_NEP #3 (BigFloat)                                   276 μs ( --- )     242 KiB ( --- )
   broyden                                                   11.2 ms ( --- )    4.95 MiB ( --- )
   SPMF                                                      1.69 ms ( --- )     939 KiB ( --- )
     compute_Mder_from_MM                                     716 μs ( --- )     331 KiB ( --- )
     compute_MM                                               409 μs ( --- )     140 KiB ( --- )
     Compute_Mlincomb                                         178 μs ( --- )     106 KiB ( --- )
     REP                                                      168 μs ( --- )     187 KiB ( --- )
     DEP                                                      114 μs ( --- )    87.1 KiB ( --- )
     PEP                                                      105 μs ( --- )    88.0 KiB ( --- )
   sgiter                                                    1.59 ms ( --- )     290 KiB ( --- )
   discretizepolygon                                         1.16 ms (  +4%)     633 KiB (  +0%)
     unit disk                                                719 μs (  -2%)     238 KiB (  +0%)
-    concave polygon                                          262 μs ( +11%)     281 KiB (  +0%)
-    too narrow Σ                                             101 μs ( +54%)    29.8 KiB (  +0%)
     narrow Σ                                                40.4 μs (  +2%)    34.2 KiB (  +0%)
     Chebyshev points                                        38.1 μs (  -5%)    50.2 KiB (  +0%)
   MSLP                                                       809 μs ( --- )     476 KiB ( --- )
     mslp + double                                            809 μs ( --- )     476 KiB ( --- )
   Core                                                       287 μs ( --- )    65.3 KiB ( --- )
   cached_lu_solver                                           266 μs ( --- )     203 KiB ( --- )
   Serialization                                              140 μs ( --- )    79.7 KiB ( --- )
   inpolygon                                                 43.8 μs (  -3%)    33.2 KiB (  +0%)
   Types (sumnep)                                            27.6 μs ( --- )    32.8 KiB ( --- )
 ───────────────────────────────────────────────────────────────────────────────────────────────
```
Previous context:
```
UTC time: 2018-09-13 21:57:43
Commit: cd816dc22610961741684965b5b922c3dcc0eb3a
Message: Merge branch 'master' into benchmarks
Travis build: 688

Julia Version 1.0.0
Commit 5d4eaca0c9 (2018-08-08 20:58 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 14.04.5 LTS
  uname: Linux 4.4.0-101-generic #124~14.04.1-Ubuntu SMP Fri Nov 10 19:05:36 UTC 2017 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU @ 2.50GHz: 
              speed         user         nice          sys         idle          irq
       #1  2500 MHz       2592 s          0 s        748 s       9168 s          0 s
       #2  2500 MHz       6377 s          0 s        693 s       5547 s          0 s
       
  Memory: 7.304546356201172 GB (5862.6171875 MB free)
  Uptime: 131.0 sec
  Load Avg:  0.9140625  0.36962890625  0.13916015625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, ivybridge)
Environment:
  TRAVIS_JULIA_VERSION = 1.0
  JULIA_LOAD_PATH = @:/tmp/tmpOGqOys
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
  JULIA_LOAD_PATH = @:/tmp/tmpOGqOys
```
Current context:
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
