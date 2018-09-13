### Merge branch 'master' into benchmarks
commit [cd816dc22610961741684965b5b922c3dcc0eb3a](https://github.com/nep-pack/NonlinearEigenproblems.jl/commit/cd816dc22610961741684965b5b922c3dcc0eb3a)
```diff
 ───────────────────────────────────────────────────────────
 Test name                    Time               Memory
 ───────────────────────────────────────────────────────────
 All tests               1.16 ms (  -0%)     666 KiB (  +0%)
   discretizepolygon     1.11 ms (  -1%)     633 KiB (  +0%)
     unit disk            734 μs (  -1%)     238 KiB (  +0%)
     concave polygon      236 μs (  -1%)     281 KiB (  +0%)
     too narrow Σ        65.8 μs (  +1%)    29.8 KiB (  +0%)
     Chebyshev points    40.0 μs (  +8%)    50.2 KiB (  +0%)
     narrow Σ            39.4 μs (  +2%)    34.2 KiB (  +0%)
   inpolygon             44.9 μs (  +2%)    33.2 KiB (  +0%)
 ───────────────────────────────────────────────────────────
```
Previous context:
```
UTC time: 2018-09-13 20:55:40
Commit: 12b1991749c5f3f03a0ca5cc64e4e150fae92f7e
Message: Include comparisons in report
Travis build: 686

Julia Version 1.0.0
Commit 5d4eaca0c9 (2018-08-08 20:58 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 14.04.5 LTS
  uname: Linux 4.4.0-101-generic #124~14.04.1-Ubuntu SMP Fri Nov 10 19:05:36 UTC 2017 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2300 MHz       5866 s          0 s        871 s       6044 s          0 s
       #2  2300 MHz       3354 s          0 s        645 s       8965 s          0 s
       
  Memory: 7.304546356201172 GB (5862.16015625 MB free)
  Uptime: 134.0 sec
  Load Avg:  0.9072265625  0.3349609375  0.12353515625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, haswell)
Environment:
  TRAVIS_JULIA_VERSION = 1.0
  JULIA_LOAD_PATH = @:/tmp/tmpuwZH32
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
  JULIA_LOAD_PATH = @:/tmp/tmpuwZH32
```
Current context:
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
