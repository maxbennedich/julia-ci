### Include comparisons in report
commit [12b1991749c5f3f03a0ca5cc64e4e150fae92f7e](https://github.com/nep-pack/NonlinearEigenproblems.jl/commit/12b1991749c5f3f03a0ca5cc64e4e150fae92f7e)
```diff
 ───────────────────────────────────────────────────────────
 Test name                    Time               Memory
 ───────────────────────────────────────────────────────────
 All tests               1.17 ms (  +4%)     666 KiB (  +0%)
   discretizepolygon     1.12 ms (  +4%)     633 KiB (  +0%)
     unit disk            742 μs (  +6%)     238 KiB (  +0%)
     concave polygon      238 μs (  +1%)     281 KiB (  +0%)
     too narrow Σ        65.3 μs (  -2%)    29.8 KiB (  +0%)
     narrow Σ            38.8 μs (  -2%)    34.2 KiB (  +0%)
     Chebyshev points    37.0 μs (  -0%)    50.2 KiB (  +0%)
   inpolygon             44.1 μs (  -0%)    33.2 KiB (  +0%)
 ───────────────────────────────────────────────────────────
```
Previous context:
```
UTC time: 2018-09-13 19:25:24
Commit: unit
Message: N/A
Travis build: N/A

Julia Version 1.0.0
Commit 5d4eaca0c9 (2018-08-08 20:58 UTC)
Platform Info:
  OS: macOS (x86_64-apple-darwin14.5.0)
  uname: Darwin 17.4.0 Darwin Kernel Version 17.4.0: Sun Dec 17 09:19:54 PST 2017; root:xnu-4570.41.2~1/RELEASE_X86_64 x86_64 i386
  CPU: Intel(R) Core(TM) i7-6920HQ CPU @ 2.90GHz: 
              speed         user         nice          sys         idle          irq
       #1  2900 MHz     729973 s          0 s     366288 s    4860320 s          0 s
       #2  2900 MHz      85539 s          0 s      40892 s    5827193 s          0 s
       #3  2900 MHz     688590 s          0 s     236710 s    5028352 s          0 s
       #4  2900 MHz      86626 s          0 s      42420 s    5824568 s          0 s
       #5  2900 MHz     698271 s          0 s     240673 s    5014698 s          0 s
       #6  2900 MHz      86022 s          0 s      42402 s    5825181 s          0 s
       #7  2900 MHz     682607 s          0 s     234234 s    5036793 s          0 s
       #8  2900 MHz      86303 s          0 s      42543 s    5824750 s          0 s
       
  Memory: 16.0 GB (197.52734375 MB free)
  Uptime: 1.849116e6 sec
  Load Avg:  3.1689453125  2.24560546875  2.1220703125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-6.0.0 (ORCJIT, skylake)
Environment:
  JULIA_NUM_THREADS = 8
```
Current context:
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
