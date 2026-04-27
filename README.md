# NPAt vs IEEE 754 — Early Results

> **Note:** This repository contains early experimental results obtained before the full NPAt Pathway 1 implementation was complete. For the current verified benchmark with hardware FPU comparison, see [Benchmark_Hardware-vs-NPAt-](https://github.com/yur-spiridonov/Benchmark_Hardware-vs-NPAt-).

---

## Contents

This repository presents early results of summing Z = 1,000,000 signed numbers in both NPAt format and IEEE 754 `double`, using the formula:

```
R = x₁ + x₂ · (Z − 1)
```

Results are shown in [presentation.pdf](presentation.pdf) as terminal screenshots comparing NPAt and IEEE 754 outputs across 7 input cases:

1. x₁ = −0.89382715639, x₂ = 0.7878271567 (999,999 additions)
2. x₁ = 0.89382715639, x₂ = 0.7878271567
3. x₁ = 89382715639, x₂ = 7878271567
4. x₁ = 89382715639e+15, x₂ = 7878271567e+23
5. x₁ = 838.678, x₂ = 7.87827e+76.236 (9,999,999 additions)
6. x₁ = 1234, x₂ = 765432
7. x₁ = −8.93827e+10, x₂ = 7.87827e+09 (99,999 additions)

---

## Key Finding

NPAt summation results at t = 24 or t = 53 are **bit-identical** to IEEE 754 `float` and `double` respectively, for arbitrary Z and arbitrary signed inputs.

---

## Related Repositories

| Repository | Description |
|---|---|
| [NPAt-Core-Research](https://github.com/yur-spiridonov/NPAt-Core-Research) | Main repository — NPAt format, theory, demo, IP |
| [Benchmark_Hardware-vs-NPAt-](https://github.com/yur-spiridonov/Benchmark_Hardware-vs-NPAt-) | Current benchmark — NPAt Pathway 1 vs hardware FPU (×1.46–2.26×) |

---

*Part of the NPAt project · Author: Iouri Spiridonov · 2026*
