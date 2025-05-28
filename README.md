# Visualization of Approximate Entropy Analysis

An interactive web-based visualization demonstrating how Approximate Entropy (ApEn) distinguishes between regular and random signals through pattern matching analysis.

## 🎯 Live Demo

**[View Interactive Visualization](https://filipnovicky.github.io/ApEn-Visualization/)**

## 📖 What is Approximate Entropy?

Approximate Entropy (ApEn) is a statistical measure used to quantify the regularity and predictability of time-series data. It was introduced by Steve Pincus in 1991 and is widely used in:

- **Biomedical signal analysis** (heart rate variability, EEG signals)
- **Financial time series** (market volatility analysis)
- **Physiological data** (hormone secretion patterns)
- **Quality control** (manufacturing process monitoring)

## 🔬 How This Visualization Works

### Signal Analysis
The visualization compares two types of signals:
- **Regular Signal**: A periodic triangle wave with predictable patterns
- **White Noise**: Random fluctuations with no underlying pattern

### Pattern Matching Process
1. **Analysis Window**: Extracts patterns from the first 10 samples
2. **Pattern Search**: Finds similar patterns throughout the entire signal using Chebyshev distance
3. **Counting**: Records how many times each pattern repeats
4. **Calculation**: Computes ApEn using the mathematical formula

### Mathematical Foundation
```
ApEn(m, r) = φ(m) - φ(m+1)
φ(m) = (1/N) × Σ ln(Cᵢ(m)/N)
```
Where:
- `m` = pattern length (2 or 3 points)
- `r` = tolerance threshold (0.05)
- `Cᵢ(m)` = count of patterns similar to pattern i
- `N` = total number of patterns

## 🎮 Interactive Features

- **Real-time Pattern Highlighting**: Watch as patterns are identified and matched
- **Visual Signal Comparison**: See the difference between regular and random signals
- **Pattern Count Tables**: View exact repetition counts for each pattern
- **Mathematical Results**: Compare final ApEn values between signal types

## 📊 Key Insights

- **Lower ApEn** → More regular/predictable signals
- **Higher ApEn** → More irregular/random signals
- **Pattern Persistence**: Regular signals maintain high pattern counts at both m=2 and m=3
- **Pattern Decay**: Random signals show fewer matches as pattern length increases

## 🛠️ Technical Details

- **Built with**: Pure HTML, CSS, and React (via CDN)
- **Styling**: Tailwind CSS
- **Deployment**: GitHub Pages
- **Algorithm**: Chebyshev distance for pattern matching
- **Responsive Design**: Works on desktop and mobile devices

## 🚀 Usage

### Online
Simply visit the [live demo](https://filipnovicky.github.io/ApEn-Visualization/) in any modern web browser.

### Local Development
1. Clone this repository:
   ```bash
   git clone https://github.com/filipnovicky/ApEn-Visualization.git
   ```
2. Open `index.html` in your web browser
3. No build process required!

## 📚 Educational Value

This visualization is designed for:
- **Students** learning signal processing and time series analysis
- **Researchers** needing to understand ApEn methodology
- **Educators** teaching complexity measures in data
- **Anyone** curious about pattern recognition in signals

## 🤖 AI-Generated Content

This visualization was created with assistance from **Claude.ai** (Anthropic). The interactive demonstration, mathematical implementation, and educational content were developed through collaborative AI-human interaction to ensure accuracy and pedagogical effectiveness.

## 📖 References

1. Pincus, S. M. (1991). Approximate entropy as a measure of system complexity. *Proceedings of the National Academy of Sciences*, 88(6), 2297-2301.
2. Richman, J. S., & Moorman, J. R. (2000). Physiological time-series analysis using approximate entropy and sample entropy. *American Journal of Physiology-Heart and Circulatory Physiology*, 278(6), H2039-H2049.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](../../issues) if you want to contribute.

## 👨‍💻 Author

**Filip Novicky**
- GitHub: [@filipnovicky](https://github.com/filipnovicky)

---

*Made with ❤️ and Claude.ai for educational purposes*
