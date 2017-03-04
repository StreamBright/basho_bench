# basho-bench

This is a fork from the original project at version 0.10.0. There are minor modifications to the original, mostly related to HTTP performance. There is some functionality that got removed (like Cassandra).

## Overview

   Basho Bench is a benchmarking tool created to conduct accurate and
   repeatable performance tests and stress tests, and produce
   performance graphs.

   Originally developed to benchmark Riak, it exposes a pluggable
   driver interface and has been extended to serve as a benchmarking
   tool across a variety of projects.

   Basho Bench focuses on two metrics of performance:

   - Throughput: number of operations performed in a timeframe,
     captured in aggregate across all operation types
   - Latency: time to complete single operations, captured in
     quantiles per-operation

## Quick Start

   You must have [[http://erlang.org/download.html][Erlang/OTP 19]] or later to build this project. The R dependency is there for the graphing, could be replaced with Python do drop the crazy amount of dependencies installing R and R libs.

### Compiling

```
git clone git@github.com:StreamBright/basho_bench.git
cd basho_bench
make all
```

### Running tests 

```
$ ./basho_bench examples/riakc_pb.config
INFO: Est. data size: 95.37 MB
INFO: Using target ip {127,0,0,1} for worker 1
INFO: Starting max worker: <0.55.0>
```

### Generating results 

```
$ make results
priv/summary.r -i tests/current
Loading required package: proto
Loading required package: reshape
Loading required package: plyr
Loading required package: digest
null device 
          1 
$ open tests/current/summary.png
```
