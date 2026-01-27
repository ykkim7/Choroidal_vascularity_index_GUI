# Choroidal_vascularity_index_GUI

OCT Choroid Analyzer
A Python-based GUI application for the semi-automated analysis of Choroidal Vascularity Index (CVI) and Subfoveal Choroidal Thickness (SCT) in EDI-OCT images.

🚀 Key Features
Automated Scale Detection: Detects vertical and horizontal scales using scale bar lines.

Semi-Automated Segmentation: RPE and Choroidal-Scleral Interface (CSI) detection with manual refinement.

Spline Interpolation: Provides smooth, anatomically accurate boundary lines using Natural Cubic Splines.

Subfield Analysis: Automatically calculates CVI for 1500μm, 3000μm, and 5000μm ranges.

Batch Export: Saves results in a structured Excel format (.xlsx) and generates visualization grid images.

📥 Installation

Go to the Releases page.

Download the latest CVI_Analyzer.exe.

Run the executable file (No Python installation required for the .exe version).

📖 How to Use
Upload Image: Click Upload Image to load your EDI-OCT file.

Automated Processing: Click Detect Scale Bar & RPE to initialize the analysis.

Manual Refinement:

Use Edit RPE Line or Draw/Edit Choroid Line to adjust boundaries.

Right-click on the image to add, remove, or batch-delete control points.

Boundaries are automatically smoothed via spline interpolation.

Find Center: Click Find Center and drag the yellow dashed line to the foveal center.

Calculate & Save: Click Calculate CVI & Save. The results will be stored in a new folder named after the image.

📊 Analysis Parameters
Binarization: Niblack Method (Window size: 25, k: -0.2)

Despeckling: Small particles (< 10 pixels) are removed to reduce noise.
