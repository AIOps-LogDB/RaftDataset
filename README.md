# Dataset of Raft-based Storage System Diagnosis

## Paper Title

Towards Close-To-Zero Runtime Collection Overhead: Raft-Based Anomaly Diagnosis on System Faults for Distributed Storage System

## Overview

The dataset download link:

**Apache IoTDB**

- normal: https://zenodo.org/records/14533750/files/normal.zip
- leader: https://zenodo.org/records/14533750/files/leader.zip
- follower: https://zenodo.org/records/14533750/files/follower.zip
- database: https://zenodo.org/records/14533750/files/database.zip

**Alluxio**

- https://zenodo.org/records/14533750/files/alluxio.zip
- https://zenodo.org/records/14533750/files/alluxio.z01
- https://zenodo.org/records/14533750/files/alluxio.z02
- https://zenodo.org/records/14533750/files/alluxio.z03
- https://zenodo.org/records/14533750/files/alluxio.z04
- https://zenodo.org/records/14533750/files/alluxio.z05
- https://zenodo.org/records/14533750/files/alluxio.z06
- https://zenodo.org/records/14533750/files/alluxio.z07
- https://zenodo.org/records/14533750/files/alluxio.z08
- https://zenodo.org/records/14533750/files/alluxio.z09
- https://zenodo.org/records/14533750/files/alluxio.z10
- https://zenodo.org/records/14533750/files/alluxio.z11
- https://zenodo.org/records/14533750/files/alluxio.z12
- https://zenodo.org/records/14533750/files/alluxio.z13

This two dataset is mainly designed for root-cause analysis:

- System Fault
  - CPU Bottleneck
  - Memory Bottleneck
  - IO Bottleneck
  - Network Fault
    - Network Delay Increased
    - Network Bandwidth Limited
    - Network Partition
  - Workload Spike
- Storage System Fault
  - Storage Backup
  - Restore Backup
  - Accompany with Slow Query
  - Too Much Background Tasks
  - Configuration Error

## How to use

### Apache IoTDB

Download and unzip all linked files, then use normal/leader/follower/database to train and test. 

#### normal

No fault is injected

#### leader:

Inject fault for leader node

- cpu1: CPU Bottleneck
- memory1: Memory Bottleneck
- io1: IO Bottleneck
- network1: Network Delay Increased
- network2: Network Bandwidth Limited
- network3: Network Partition
- workload1: Workload Spike
- export: Storage Backup
- import: Restore Backup
- query1: Accompany with Slow Query

#### follower:

Inject fault for follower node

- cpu1: CPU Bottleneck
- memory1: Memory Bottleneck
- io1: IO Bottleneck
- network1: Network Delay Increased
- network2: Network Bandwidth Limited
- network3: Network Partition
- workload1: Workload Spike
- export: Storage Backup
- import: Restore Backup
- query1: Accompany with Slow Query

#### database:

Modify database configuration and run, which means fault is injected throughout the process

- database1: Background Tasks (Compaction)
- database2: Configuration1 (Flush Frequency)
- database3: Configuration2 (Ratio of write memory for rejecting insertion)
- database4: Lock Contention

### Alluxio

Download and unzip all linked files, the dataset contains the following dirs

- normal: No Fault Injected
- cpu1: CPU Bottleneck
- memory1: Memory Bottleneck
- io1: IO Bottleneck
- network1: Network Delay Increased
- network2: Network Bandwidth Limited
- network3: Network Partition
- workload1: Workload Spike
- export: Storage Backup
- import: Restore Backup
- query1: Accompany with Slow Query

### composition:

- logs: storage system application logs of each node
- metrics: KPIs data collected from docker
- raft: raft logs of each node and each region