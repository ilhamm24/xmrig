# HYCminer

HYCminer is a high performance Hycon (HYC) CPU miner, forked from [XMRig](https://github.com/xmrig/xmrig) release v2.5.3.

* This is the **CPU-mining** version, there is also a [NVIDIA GPU version](https://bitbucket.org/glosfer/miner-nvidia) and [AMD GPU version](https://bitbucket.org/glosfer/miner-amd).
* We plan on releasing our roadmap for next releases soon.

#### Table of contents
* [Features](#features)
* [Download](#download)
* [Usage](#usage)
* [Algorithm variations](#algorithm-variations)
* [Build](https://bitbucket.org/glosfer/cpu-miner/wiki/Build)
* [Common Issues](#common-issues)
* [Other information](#other-information)
* [Contacts](#contacts)

## Features
* Currently running Cryptonight v7
* High performance.
* Small Windows executable, without dependencies.
* x86/x64 support.
* Support for backup (failover) mining server.
* keepalived support.
* Command line options compatible with cpuminer.
* Smart automatic [CPU configuration](https://bitbucket.org/glosfer/cpu-miner/wiki/Threads).
* Nicehash support
* It's open source software.

## Download
* Binary releases: TBA
* Git tree: https://bitbucket.org/glosfer/cpu-miner.git
    * Clone with `git clone https://bitbucket.org/glosfer/cpu-miner.git` :hammer: [Build instructions](https://bitbucket.org/glosfer/cpu-miner/wiki/Build).

## Usage
See the example `config.json` to configure the miner.

### Options
```
  -a, --algo=ALGO          cryptonight (default) or cryptonight-lite
  -o, --url=URL            URL of mining server
  -O, --userpass=U:P       username:password pair for mining server
  -u, --user=USERNAME      username for mining server
  -p, --pass=PASSWORD      password for mining server
  -t, --threads=N          number of miner threads
  -v, --av=N               algorithm variation, 0 auto select
  -k, --keepalive          send keepalived for prevent timeout (need pool support)
  -r, --retries=N          number of times to retry before switch to backup server (default: 5)
  -R, --retry-pause=N      time to pause between retries (default: 5)
      --cpu-affinity       set process affinity to CPU core(s), mask 0x3 for cores 0 and 1
      --cpu-priority       set process priority (0 idle, 2 normal to 5 highest)
      --no-huge-pages      disable huge pages support
      --no-color           disable colored output
      --variant            algorithm PoW variant
      --donate-level=N     donate level, default 5% (5 minutes in 100 minutes)
      --user-agent         set custom user-agent string for pool
  -B, --background         run the miner in the background
  -c, --config=FILE        load a JSON-format configuration file
  -l, --log-file=FILE      log all output to a file
  -S, --syslog             use system log for output messages
      --max-cpu-usage=N    maximum CPU usage for automatic threads mode (default 75)
      --safe               safe adjust threads and av settings for current CPU
      --nicehash           enable nicehash/xmrig-proxy support
      --print-time=N       print hashrate report every N seconds
      --api-port=N         port for the miner API
      --api-access-token=T access token for API
      --api-worker-id=ID   custom worker-id for API
  -h, --help               display this help and exit
  -V, --version            output version information and exit
```

Also you can use configuration via config file, default **config.json**. You can load multiple config files and combine it with command line options.

## Algorithm variations
Since version 0.8.0.
* `--av=1` For CPUs with hardware AES.
* `--av=2` Lower power mode (double hash) of `1`.
* `--av=3` Software AES implementation.
* `--av=4` Lower power mode (double hash) of `3`.

## Common Issues
### HUGE PAGES unavailable
* Run HYCminer as Administrator.
* Since version 0.8.0 HYCminer automatically enables SeLockMemoryPrivilege for current user, but reboot or sign out still required. [Manual instruction](https://msdn.microsoft.com/en-gb/library/ms190730.aspx).

## Other information
* No HTTP support, only stratum protocol support.
* No TLS support.
* Default donation 5% (5 minutes in 100 minutes) can be reduced to 1% via command line option `--donate-level`.


### CPU mining performance
* **Intel i7-7700** - 307 H/s (4 threads)
* **AMD Ryzen 7 1700X** - 560 H/s (8 threads)

Please note performance is highly dependent on system load. The numbers above are obtained on an idle system. Tasks heavily using a processor cache, such as video playback, can greatly degrade hashrate. Optimal number of threads depends on the size of the L3 cache of a processor, 1 thread requires 2 MB of cache.

### Maximum performance checklist
* Idle operating system.
* Do not exceed optimal thread count.
* Use modern CPUs with AES-NI instruction set.
* Try setup optimal cpu affinity.
* Enable fast memory (Large/Huge pages).

<<<<<<< HEAD
## Donations
* XMR: `48edfHu7V9Z84YzzMa6fUueoELZ9ZRXq9VetWzYGzKt52XU5xvqgzYnDK9URnRoJMk1j8nLwEVsaSWJ4fhdUyZijBGUicoD`
* BTC: `1P7ujsXeX7GxQwHNnJsRMgAdNkFZmNVqJT`

## Release checksums
### SHA-256
```
dbc2b0f92df5098dc91a361febfda46382d347ae3085415f35e1637b7ebc67e9 xmrig-2.6.3-xenial-amd64.tar.gz/xmrig-2.6.3/xmrig
b54ffe80cd54ac486f03f064c09de80b6ec29f19ddebb50a8d7316a947045b85 xmrig-2.6.3-gcc-win32.zip/xmrig.exe
c828ed21bbaf71a808b26928ab1eb6f6355029f2b731a639043733e6b48e9d77 xmrig-2.6.3-gcc-win64.zip/xmrig.exe
2e7432d14546b510506ccc22df62ef334d424d02fbc6baaa7a0498a0102de156 xmrig-2.6.3-msvc-win64.zip/xmrig.exe
```

=======
>>>>>>> Updated README, include config.json during build
## Contacts
* hycon@glosfer.com
* [site](https://www.hycon.io)
* [reddit](https://www.reddit.com/r/HYCON)
* [facebook](https://www.facebook.com/teamHycon)
* [instagram](https://www.instagram.com/teamhycon)
* [medium](https://www.medium.com/@teamhycon)
* [twitter](https://www.twitter.com/teamhycon)