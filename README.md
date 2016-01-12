# TAPIR

This repository includes code implementing several replicated and
transactional key-value stores.

The repo is structured as follows:

- /lib - the transport library for communication between nodes. This
  includes UDP based network communcation as well as the ability to
  simulate network conditions on a local machine, including packet
  delays and reorderings.

- /replication - replication library for the distributed stores
  - /vr - implementation of viewstamped replication protocol
  - /ir - implementation of inconsistent replication protocol

- /store - partitioned/sharded distributed store
  - /common - common data structures, backing stores and interfaces for all of stores
  - /tapirstore - implementation of TAPIR designed to work with IR
  - /strongstore - implementation of both an OCC-based and locking-based 2PC transactional
  storage system, designed to work with VR
  - /weakstore - implementation of an eventually consistent storage
    system, using quorum writes for replication

- /lockserver - a lock server designed to be used with IR

## Compiling & Running
You can compile all of the TAPIR executables by running make in the root directory

TAPIR depends on protobufs and libevent, so you will need those development libraries installed on your machine. On Linux, this can be done through apt.

## Contact and Questions
Please email us at iyzhang@cs.washington.edu and naveenks@cs.washington.edu