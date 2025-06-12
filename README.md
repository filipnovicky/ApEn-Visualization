# Approximate Entropy

Consider analyzing sensor data from a complex dynamical system - perhaps temperature fluctuations in a chemical reactor, stock market prices, seismic activity recordings, or electrophysiological signals. These signals appear intricate and unpredictable, yet some may contain underlying regularities while others are purely chaotic.

Approximate Entropy (ApEn) addresses this challenge by quantifying pattern regularity without requiring knowledge of the underlying mathematical function the system can be described with. Even when we cannot understand the specific mechanisms generating the signal, we can assess whether there is some inherent regularity or randomness - something that can be informative about the complexity of the system.

## 🎯 Live Demo

**[View Interactive Visualization](https://filipnovicky.github.io/ApEn-Visualization/)**

## 🔬 How This Visualization Works

### Signal Analysis
The visualization compares two types of signals:
- **Signal A (Red)**: Random fluctuations with no underlying pattern
- **Signal B (Blue)**: Periodic oscillations with regular, repeating patterns (with adjustable noise)

### Pattern Matching Process
1. **Analysis Window**: Extracts patterns from the first 10 samples (for educational demonstration)
2. **Adaptive Tolerance**: Uses r = α × SD(signal) for each signal individually
3. **Pattern Search**: Finds similar patterns throughout the entire signal using Chebyshev distance
4. **Counting**: Records how many times each pattern repeats across the full signal
5. **Calculation**: Computes ApEn using the mathematical formula

### Mathematical Foundation
```
ApEn(m, α) = φᵐ(r) - φᵐ⁺¹(r), where r = α × SD(signal)
φᵐ(r) = (1/N) × Σ ln(Cᵢᵐ(r))
Cᵢᵐ(r) = (number of patterns j such that d[x(i), x(j)] ≤ r) / N
d[x(i), x(j)] = max|x(i+k) - x(j+k)| for k = 0, 1, ..., m-1 (Chebyshev distance)
```
Where:
- `m` = pattern length (user-selectable: 2-5 points)
- `α` = scaling factor (0.1-0.5) for adaptive tolerance
- `r` = tolerance threshold = α × standard deviation of signal
- `Cᵢᵐ(r)` = relative frequency of patterns similar to pattern i
- `N` = total possible patterns in the signal
- `i, j` are sampled from {1, 2, ..., N}

## 🎮 Interactive Features

- **Adaptive Parameter Control**: Adjust pattern length (m), alpha scaling (α), and noise level
- **Real-time Pattern Highlighting**: Watch as patterns are identified and matched throughout the signal
- **Step-by-step Animation**: Control the analysis progression with play/pause and manual stepping
- **Educational Analysis Window**: Demonstrates pattern extraction from a subset while searching the full signal
- **Pattern Count Tables**: View exact repetition counts and relative frequencies (Cᵢᵐ(r)) for each pattern
- **Mathematical Results**: Compare final ApEn values with detailed φ calculations

## 📊 Key Insight

The visualization reveals the fundamental principle behind ApEn:

**Pattern Persistence Principle**: If a signal is regular across a specific length, then the count of m-length and (m+1)-length patterns should be approximately equal. If the signal is irregular, there will be more m-length matches than (m+1)-length matches simply because of chances. Hence, φᵐ(r) - φᵐ⁺¹(r) will be higher for irregular systems, while both φ values should be approximately equal for signals showing regularities.


### Local Development
1. Clone this repository:
   ```bash
   git clone https://github.com/filipnovicky/ApEn-Visualization.git
   ```
2. Open `index.html` in your web browser
3. No build process required!

## 🤖 AI-Generated Content

This visualization was created with assistance from **Claude.ai** (Anthropic). The interactive demonstration, mathematical implementation, and educational content were developed through collaborative AI-human interaction to ensure accuracy and pedagogical effectiveness.

## 📖 References

1. Pincus, S. M. (1991). Approximate entropy as a measure of system complexity. *Proceedings of the National Academy of Sciences*, 88(6), 2297-2301.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](../../issues) if you want to contribute.

## 👨‍💻 Author

**Filip Novicky**
- GitHub: [@filipnovicky](https://github.com/filipnovicky)

---

*Made with Claude.ai for educational purposes*
