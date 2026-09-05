# 🔬 Raman Spectroscopy Analysis Tool

## ✨ Overview

The **Raman Spectroscopy Analysis Tool** is a comprehensive web application built with Streamlit and advanced scientific Python libraries (like Pandas, NumPy, and potentially SciPy/LMFIT) designed for chemists, materials scientists, and engineers to quickly and accurately process, analyze, and characterize Raman spectroscopy data, particularly focusing on **carbonaceous materials** (e.g., graphene, carbon nanotubes).

It streamlines the entire workflow from raw data import to quantitative material property extraction, eliminating the need for complex desktop software.

📈 Screenshots from the application: 


![Screen from app](img%20(1).png)

#### 🔍 Peak Detection Visualization
The "Peak Detection" screen displays the results of automatic peak identification within a Raman spectrum (example for CNT-COOH_c.txt). The overlaid interactive Plotly chart visualizes 11 detected peaks (marked with a red 'X'), based on defined parameters such as Minimum height (0.15) and Prominence (0.08).

![Screen from app](img%20(2).png)

#### 📊 Loaded Spectrum Overview
The **"Data Overview"** screen serves as the analysis starting point. It displays **metadata** for the loaded file (e.g., CNT-COOH\_c.txt), including the **number of data points** (7070), the **Wavenumber Range** (603.2 - 3400.0 cm^{-1}), and the minimum and maximum intensity values. The **"Data validation passed"** section confirms that the data format is correct before commencing the processing workflow.

![Screen from app](img%20(3).png)

#### 📈 Spectrum Normalization Comparison
The **"Preprocessing"** tab allows you to select a normalization method. The screenshot shows a comparison of the original spectrum (left, blue) with the normalized spectrum (right, green) using the **Min-Max** method. This method scales intensities to the range [0, 1], which is crucial for sample comparison and ensuring data consistency for peak detection algorithms.


## 🛠️ Key Features and Workflow

The application implements a full-featured spectroscopy workflow across several tabs:

* **Data Handling:** Supports easy upload of single or multiple `.txt` files with Wavenumber and Intensity columns. Includes data **validation** and metadata extraction.
* **Preprocessing:** Essential steps to prepare spectra for analysis:
    * **Baseline Correction:** Algorithms including **Linear (Endpoints)** and **Asymmetric Least Squares (ALS)** to remove fluorescence background. 
    * **Normalization:** Methods like Min-Max, Max-Intensity, Area, and Vector (L2) normalization for comparison.
    * **Smoothing:** Optional Savitzky-Golay filtering to reduce noise.
* **Peak Analysis:** Automated detection and categorization of Raman bands (such as **D, G, RBM, 2D bands** for carbon materials). Calculates fundamental peak statistics.
* **Quantitative Fitting & Deconvolution:** Advanced fitting using **Lorentzian** or **Gaussian** models for precise deconvolution of overlapping bands (e.g., D and G bands). This allows calculation of critical ratios.
* **Material Characterization:** Calculates key material parameters based on fitting results, such as:
    * The **$I_D/I_G$ ratio**, crucial for determining defect density/crystallinity.
    * The **$I_{2D}/I_G$ ratio**, critical for characterizing the number of graphene layers.
* **Visualization & Export:** Interactive plots (Plotly) at every stage of the pipeline and the ability to export final results.

## 💻 Technical Stack

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend/App** | **Streamlit** | Rapid web application development and interactive UI/UX. |
| **Data Processing** | **Python (Pandas, NumPy)** | Core data manipulation and scientific computing. |
| **Signal Processing** | **SciPy** | Implementation of advanced algorithms (Savitzky-Golay, Peak Detection, ALS). |
| **Peak Fitting** | **LMFIT** (Implied by functionality) | Non-linear least squares minimization for peak deconvolution. |
| **Visualization** | **Plotly** / **Matplotlib** | Generating responsive, interactive data visualizations. |

## 🌟 Contributions and Impact

This project showcases expertise in:

* **Scientific Software Development:** Creating reliable, user-friendly tools for specialized scientific domains.
* **Signal and Data Processing:** Applying statistical methods to complex spectral data.
* **Chemical/Materials Informatics:** Direct application of computational tools to characterize physical properties from spectroscopic data.

## 🔗 Project Links

* <a href="https://raman-spectroscopy-analyzer.streamlit.app/" target="_blank">Project Page</a>
* <a href="https://github.com/slastrzelec/04_Raman-Spectroscopy-Analyzer" target="_blank">GitHub Repository</a>

