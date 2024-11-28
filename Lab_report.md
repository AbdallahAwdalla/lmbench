
The lmbench results:

### Basic System Parameters
- **CPU Speed**: The CPU speeds range from 2993 MHz to 3088 MHz.
- **Cache Line Size**: 128 bytes, which is typical for modern CPUs.

### Processor and Processes
- **Null Call**: Times range from 0.11 to 0.25 microseconds, indicating efficient system calls.
- **Fork and Exec**: Times for fork range from 153 to 168 microseconds, and exec from 382 to 467 microseconds. These are reasonable for a modern system.
- **Shell**: Times for shell operations range from 776 to 1415 microseconds, showing some variability.

### Basic Integer Operations
- **Addition and Multiplication**: Very low times (0.01 to 1.07 nanoseconds), indicating efficient integer operations.
- **Division and Modulus**: Slightly higher times (3.48 to 5.88 nanoseconds), which is expected due to the complexity of these operations.

### Floating Point Operations
- **Addition and Multiplication**: Times are consistent (0.63 to 0.69 nanoseconds for addition, 1.29 to 1.50 nanoseconds for multiplication).
- **Division**: Higher times (3.49 to 3.99 nanoseconds), as floating-point division is more complex.

### Double Precision Operations
- **Addition and Multiplication**: Similar to floating-point operations, with times ranging from 0.63 to 0.71 nanoseconds for addition and 1.28 to 1.38 nanoseconds for multiplication.
- **Division**: Higher times (4.43 to 4.82 nanoseconds).

### Context Switching
- **2p/0K to 16p/64K**: Times range from 16.8 to 24.0 microseconds, indicating efficient context switching.

### Local Communication Latencies
- **Pipe and AF UNIX**: Latencies are around 35 to 37 microseconds.
- **TCP and UDP**: Latencies are slightly higher, around 40 to 42 microseconds.

### File and VM System Latencies
- **File Create/Delete**: Times range from 8.44 to 14.9 microseconds for create and 8.44 to 11.0 microseconds for delete.
- **Mmap Latency**: Around 26.4K to 28.3K microseconds, which is typical for memory-mapped file operations.
- **Page Faults**: Very low times (0.0483 to 0.0555 microseconds), indicating efficient memory management.

### Local Communication Bandwidths
- **Pipe and AF UNIX**: High bandwidths (1630 to 5107 MB/s).
- **TCP**: Consistently high bandwidths around 5081 to 5102 MB/s.
- **File Reread and Mmap**: Very high bandwidths (7441.5 to 15.4K MB/s).

### Memory Latencies
- **L1 and L2 Cache**: Very low latencies (1.66 to 3.94 nanoseconds).
- **Main Memory**: Latencies around 8.85 to 8.93 nanoseconds.
- **Random Memory**: Higher latencies (135.4 to 230.5 nanoseconds), which is expected.



Here's the lmbench summary in Markdown format:

# LMbench 3.0 Summary
**(Alpha software, do not distribute)**

## Basic System Parameters
| Host      | OS Description       | Mhz | tlb pages | cache line bytes | mem par | scal load |
|-----------|----------------------|-----|-----------|------------------|---------|-----------|
| AAwdallah | Linux 5.15.16 x86_64 | 2993|           | 128              |         | 1         |

## Processor, Processes - Times in Microseconds (Smaller is Better)
| Host      | OS           | Mhz | null call | null I/O | stat | open | slct | clos | TCP inst | sig hndl | fork | exec | sh proc |
|-----------|---------------|-----|-----------|----------|------|------|------|------|----------|----------|------|------|---------|
| AAwdallah | Linux 5.15.16 | 2993| 0.25      | 0.18     | 0.44 | 1.70 | 1.78 | 0.17 | 0.96     | 155.0    | 467.0| 1415.0|
| AAwdallah | Linux 5.15.16 | 3015| 0.12      | 0.15     | 0.44 | 1.04 | 2.27 | 0.19 | 0.87     | 153.0    | 395.0| 933.0 |
| AAwdallah | Linux 5.15.16 | 3088| 0.18      | 0.14     | 0.36 | 1.02 | 1.50 | 0.19 | 0.89     | 155.0    | 399.0| 851.0 |
| AAwdallah | Linux 5.15.16 | 3088| 0.11      | 0.13     | 0.36 | 0.90 | 1.50 | 0.28 | 0.89     | 168.0    | 401.0| 776.0 |
| AAwdallah | Linux 5.15.16 | 3088| 0.11      | 0.15     | 0.36 | 0.85 | 1.38 | 0.16 | 0.82     | 160.0    | 382.0| 839.0 |
| AAwdallah | Linux 5.15.16 | 3088| 0.20      | 0.17     | 0.44 | 1.70 | 1.95 | 0.23 | 1.06     | 194.0    | 589.0| 1325.0|

## Basic Integer Operations - Times in Nanoseconds (Smaller is Better)
| Host      | OS           | intgr bit | intgr add | intgr mul | intgr div | intgr mod |
|-----------|---------------|-----------|-----------|-----------|-----------|-----------|
| AAwdallah | Linux 5.15.16 | 0.2400    | 0.0100    | 1.0300    | 3.6600    | 5.6500    |
| AAwdallah | Linux 5.15.16 | 0.2400    | 0.0100    | 1.0500    | 3.8700    | 5.6400    |
| AAwdallah | Linux 5.15.16 | 0.2500    | 0.0100    | 1.0600    | 3.7600    | 5.8800    |
| AAwdallah | Linux 5.15.16 | 0.2400    | 0.0100    | 0.9800    | 3.4800    | 5.4000    |
| AAwdallah | Linux 5.15.16 | 0.2600    | 0.0100    | 1.0700    | 3.7800    | 5.8400    |
| AAwdallah | Linux 5.15.16 | 0.3600    | 0.0100    | 1.2600    | 4.5000    | 7.3100    |

## Basic Float Operations - Times in Nanoseconds (Smaller is Better)
| Host      | OS           | float add | float mul | float sqrt | float div | float bogo |
|-----------|---------------|-----------|-----------|------------|-----------|------------|
| AAwdallah | Linux 5.15.16 | 0.6700    | 1.3300    |            | 3.6900    | 1.0100     |
| AAwdallah | Linux 5.15.16 | 0.6700    | 1.3300    |            | 3.6800    | 1.0000     |
| AAwdallah | Linux 5.15.16 | 0.6900    | 1.4100    |            | 3.7800    | 1.0200     |
| AAwdallah | Linux 5.15.16 | 0.6300    | 1.2900    |            | 3.4900    | 0.9500     |
| AAwdallah | Linux 5.15.16 | 0.6800    | 1.5000    |            | 3.9900    | 1.0500     |
| AAwdallah | Linux 5.15.16 | 0.8300    | 1.6600    | 5.5700     | 4.5700    | 1.2200     |

## Basic Double Operations - Times in Nanoseconds (Smaller is Better)
| Host      | OS           | double add | double mul | double div | double bogo |
|-----------|---------------|------------|------------|------------|-------------|
| AAwdallah | Linux 5.15.16 | 0.6600     | 1.3300     | 4.7200     | 1.3300      |
| AAwdallah | Linux 5.15.16 | 0.6700     | 1.3300     | 4.6900     | 1.3300      |
| AAwdallah | Linux 5.15.16 | 0.7100     | 1.3800     | 4.8200     | 1.3800      |
| AAwdallah | Linux 5.15.16 | 0.6300     | 1.2800     | 4.4300     | 1.2600      |
| AAwdallah | Linux 5.15.16 | 0.6900     | 1.3700     | 4.8200     | 1.3700      |
| AAwdallah | Linux 5.15.16 | 0.9500     | 1.6300     | 5.7500     | 1.6600      |

## Context Switching - Times in Microseconds (Smaller is Better)
| Host      | OS           | 2p/0K ctxsw | 2p/16K ctxsw | 2p/64K ctxsw | 8p/16K ctxsw | 8p/64K ctxsw | 16p/16K ctxsw | 16p/64K ctxsw |
|-----------|---------------|-------------|--------------|--------------|--------------|--------------|---------------|---------------|
| AAwdallah | Linux 5.15.16 | 17.3        | 19.3         | 17.3         | 19.7         | 19.1         | 20.1          | 21.1          |
| AAwdallah | Linux 5.15.16 | 16.8        | 18.1         | 19.5         | 19.3         | 24.0         | 22.8          | 21.9          |
| AAwdallah | Linux 5.15.16 | 53.2        | 23.5         | 27.4         | 31.2         | 28.6         | 30.5          | 23.2          |

## Local Communication Latencies in Microseconds (Smaller is Better)
| Host      | OS           | 2p/0K ctxsw | Pipe | AF UNIX | UDP  | RPC/UDP | TCP  | RPC/TCP | TCP conn |
|-----------|---------------|-------------|------|---------|------|---------|------|---------|----------|
| AAwdallah | Linux 5.15.16 |             | 36.7 | 35.9    | 41.3 |         | 41.9 |         |          |
| AAwdallah | Linux 5.15.16 | 17.3        | 36.5 | 35.2    | 42.9 |         | 41.3 |         | 30.0     |
| AAwdallah | Linux 5.15.16 |             | 35.7 | 34.7    | 41.8 |