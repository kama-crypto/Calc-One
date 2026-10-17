<img src="assets/logo.svg" alt="Calc One logo" width="68" align="left">

# Calc One

A web-based calculus calculator with worked solutions. It covers derivatives, integrals, limits, sums, Taylor polynomials and selected infinite-series problems.

Built using **Python, Flask, SymPy, JavaScript, HTML, CSS and MathJax**. The application uses symbolic computation for answers and additional logic to explain which mathematical methods apply. It is an ongoing educational project, not a substitute for checking important results independently.

**[Video demo (earlier build)](https://youtu.be/-ybTvcuMwWE)** · **[GitHub profile](https://github.com/kama-crypto)**

<br clear="left">

## Screenshots

Screenshots below were captured from an earlier frontend build. The calculator's interface may have changed since these were taken; updated screenshots will replace them.

### Taylor & Maclaurin expansions

![Taylor polynomial result with mathematical steps in the Calc One interface](images/taylor-desktop.png)

### Infinite-series convergence

![Convergence classification and explanation for an alternating series](images/convergence-desktop.png)

<details>
<summary>Additional screenshots</summary>

**Taylor coefficient table**

![Derivative-coefficient table used to construct a Taylor polynomial](images/coefficients-desktop.png)

**Recognize a series**

![Recognizing a standard function from the first terms of a series](images/series-recognition-desktop.png)

**Mobile layout**

<img src="images/taylor-mobile.png" alt="Taylor polynomial controls and result on a narrow mobile screen" width="300">

</details>

## What it does

| Tool | Supported functionality |
| --- | --- |
| **Derivatives** | Symbolic differentiation with explanations for common rules, including power, product, quotient and chain rules. |
| **Integrals** | Definite and indefinite integrals; explanations for standard forms and selected substitution and integration-by-parts patterns. |
| **Limits** | Direct substitution, simplification, selected L’Hôpital cases and limits at infinity. |
| **Sums** | Finite summations and selected symbolic infinite summations. |
| **Convergence / divergence** | Automatic selection or manual use of the nth-term, geometric, p-series/logarithmic p-series, telescoping, direct comparison, limit comparison, ratio, root, integral and alternating-series tests. |
| **Taylor & Maclaurin** | Polynomial expansions about a chosen center, through degree 12, with a table of derivative coefficients. |
| **Series recognition** | Looks for supported standard functions from a general summation term or an initial run of coefficients. A finite prefix cannot uniquely determine an infinite series. |

A convergence test is not guaranteed to produce a verdict. The program can report **inconclusive** when a method does not apply or its assumptions cannot be established.

## Examples

| Problem | Expected result |
| --- | --- |
| Differentiate `x^3*sin(x)` | `3*x^2*sin(x) + x^3*cos(x)` |
| Integrate `x*exp(x)` | `(x-1)*exp(x) + C` |
| Evaluate `(x^2-1)/(x-1)` as `x → 1` | `2` |
| Sum `n^2` for `n = 1` through `10` | `385` |
| Expand `exp(x)` around `0` to degree `3` | `1 + x + x^2/2 + x^3/6` |
| Classify `1/n^2` for `n ≥ 1` | Converges absolutely |
| Classify `(-1)^(n+1)/n` for `n ≥ 1` | Converges conditionally |

These are examples of the mathematics the solver is designed to handle, not a measured overall success rate.

## How it works

A Flask endpoint accepts the selected operation and expression, calls the corresponding Python calculation module and returns the result with explanatory steps. SymPy provides symbolic operations; additional logic identifies common techniques and builds explanations. MathJax formats the answers in the browser.

The backend separates the calculus solver from the modules used for series analysis and Taylor expansions. Requests run in bounded worker processes to limit excessive symbolic calculations.

## Limitations and development

- This is a work in progress; uncommon expressions can produce incomplete explanations, an inconclusive result, or an incorrect answer.
- Some improper integrals, particularly those with singularities inside the interval, require additional validation.
- Not every infinite series can be classified using the supported tests.
- Recognizing a pattern from a limited number of terms is not proof that the pattern continues.
- No overall percentage-accuracy claim has been established; a result such as "99% accurate" would require a defined and independently checked benchmark.

**Next steps:** expand edge-case tests, improve the clarity of explanations, review problematic integrals and update the screenshots as the interface changes.

AI tools were used to assist with the initial implementation. The ongoing project provides a way to study the mathematics, review the code, test results and improve the application. Specific personal development contributions should be described separately as they are completed.

## Project source and contact

This repository is a **public project showcase**; the application source code is kept separately. Source access for academic review can be requested through [@kama-crypto](https://github.com/kama-crypto).

To add or replace repository images, see [MEDIA_GUIDE.md](MEDIA_GUIDE.md).

© 2026 kama-crypto. All rights reserved. See [LICENSE](LICENSE).
