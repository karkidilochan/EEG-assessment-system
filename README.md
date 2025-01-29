# Electroencephalogram (EEG) Signal Analysis and Classification

This project focuses on analyzing electroencephalogram (EEG) signals, a type of brain-computer interface, to classify rhythmic content and identify noisy channels using advanced signal processing and machine learning techniques. The project also includes a 3D visualization of EEG data, leveraging Fourier transforms and color coding for enhanced interpretability.

---

## Features

- **Signal Preprocessing**:
  - **Fast Fourier Transform (FFT)**: Decomposes EEG signals into frequency components.
  - **Noise Removal**: Filters out noise at 50 Hz caused by electrical interference.
  - **Rhythmic Power Calculation**: Computes the power of each frequency range by squaring the amplitude of the Fourier transform.

- **Channel Classification**:
  - Labels channels with rhythmic power below 10% as "bad channels" (insufficient rhythmic content).
  - Uses rhythmic and artifact values as features for classification.

- **Machine Learning**:
  - Implements a Support Vector Machine (SVM) classifier with:
    - **Linear Kernel**: Suitable for linearly separable data.
    - **Misclassification Cost (C)**: Set to $$2^{50}$$ for optimal performance.
  - Observes linearly separable data distribution in a 2D feature space.

- **3D Visualization**:
  - Synthesizes a 3D model based on signals from 16 main EEG electrodes.
  - Applies Fourier transforms to calculate signal amplitudes in alpha, beta, and delta ranges.
  - Normalizes voltages and maps them to RGB color codes:
    - **Alpha (Red)**, **Beta (Green)**, **Delta (Blue)**.
  - Displays data in a rendering engine using a clean, normalized 3D array.

---

## Workflow

1. **Preprocessing**:
   - Slice electric signals at 50 Hz to remove noise.
   - Apply FFT to obtain frequency domain data.
   - Calculate rhythmic power by squaring amplitudes.

2. **Channel Labeling**:
   - Identify "bad channels" with rhythmic power <10%.
   - Use rhythmic percentage and artifact values for classification.

3. **Classification**:
   - Train an SVM classifier with linear kernel on labeled data.
   - Optimize with $$C = 2^{50}$$ for misclassification cost.

4. **3D Visualization**:
   - Compute normalized voltages for alpha, beta, and delta waves.
   - Map voltages to RGB color codes for rendering.
   - Generate a clean, visual representation of EEG activity.

---

## Results

- Achieved accurate classification of rhythmic vs. noisy channels using SVM.
- Demonstrated linearly separable data distribution in feature space.
- Produced visually interpretable 3D models of EEG activity with color-coded wave representations.

---


## Future Work

- Explore advanced noise reduction techniques for improved signal quality.
- Implement deep learning models for more robust classification.
- Extend visualization capabilities to include temporal dynamics of EEG signals.

---

## Contributing

Contributions are welcome! Please fork the repository, create a new branch, and submit a pull request with your changes.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
