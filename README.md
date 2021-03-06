# TouDoum-Framework

## Imported and renowned from msterhuj/TouDoum-DDoS-Exploit

## DISCLAIMER
* The application is currently being completely redesigned with a system of plug-ins, saving scan results

* The documentation is not up to date 

* Use this branch at your own risk

## OLD Docs
> This script can scan ip's or retrieve them from shodan and then scan them for vulnerabilities and use them to carry out large ddos attacks.
> This script uses the amplification technologies of:
> * memcached [POC](https://www.cloudflare.com/learning/ddos/memcached-ddos-attack/)
> * ntp [POC](https://www.cloudflare.com/learning/ddos/ntp-amplification-ddos-attack/)
> * dns [POC](https://www.cloudflare.com/learning/ddos/dns-amplification-ddos-attack/)
>
>I am NOT responsible for damages caused or crimes committed by the use of this tool. 

## Installation

### Remember
> You need to run this script with root privileges and run this tool on machine with public ip for attack (spoffing)
```shell script
git clone https://github.com/msterhuj/TouDoum-DDoS-Exploit
cd TouDoum-DDoS-Exploit
pip3 install -r requirements.txt
```

## Using

### There are two ways to use this tool

#### Option One CLI for scan and attack
> The disadvantage that the scanner only works with a core for a faster scan use option 2
```shell script
python3 TouDoum.py
```
```
▄▄▄█████▓ ▒█████   █    ██    ▓█████▄  ▒█████   █    ██  ███▄ ▄███▓    ▐██▌ 
▓  ██▒ ▓▒▒██▒  ██▒ ██  ▓██▒   ▒██▀ ██▌▒██▒  ██▒ ██  ▓██▒▓██▒▀█▀ ██▒    ▐██▌ 
▒ ▓██░ ▒░▒██░  ██▒▓██  ▒██░   ░██   █▌▒██░  ██▒▓██  ▒██░▓██    ▓██░    ▐██▌ 
░ ▓██▓ ░ ▒██   ██░▓▓█  ░██░   ░▓█▄   ▌▒██   ██░▓▓█  ░██░▒██    ▒██     ▓██▒ 
  ▒██▒ ░ ░ ████▓▒░▒▒█████▓    ░▒████▓ ░ ████▓▒░▒▒█████▓ ▒██▒   ░██▒    ▒▄▄  
  ▒ ░░   ░ ▒░▒░▒░ ░▒▓▒ ▒ ▒     ▒▒▓  ▒ ░ ▒░▒░▒░ ░▒▓▒ ▒ ▒ ░ ▒░   ░  ░    ░▀▀▒ 
    ░      ░ ▒ ▒░ ░░▒░ ░ ░     ░ ▒  ▒   ░ ▒ ▒░ ░░▒░ ░ ░ ░  ░      ░    ░  ░ 
  ░      ░ ░ ░ ▒   ░░░ ░ ░     ░ ░  ░ ░ ░ ░ ▒   ░░░ ░ ░ ░      ░          ░ 
             ░ ░     ░           ░        ░ ░     ░            ░       ░    
                               ░                
                    ---===[Author: @MsterHuj]===---
                          --==[Ver : X.X]==--

Usage: TouDoum.py [OPTIONS] COMMAND [ARGS]...

Options:
  --help  Show this message and exit.

Commands:
  attack   Attack server with spoofed udp packed
  scanner  Scanner for detect udp port on memcached, dns and ntp
```

#### Option two Docker
For a more efficient scan you can use the compose docker at the root of this repo.
Edit var environments in docker-compose.yml, build, and run compose
````shell script
docker-compose build
docker-compose up # add -d for run this compose in background
````
You can scale the client for more efficiency
````shell script
docker-compose --scale client=X # X is number of client for scan you want to run
````

One web ui is available for show all data from this scan on http://<docker ip>:8081

## Features
* scan range of ip with cli or docker stack
* get ip from shodan.io (only cli)
* import ip from file (one ip per line and only cli)
* scan by service type (memcache, ntp, dns) with udp protocol
* attack with multi thread and multiple service type scanned before (only cli)

## Future update
* rewrite function for get ip on shodan.io
* build a REST API with flask
* full implementation of mongodb
* plugin system for add more scanner function
* add a drive for storage ip system (mongo, .json file)

## Credit for dev
* [Dns UDP port checker](https://stackoverflow.com/a/51970598)
