# 📸 Online App for Detection of Cells and Crystals in Algae Images

This is an online Python application built with **Streamlit** that allows you to detect and analyze cells and crystals in bright-field (BF) and polarized light (PL) microscopy images at various scales (10 µm, 20 µm, 40 µm, 100 µm).

👉 **Live App:** [Launch here](https://appdetectorcrystals-dttdtr4f68yeu8bzuw9daa.streamlit.app/)

---

## 🧰 Features

- Upload paired BF and PL microscopy images
- Detect and segment cells and crystals
- Calculate areas, counts, and overlaps
- Associate crystals with individual cells
- Generate plots showing crystal percentages over time
- Export detailed datasets, segmented images, and plots
- Manage custom scale settings for precise area calculations

---

## 💻 Installation

### Prerequisites

- Python (3.8 or higher recommended)

### Required Python packages

```bash
pip install -r requirements.txt
```

**requirements.txt**

```
streamlit
numpy
scipy
scikit-image
opencv-python
Pillow
pandas
matplotlib
scikit-learn
openpyxl
xlsxwriter
```

---

## 🚀 Running the App Locally

```bash
streamlit run app.py
```

---

## 📂 Repository Structure

```
.
├── app.py             # Main Streamlit app script
├── requirements.txt   # List of Python dependencies
```

---

## 🖼️ Image Preparation

- **File naming:** Images must include a day number and letter (e.g., 1A, 1B, 1C).
- Example folders:
  ```
  - 1A, 1B, 1C   # Day 1
  - 2A, 2B, 2C   # Day 2
  - 3A, 3B, 3C   # Day 3
  ```
- Images will be grouped by day to generate plots and summary statistics.

---

## 🏷️ Available Functions

### 1️⃣ Number of Crystals

- Calculates the number and percentage of cells containing crystals per image.
- Generates a plot of crystal-containing cells (%) over days.
- Download options: individual image results and global summary.

### 2️⃣ Areas

- Calculates crystal areas and their percentage relative to cell areas per image.
- Generates a plot of crystal area percentage over days.
- Download options: datasets, images, histograms, and plots.

### 3️⃣ Number of Cells

- Calculates cell count and area per image.
- Outputs segmented images, overlap maps, and histograms.
- Download options: per image or for all images.

---

## 📏 Scales

- Built-in options: 20 um, 40 µm, 100 um and 200 µm.
- You can **add new scales** or **delete existing scales** from the app GUI.
- **Adding a new scale:**  
  Use ImageJ to calculate µm/pixel equivalence:
  - Draw a line on the scale bar in your image.
  - Go to *Analyze > Measure* in ImageJ to get pixel length.
  - Input the conversion in the app.

- **Deleting a scale:**  
  Select from the list and press **Delete Scale**.

---

## 💾 Output Files

All outputs (datasets, plots, images) are automatically saved to your **Downloads** folder.

### Dataset contents

- **Cells dataset (per image):** region labels, area in pixels and µm², total area, total cells.
- **Crystals dataset (per image):** region labels, associated cells, overlaps, area in pixels and µm², total area crystals, cells with crystals count.
- **Mapping dataset:** cell-to-crystal associations, crystal count per cell.
- **Summary dataset (per folder):** days, mean and standard deviation of percentages.
- **Merged dataset:** combined data of cells and crystals with overlap and area details.

---

## ⚠️ Important Notes

✅ After completing a batch processing:

1. Press **STOP** in the app.  
2. Refresh your browser before starting a new batch.

---

## 🙌 Acknowledgments

This tool was developed to assist in automated detection of crystals in *Chlamydomonas* algae microscopy images and can be adapted to other biological microscopy workflows.

---

## 📄 License

[MIT License](LICENSE)
