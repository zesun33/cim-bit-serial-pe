# cim-bit-serial-pe: Architectural Specification

## 1. D-CIM Compute Model
For an $N$-bit activation $A = \sum_{k=0}^{N-1} a_k \cdot 2^k$ and an $M$-bit weight $W$:
$$P = A \times W = \sum_{k=0}^{N-1} (a_k \cdot W) \cdot 2^k$$

Each cycle $k$, if $a_k = 1$, the shifted weight $(W \ll k)$ is accumulated into the partial sum register.

## 2. Pinout & Interface
| Signal | Direction | Width | Description |
| :--- | :---: | :---: | :--- |
| `clk` | In | 1 | Master clock |
| `rst_n` | In | 1 | Active-low asynchronous reset |
| `act_bit` | In | 1 | 1-bit streaming activation slice |
| `act_sign` | In | 1 | Indicates current bit is sign bit (subtraction instead of addition) |
| `weight_in` | In | 4 | Stationary weight register load bus |
| `weight_load` | In | 1 | Strobe to latch new stationary weight |
| `cycle_idx` | In | 3 | Current bit-serial cycle index (0..3 for INT4) |
| `accum_en` | In | 1 | Strobe to perform accumulation |
| `accum_clear` | In | 1 | Clear accumulator for new dot product vector |
| `psum_out` | Out | 16 | 16-bit accumulated partial sum |
