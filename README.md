Here’s an improved version of the **README.md** file with properly formatted equations using LaTeX syntax that can be rendered on GitHub (through tools like MathJax):

---

# **Spectral Estimation Methods with MATLAB**

## **Overview**
This project explores spectral estimation methods in MATLAB, focusing on the reconstruction of sinusoidal signal parameters in noisy environments. Key topics include:
1. **DTMF Signal Simulation**: Dual Tone Multi-Frequency (DTMF) signal generation and analysis.
2. **Pisarenko Spectral Estimation**: A subspace-based method to detect signal frequencies.

---

## **Key Features**
1. **DTMF Signal Simulation**:
   - Generate DTMF signals corresponding to phone numbers.
   - Add Gaussian noise with configurable variance and Signal-to-Noise Ratio (SNR).
2. **Pisarenko Spectral Estimation**:
   - Identify dominant frequencies of noisy signals using eigenvalue decomposition.
3. **Visualization**:
   - Plot time-domain signals and frequency spectra.

---

## **Technologies**
- MATLAB for signal generation, noise modeling, and spectral analysis.

---

## **Theoretical Background**

### **1. Auto-Regressive Models**
An AR signal \( x_t \) is modeled as:
\[
x_t = -\sum_{k=1}^{p} a_k x_{t-k} + \epsilon_t
\]
where:
- \( a_k \): AR coefficients.
- \( \epsilon_t \): White noise with mean zero and variance \( \sigma^2 \).

### **2. DTMF Signal**
The DTMF signal is generated as a sum of two sinusoidal components:
\[
s(t) = a_1 \sin(2\pi f_1 t) + a_2 \sin(2\pi f_2 t)
\]
where:
- \( f_1 \) and \( f_2 \): Frequencies of the two tones.
- \( t \): Time vector.

### **3. Covariance Matrix for Pisarenko Method**
The covariance matrix \( R_u \) for a signal \( u(n) \) is given by:
\[
R_u = E P E^H + \sigma_w^2 I
\]
where:
- \( E \): Matrix of eigenvectors for the signal space.
- \( P \): Diagonal matrix of signal powers.
- \( \sigma_w^2 \): Variance of the noise.
- \( I \): Identity matrix.

---

## **Project Structure**
```
Spectral-Estimation/
├── README.md               # Project description
├── LICENSE                 # Licensing information
├── data/                   # Input and output data (e.g., signal data)
├── src/                    # MATLAB scripts
│   ├── dtmf_signal.m       # Script for DTMF signal generation
│   ├── add_noise.m         # Script to add noise to signals
│   ├── pisarenko_method.m  # Pisarenko spectral estimation
│   ├── analyze_signal.m    # End-to-end analysis
└── images/                 # Saved plots for README
```

---

## **Getting Started**

### **Prerequisites**
- MATLAB (R2021a or newer) with the Signal Processing Toolbox.

### **Setup**
1. Clone the repository:
   ```bash
   git clone https://github.com/amenallah01/Spectral-Estimation.git
   cd Spectral-Estimation
   ```
2. Place any required input data (e.g., signal files) in the `data/` directory.

---

## **Scripts Overview**

### **1. `dtmf_signal.m`**
Generates a DTMF signal based on user input (e.g., a phone number). The signal combines two frequencies for each key, defined as:
\[
s(t) = a_1 \sin(2\pi f_1 t) + a_2 \sin(2\pi f_2 t) + w(t)
\]
Where \( w(t) \) is Gaussian noise.

---

### **2. `add_noise.m`**
Adds Gaussian noise to a clean signal:
\[
u(t) = s(t) + w(t)
\]
Where:
- \( s(t) \): Clean signal.
- \( w(t) \): Gaussian noise with variance \( \sigma^2 \).

---

### **3. `pisarenko_method.m`**
Uses the Pisarenko method to estimate signal frequencies. Steps include:
1. Construct the covariance matrix:
   \[
   R_u = \text{toeplitz}([r_0, r_1, \ldots, r_{p-1}])
   \]
   where \( r_i \) is the autocorrelation of \( u(t) \).
2. Compute eigenvalues and eigenvectors:
   \[
   R_u v = \lambda v
   \]
3. Identify frequencies from the smallest eigenvector.

---

### **4. `analyze_signal.m`**
Combines all steps:
1. Generate a DTMF signal.
2. Add noise to the signal.
3. Apply the Pisarenko method for frequency estimation.
4. Plot and analyze the results.

---

## **Applications**
- **Telecommunication**: Simulate and analyze DTMF signaling.
- **Signal Processing**: Apply spectral estimation techniques to noisy data.
- **Real-World Noise Scenarios**: Test methods for robust frequency detection.

---

## **Adding Visuals**
Use MATLAB to save plots:
```matlab
saveas(gcf, 'images/plot_name.png');
```
Include them in the README with:
```markdown
![Description](images/plot_name.png "Optional Title")
```

---

## **License**
This project is licensed under the MIT License.

---

## **Acknowledgments**
Special thanks to **Université Paris-Saclay** and **Mohammed El-Korso** for the guidance and theoretical foundation provided in this project.

---

This improved version correctly represents the mathematical equations and provides clarity for GitHub readers. Let me know if you'd like further refinements or assistance!
