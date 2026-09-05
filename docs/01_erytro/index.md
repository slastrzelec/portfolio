# 🔬 Erythrocyte Analysis App

## 🧬 Project Overview

This project is an interactive **Streamlit web application** for the **automated analysis of erythrocyte (red blood cell) morphology**.
Using computer vision (OpenCV) and scientific Python libraries, the app extracts key geometric parameters of red blood cells and identifies **shape anomalies**, which may indicate hematological disorders.

The application allows you to:

* Upload your own microscope image or use a sample one
* Automatically detect erythrocytes using contour analysis
* Calculate Shape Factor, Ellipticity, Area, Perimeter, and axis lengths
* Identify **normal vs. anomalous** erythrocytes
* Apply **calibration** to convert pixel-size values into micrometers
* Visualize data using multiple charts
* Download results as **CSV** or **Excel** files
* Download my associated **scientific publication** as a PDF

---

## 🎯 Key Features

### 📥 Image Input

* Upload your own `.jpg/.jpeg/.png` image
* Or load a default microscope image directly from GitHub
* Automatic error handling for corrupted files

---

### 🧪 Erythrocyte Shape Detection

The application performs:

* **Grayscale conversion**
* **Otsu’s thresholding** for automatic binarization
* **Contour extraction** using OpenCV
* **Ellipse fitting** for every detected erythrocyte
* Calculation of:

  * **Shape Factor** (major/minor axis)
  * **Ellipticity**
  * **Area**
  * **Perimeter**
  * **Major and Minor Axis lengths**

Cells are colour-coded:

* 🟢 Green — normal morphology
* 🟡 Yellow — moderately elongated
* 🔴 Red — highly elongated (potential anomaly)
* 🟣 Magenta — anomaly detected

---

### 📏 Calibration Mode (µm Conversion)

Users can provide a **µm-per-pixel calibration factor**.

When enabled, the app automatically adds:

* Major Axis (µm)
* Minor Axis (µm)
* Perimeter (µm)
* Area (µm²)

If calibration is disabled (value = 0), the measurements remain in **pixels**.

---

### 📊 Data Visualization

The app generates detailed scientific visualisations:

* **Scatter plot:** Shape Factor vs. Area, with anomaly threshold
* **Histogram:** Shape Factor distribution
* **Histogram:** Area distribution (px² or µm²)
* **Histogram:** Perimeter distribution
* **Binary mask preview** used internally for segmentation
* **Processed image** with detected cells and IDs

---

### 📋 Data Export

You can download all measurement results as:

* **CSV (.csv)**
* **Excel (.xlsx)**

Both export functions use caching for performance.

---

### 📖 Scientific Publication

The app also includes a downloadable PDF of my related research publication:

> *Functionalized carbon nanotubes and their acute effects on erythrocyte oxygen-binding properties.*

A highlighted abstract is shown inside the app, together with a direct download button.

---

## 🛠️ Tech Stack

* **Python**
* **Streamlit** — interactive UI
* **OpenCV (cv2)** — image processing
* **NumPy & Pandas** — scientific computing
* **Matplotlib** — visualizations
* **Requests** — loading remote files
* **OpenPyXL** — Excel export

---

## 🚀 Main Functional Flow

1. Load or upload an image
2. Preprocess & apply Otsu threshold
3. Detect contours and fit ellipses
4. Extract metrics for each detected erythrocyte
5. Classify as normal or anomalous
6. Apply calibration (optional)
7. Display processed images
8. Show statistics, charts, and tables
9. Allow CSV / Excel export

---

## 📁 Repository Structure (recommended)

```
📦 erythro-analysis-app
│
├── app.py                # Main Streamlit application
├── README.md             # Project documentation
├── publikacja.pdf        # Scientific publication
├── requirements.txt      # Dependencies
└── experimental_data/
        └── C.jpg         # Example microscope image
```

---

## 🎉 Summary

This project demonstrates how **computer vision, scientific analysis, and interactive UI** can be combined to support hematology research.
It automates time-consuming manual image interpretation and helps detect early morphological anomalies in erythrocytes — potentially supporting diagnostic workflows.
