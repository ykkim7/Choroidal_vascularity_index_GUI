# OCT Choroid Analyzer

A Python-based GUI application for the semi-automated analysis of **Choroidal Vascularity Index (CVI)** and **Subfoveal Choroidal Thickness (SCT)**. 

> [!IMPORTANT]
> This application is optimized for **Heidelberg Spectralis OCT** images. Using images from other devices may require manual scale adjustment.

## 🚀 Key Features
* **Automated Scale Detection**: Automatically detects vertical and horizontal scales from Spectralis scale bar lines.
* **Semi-Automated Segmentation**: RPE and Choroidal-Scleral Interface (CSI) detection with intuitive manual refinement.
* **Spline Interpolation**: Uses **Natural Cubic Splines** to provide smooth, anatomically natural boundary lines.
* **Subfield Analysis**: Automatically calculates metrics for 1500μm, 3000μm, and 5000μm ranges.
* **Batch Export**: Saves structured results in Excel (.xlsx) and generates visualization grids for verification.

## 📖 How to Use
1. **Upload Image**: Click `Upload Image` to load your EDI-OCT file. 
    * *Tip: You can use the included `sample_OCT_image.jpg` to test the workflow.*
2. **Automated Processing**: Click `Detect Scale Bar & RPE` to initialize.
3. **Manual Refinement**:
    * Use `Edit RPE Line` or `Draw/Edit Choroid Line` to adjust boundaries.
    * **Pro Tip for RPE**: If the automated RPE detection is inaccurate, you can **drag-select all control points**, **right-click** to delete them at once, and then manually plot new points for a cleaner result.
    * Boundaries are automatically smoothed via spline interpolation as you add/move points.
4. **Find Center**: Click `Find Center` and drag the yellow dashed line to the foveal center.
5. **Calculate & Save**: Click `Calculate CVI & Save`. Results are stored in a subfolder named after the image.

## 📊 Analysis Parameters & Output
The analysis utilizes the **Niblack Method** (Window size: 25, k: -0.2) for binarization.

### Excel Output Fields
The exported `.xlsx` file includes the following parameters:
* **SCA**: Total Stromal & Choroidal Area.
* **LA**: Luminal Area (Vessel area).
* **LA_d**: Luminal Area after **Despeckling**.
* **CVI / CVI_d**: Choroidal Vascularity Index (Raw / Despeckled).
* **SCT**: Subfoveal Choroidal Thickness at the selected center.
* **Avg_CT**: Average Choroidal Thickness within the specified range.

> [!NOTE]
> **What does "_d" mean?**
> Parameters marked with **_d** (e.g., `LA_d`, `CVI_d`) represent results after **Despeckling**. Small noise particles (< 10 pixels) are removed to reduce noise and provide a cleaner luminal area calculation.



## 📥 Installation & Requirements
* **Standalone Version**: Go to the [Releases](https://github.com/ykkim7/Choroidal_vascularity_index_GUI/releases/tag/v2.2) page and download `CVI_GUI_v2_2.exe`. (No Python installation required for the .exe version).
* **Source Version**: Requires Python 3.9, `OpenCV`, `PyQt5`, `scikit-image`, `scipy`, and `openpyxl`.
