# PresentationNPat

**Verification results: NPAt algorithm vs IEEE 754 hardware FPU**

This repository presents the output of [npat_vs_ieee754_compare.cpp](https://github.com/yur-spiridonov/NPAt_algorithm/blob/main/npat_vs_ieee754_compare.cpp) from the [NPAt_algorithm](https://github.com/yur-spiridonov/NPAt_algorithm) repository.

---

## What Is Verified

The program runs sequential accumulation of 10⁹ additions on the integer ALU (NPAt algorithm) and simultaneously on the hardware FPU (IEEE 754), then prints the last 6 iterations for direct comparison.

The computed result follows the formula:

```
R = x1 + (Z − 1) · x2
```

All 50 significant decimal digits are **identical** in every iteration — across the full range of 10⁹ additions, for all input types.

---

## Test 1 — Extreme small magnitude, addition (e−200)

**X1 = 1.23456789098765405e−200; X2 = 7.65432456789098681e−200; Z = 1 000 000 000**

![Test 1](https://github.com/user-attachments/assets/bec7d787-e855-4ca3-ad19-4d7ffe8ec9e6)

---

## Test 2 — Normal fractional numbers, addition (e+00)

**X1 = 1.23456789098765407e+00; X2 = 7.65432456789098659e+00; Z = 1 000 000 000**

![Test 2](https://github.com/user-attachments/assets/5074ce21-97da-420b-8faf-bd4aadfa6f66)

---

## Test 3 — Subnormal numbers, addition (e−310)

**X1 = 1.23456789098767679e−310; X2 = 7.65432456789097493e−310; Z = 1 000 000 000**

![Test 3](https://github.com/user-attachments/assets/d7923f54-3cae-4259-a301-56e3dbda68b2)

---

## Test 4 — Subnormal numbers, addition (e−310, variant 2)

**X1 = 1.23449999999997550e−310; X2 = 7.65430000000001153e−310; Z = 1 000 000 000**

![Test 4](https://github.com/user-attachments/assets/29758dbb-4452-4546-8264-a5fe223978ab)

---

## Test 5 — Subnormal numbers, subtraction (e−310)

**X1 = 1.23449999999997550e−310; X2 = −7.65430000000001153e−310; Z = 1 000 000 000**

![Test 5](https://github.com/user-attachments/assets/058361f8-88ff-47ab-8de8-1eeeaef88b94)

---

## Test 6 — Normal numbers, subtraction, positive X1 (e+00)

**X1 = 1.23449999999999993e+00; X2 = −1.00000000000000006e−01; Z = 1 000 000 000**

![Test 6](https://github.com/user-attachments/assets/6d4e945c-36b5-4509-80eb-c9161a022939)

---

## Test 7 — Normal numbers, subtraction, negative X1 (e+00)

**X1 = −1.23449999999999993e+00; X2 = −1.00000000000000006e−01; Z = 1 000 000 000**

![Test 7](https://github.com/user-attachments/assets/56ff7cd7-0a15-4e1e-81b2-cf3dd3f2f24e)

---

## Conclusion

The NPAt algorithm, executing entirely on the integer ALU without any FPU instructions, produces results that are **bit-exact identical** to IEEE 754 hardware floating-point — verified to 50 decimal places over 1 000 000 000 iterations across all input types:

- Extreme small magnitude (e−200), addition
- Normal fractional numbers (e+00), addition
- Subnormal numbers (e−310), addition (two variants)
- Subnormal numbers (e−310), subtraction
- Normal numbers (e+00), subtraction — positive X1
- Normal numbers (e+00), subtraction — negative X1

---

## Related Repositories

| Repository | Description |
|---|---|
| [NPAt_algorithm](https://github.com/yur-spiridonov/NPAt_algorithm) | Full source code — NPAt algorithm, benchmarks, precision demo |
| [NPAt-Core-Research](https://github.com/yur-spiridonov/NPAt-Core-Research) | Theoretical foundation of the NPAt format |
| [Benchmark_Hardware-vs-NPAt-](https://github.com/yur-spiridonov/Benchmark_Hardware-vs-NPAt-) | Performance results: NPAt vs hardware IEEE 754 FPU |

---

*The NPAt format and associated algorithms are covered by U.S. Patent Pending (USPTO № 19/254,239).*
