A numerical format **NPAt (Number with Point After t)** has been developed.  
It produces **bit‑exact floating‑point summation results identical to IEEE 754**,  
while using **only integer arithmetic**, which enables precise computations through  
a very simple algorithm without an FPU.

The **NPAt_algorithm**, based on the NPAt format, allows computing the sum of  
floating‑point numbers (represented in binary form) on a CPU **without an FPU**.

Below is a presentation file showing the results of summing  
**Z = 1,000,000** signed numbers *x₁* and *x₂* in both the NPAt format and  
IEEE 754 double format, using the formula:

<math xmlns="http://www.w3.org/1998/Math/MathML">
  <mi>R</mi>
  <mo>=</mo>
  <msub>
    <mi>x</mi>
    <mn>1</mn>
  </msub>
  <mo>+</mo>
  <msub>
    <mi>x</mi>
    <mn>2</mn>
  </msub>
  <mo>&#x22C5;</mo>
  <mo>(</mo>
  <mi>Z</mi>
  <mo>-</mo>
  <mn>1</mn>
  <mo>)</mo>
</math>



