# **Spectral Estimation Methods with MATLAB DTMF**

## **Overview**
This project explores spectral estimation techniques for sinusoidal signal reconstruction in noisy environments. It is implemented in MATLAB and focuses on:
1. **DTMF Signal Generation**:
   - Simulating Dual Tone Multi-Frequency (DTMF) signals used in telecommunications.
   - Adding Gaussian noise to simulate real-world conditions.
2. **Pisarenko Spectral Method**:
   - Estimating frequencies of noisy signals using the subspace method.
3. **Frequency Analysis and Visualization**:
   - Using covariance matrices and eigenvalue decomposition to detect signal frequencies.

This project demonstrates the theoretical foundations of spectral estimation and its practical implementation in MATLAB.

---

## **Key Objectives**
1. Simulate and analyze DTMF signals for real-world applications.
2. Apply Pisarenko's method to estimate frequencies in noisy environments.
3. Visualize signal spectra to interpret frequency components.

---

## **Key Features**
### **1. DTMF Signal Simulation**
- Generates DTMF signals for user-provided input (e.g., phone numbers).
- Combines sinusoidal components for each keypress.
- Allows customization of sampling frequency, SNR, and noise variance.

### **2. Pisarenko Spectral Estimation**
- Uses covariance matrices and eigenvalue decomposition to estimate signal frequencies.
- Detects dominant frequencies in noisy signals.

### **3. Noise Modeling**
- Adds Gaussian noise to simulate real-world scenarios.
- Supports varying noise levels controlled by variance and SNR.

### **4. Frequency Visualization**
- Plots signal spectra to identify and compare frequencies.
- Demonstrates the efficiency of the Pisarenko method for spectral analysis.

---

## **Technologies**
- **MATLAB**: Used for signal generation, noise modeling, and spectral estimation.

---

## **Theoretical Background**

### **1. DTMF Signal Model**
A DTMF signal combines two sinusoidal tones:

$$s(t) = a_1 \sin(2\pi f_1 t) + a_2 \sin(2\pi f_2 t) + w(t)$$

Where:
- $f_1$ and $f_2$: Frequencies of the two tones.
- $a_1$ and $a_2$: Amplitudes of the tones.
- $w(t)$: Additive Gaussian noise.

### 2. Covariance Matrix

The covariance matrix for the signal $u(n)$ is:

$$R_u = EPE^H + \sigma_w^2 I$$

Where:
- $E$: Matrix of eigenvectors.
- $P$: Diagonal matrix of signal powers.
- $\sigma_w^2$: Noise variance.
- $I$: Identity matrix.

### 3. Pisarenko Method

Pisarenko's method leverages the smallest eigenvector to estimate frequencies. Using a Toeplitz matrix for covariance:

$$R_u = \text{toeplitz}([r_0, r_1, ..., r_{p-1}])$$

Frequencies are extracted from eigenvalues and eigenvectors.

---

## **Project Structure**
```
Spectral-Estimation/
├── README.md                 # Project description and instructions
├── LICENSE                   # Licensing information
├── data/                     # Input data (e.g., signal data)
├── src/                      # MATLAB scripts
│   ├── dtmf_signal.m         # Script for generating DTMF signals
│   ├── analyze_signal.m      # Comprehensive analysis
```
---

## **Running the Scripts**

### **1. Generate DTMF Signal**
Run dtmf_signal.m:
- Input: Phone number and signal parameters (sampling frequency, noise variance, SNR).
- Output: Time-domain DTMF signal.

### **2. Add Noise**
Run add_noise.m:
- Input: Clean DTMF signal.
- Output: Noisy signal.

### **3. Frequency Estimation**
Run pisarenko_method.m:
- Input: Noisy signal.
- Output: Estimated frequencies and spectrum plot.

### **4. Comprehensive Analysis**
Run analyze_signal.m:
- Performs end-to-end analysis from signal generation to frequency estimation.

---

## **Applications**
1. **Telecommunication**: Simulates and analyzes DTMF signaling.
2. **Signal Processing**: Demonstrates robust spectral estimation for noisy signals.
3. **Real-World Noise Scenarios**: Tests algorithms for reliable frequency detection.
