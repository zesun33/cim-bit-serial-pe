# cim-bit-serial-pe

> Digital Compute-in-Memory (D-CIM) Bit-Serial Processing Element with Zero-Skipping and Stationary Weights.

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](./LICENSE)
[![Category: D-CIM](https://img.shields.io/badge/architecture-D--CIM%20Bit--Serial-blueviolet)](#)
[![Precision: INT4 / INT8](https://img.shields.io/badge/precision-INT4%20%7C%20INT8-orange)](#)

## Overview
`cim-bit-serial-pe` is a compact digital Compute-in-Memory (D-CIM) processing element macro slice. It stores stationary multi-bit quantized weights locally while streaming single-bit activation slices per clock cycle, minimizing memory bandwidth and maximizing silicon compute density (Area / MAC).

## Key Features
- **Bit-Serial Arithmetic**: Computes multi-bit products over N clock cycles without expensive multi-bit DSP multipliers.
- **Dynamic Zero-Skipping**: Bypasses clock switching and accumulation when input activation bits are 0, cutting dynamic energy by up to 70%.
- **Signed Fixed-Point Saturation**: 16-bit accumulator preventing numerical overflow.
