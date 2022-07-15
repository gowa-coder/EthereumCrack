# EthCrack
A tool for brute-forcing Ethereum private keys and seeds. The main purpose of this project is to contribute to the effort of solving the Ethereum puzzle transaction: A transaction with 32 addresses that become increasingly difficult to crack.

### Using BitCrack

#### Usage

Use `cuda_EthCrack.exe` for CUDA devices and `opcl_EthCrack.exe` for OpenCL devices.

```
xxxxEthCrack.exe [OPTIONS] [TARGETS]

Where [TARGETS] are one or more Ethereum address

Options:

-i, --in FILE
    Read addresses from FILE, one address per line. If FILE is "-" then stdin is read

-o, --out FILE
    Append private keys to FILE, one per line

-d, --device N
    Use device with ID equal to N

-b, --blocks BLOCKS
    The number of CUDA blocks

-t, --threads THREADS
    Threads per block

-p, --points NUMBER
    Each thread will process NUMBER keys at a time

--keyspace KEYSPACE
    Specify the range of keys to search, where KEYSPACE is in the format,

	START:END start at key START, end at key END
	START:+COUNT start at key START and end at key START + COUNT
    :END start at key 1 and end at key END
	:+COUNT start at key 1 and end at key 1 + COUNT

-c, --compressed
    Search for compressed keys (default). Can be used with -u to also search uncompressed keys

-u, --uncompressed
    Search for uncompressed keys, can be used with -c to search compressed keys

--compression MODE
    Specify the compression mode, where MODE is 'compressed' or 'uncompressed' or 'both'

--list-devices
    List available devices

--stride NUMBER
    Increment by NUMBER

--share M/N
    Divide the keyspace into N equal sized shares, process the Mth share

--continue FILE
    Save/load progress from FILE
```

![.](https://gifer.com/ru/2tsW)
