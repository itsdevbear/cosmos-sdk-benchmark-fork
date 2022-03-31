custom fork of Cosmos SDK @ a specific commit + modifications that we utilize for our stuff.

run benchmarks:
```
# cosmos specific benchmarks
cd cosmos-sdk
make test-sim-profile test-sim-benchmark benchmark  # default uses leveldb
ENABLE_ROCKSDB=rocksdb make test-sim-profile test-sim-benchmark benchmark   # use rocksdb

# ethereum specific çbenchmarks
cd ethermint
make benchmark  # default uses leveldb
ENABLE_ROCKSDB=rocksdb make benchmark   # use rocksdb

```

To adjust length of sim tests

```
SIM_NUM_BLOCKS ?= 1500              # how many blocks to simulate
SIM_BLOCK_SIZE ?= 500               # max number of transactions per block
```     

Note: a bunch of tests might fail because they required a hardware wallet to be attached to the machine during the run, you can ignore the failures. 

I can add a ENABLE_ROCKSDB=speedb as well if needed, will have to make the change in tm-db but should be easy.
