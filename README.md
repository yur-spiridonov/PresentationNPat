# PresentationNPat

**Verification results: NPAt algorithm vs IEEE 754 hardware FPU**

This repository presents the output of [npat_vs_ieee754_compare.cpp](https://github.com/yur-spiridonov/NPAt_algorithm/blob/main/npat_vs_ieee754_compare.cpp) from the [NPAt_algorithm](https://github.com/yur-spiridonov/NPAt_algorithm) repository.

---

## What Is Verified

The program runs sequential accumulation of 10⁹ additions on the integer ALU (NPAt algorithm) and simultaneously on the hardware FPU (IEEE 754), then prints the last 6 iterations for direct comparison.

**Input data used:**

| Parameter | Value |
|---|---|
| Initial Value (X1) | −1.23449999999999993e+00 |
| Adder Value (X2) | −1.00000000000000006e−01 |
| Total Iterations (Z) | 1 000 000 000 |

---

## Result

![NPAt vs IEEE 754 comparison output](screenshot.png)

All 50 significant decimal digits are **identical** in every iteration — across the full range of 10⁹ additions.

---

## Conclusion

The NPAt algorithm, executing entirely on the integer ALU without any FPU instructions, produces results that are **bit-exact identical** to IEEE 754 hardware floating-point — verified to 50 decimal places over 1 000 000 000 iterations.

---

## Related Repositories

| Repository | Description |
|---|---|
| [NPAt_algorithm](https://github.com/yur-spiridonov/NPAt_algorithm) | Full source code — NPAt algorithm, benchmarks, precision demo |
| [NPAt-Core-Research](https://github.com/yur-spiridonov/NPAt-Core-Research) | Theoretical foundation of the NPAt format |
| [Benchmark_Hardware-vs-NPAt-](https://github.com/yur-spiridonov/Benchmark_Hardware-vs-NPAt-) | Performance results: NPAt vs hardware IEEE 754 FPU |

---

*The NPAt format and associated algorithms are covered by U.S. Patent Pending (USPTO № 19/254,239).*
