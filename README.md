Fork of: https://github.com/crypto-jeronimo/pyminer <br>
Changes: 

- Removed Scrypt hashing and added Miner class
- Made it work with Python3
- added [PiAxe](https://github.com/shufps/piaxe) as miner
- added reconnect logic on broken connections

Influx and Grafana
==================

The repository contains a dockered setup running on the Pi that shows some statistics:

<img src="https://github.com/shufps/piaxe-miner/assets/3079832/28b80a15-aed1-429e-ba35-7a35026768e3" width="600px"/>


PyMiner
=======

Currently supported algorithms:
- `sha256d`: SHA256d


Usage
-----
```
    python pyminer.py [-h] [-o URL] [-u USERNAME] [-p PASSWORD]
                         [-O USERNAME:PASSWORD] [-a ALGO] [-B] [-q]
                         [-P] [-d] [-v]

    -o URL, --url=              stratum mining server url
    -u USERNAME, --user=        username for mining server
    -p PASSWORD, --pass=        password for mining server
    -O USER:PASS, --userpass=   username:password pair for mining server

    -B, --background            run in the background as a daemon

    -q, --quiet                 suppress non-errors
    -P, --dump-protocol         show all JSON-RPC chatter
    -d, --debug                 show extra debug information

    -h, --help                  show the help message and exit
    -v, --version               show program's version number and exit


    Example:
        python pyminer.py -o stratum+tcp://foobar.com:3333 -u user -p passwd
```



Misc:
```
$ curl --user bitcoin --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "createwallet", "params": ["piaxe-wallet"]}' -H 'content-type: text/plain;' http://127.0.0.1:18332/
$ curl --user bitcoin --data-binary '{"jsonrpc": "1.0", "id": "curltest", "method": "getnewaddress", "params": []}' -H 'content-type: text/plain;' http://127.0.0.1:18332/
```

