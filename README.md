# HYCminer

HYCminer is a high performance Hycon (HYC) CPU miner, forked from [XMRig](https://github.com/xmrig/xmrig) release v2.6.3.

* This is the **CPU-mining** version, there is also a [NVIDIA GPU version](https://github.com/team-hycon/xmrig-nvidia) and [AMD GPU version](https://github.com/team-hycon/xmrig-amd).
* We plan on releasing our roadmap for next releases soon.

#### Table of contents
* [Features](#features)
* [Download](#download)
* [Usage](#usage)
* [Algorithm variations](#algorithm-variations)
* [Build](https://github.com/team-hycon/xmrig/wiki/Build)
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
* Smart automatic [CPU configuration](https://github.com/team-hycon/xmrig/wiki/Threads).
* Nicehash support
* It's open source software.

## Download
* Binary releases: TBA
* Git tree: https://github.com/team-hycon/cpu-miner.git
    * Clone with `git clone https://github.com/team-hycon/cpu-miner.git` :hammer: [Build instructions](https://github.com/team-hycon/xmrig/wiki/Build).

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

## SHA256 for Windows Binary files
    9ac62cf597973365a55715f993e7333f6d4f0ee8e1c92616a4dd97014e50d08f: certUtil -hashfile hycon-win-0.0.1-without-mhttpd/xmrig.exe sha256
    1b0100df98846ad03f8eed073fd578b83366417c696cab4261d55ad213a5166e: certUtil -hashfile hycon-win-0.0.1/xmrig.exe sha256

## Contacts
* hycon@glosfer.com
* [site](https://www.hycon.io)
* [reddit](https://www.reddit.com/r/HYCON)
* [facebook](https://www.facebook.com/teamHycon)
* [instagram](https://www.instagram.com/teamhycon)
* [medium](https://www.medium.com/@teamhycon)
* [twitter](https://www.twitter.com/teamhycon)