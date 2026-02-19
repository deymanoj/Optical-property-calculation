# Optical Properties Post-Processing from VASP OUTCAR

This project provides a Python workflow for extracting and post-processing
the frequency-dependent dielectric function from a VASP `OUTCAR` file
to compute refractive indices and birefringence.

The script is designed for anisotropic materials and is particularly useful
for nonlinear optical crystals and birefringent systems.

---

## ✨ Features

- Automatic extraction of real and imaginary dielectric tensors from `OUTCAR`
- Calculation of directional refractive indices:  
  \( n_x, n_y, n_z \)
- Birefringence computation:

  \[
  \Delta n = \max(n_x, n_y, n_z) - \min(n_x, n_y, n_z)
  \]

- Energy (eV) → Wavelength (nm) conversion
- Filtering of visible and infrared range (≥ 450 nm)
- Cubic spline interpolation for smooth spectra
- High-resolution publication-quality plots
- Export of processed optical data to text file

---

## 📚 Physical Background

VASP provides the complex dielectric function:

\[
\varepsilon(\omega) = \varepsilon_1(\omega) + i \varepsilon_2(\omega)
\]

The refractive index is computed as:

\[
n(\omega) =
\sqrt{
\frac{
\sqrt{\varepsilon_1^2 + \varepsilon_2^2}
+
\varepsilon_1
}{2}
}
\]

Photon energy and wavelength are related by:

\[
\lambda \, (\text{nm}) = \frac{1239.84193}{E \, (\text{eV})}
\]

---

## 🛠 Requirements

- Python ≥ 3.8
- NumPy
- Matplotlib
- SciPy

Install dependencies using:

```bash
pip install numpy matplotlib scipy
