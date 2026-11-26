# 4-Bit Register with Parallel Load

A project documenting a **4-bit register with parallel load**. The register stores a 4-bit data word and can load all four bits simultaneously, using a load-enable control signal.

## Overview

A parallel-load register has separate data inputs for each bit and a common clock. When the load input is enabled, all input values are stored on the clock edge. When loading is disabled, the register retains its previous value.

## Features

- 4-bit parallel data input
- 4-bit registered output
- Clocked operation
- Parallel load capability
- Stable data retention when load is disabled

## Pin Description

| Name | Width | Direction | Description |
|---|---:|---|---|
| `D[3:0]` | 4 bits | Input | Parallel data inputs |
| `Load` | 1 bit | Input | Enables loading of `D[3:0]` |
| `CLK` | 1 bit | Input | Clock signal |
| `Q[3:0]` | 4 bits | Output | Stored 4-bit value |

## Operation

| `Load` | On rising `CLK` edge | `Q[3:0]` result |
|---|---|---|
| `0` | Clock pulse | Holds the previous value |
| `1` | Clock pulse | Loads `D[3:0]` |

## Truth Table

| Load | `D[3:0]` | `Q[3:0]` after rising clock edge |
|---|---|---|
| 0 | Any | Previous `Q[3:0]` |
| 1 | `0000` | `0000` |
| 1 | `0101` | `0101` |
| 1 | `1010` | `1010` |
| 1 | `1111` | `1111` |

## Project Documentation

Detailed project material is available in [`4_bit_register_with_parallel_load.pdf`](4_bit_register_with_parallel_load.pdf).

## Repository Structure

```text
.
├── 4_bit_register_with_parallel_load.pdf
└── README.md
```

## Author

Abhishek Kumar
