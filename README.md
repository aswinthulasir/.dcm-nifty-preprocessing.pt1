# 🧠 Medical Imaging Preprocessing using DICOM

This repository contains a Jupyter Notebook (`Preprocessing.ipynb`) for preprocessing medical imaging data in DICOM format. It includes tools to read, visualize, and process DICOM files using Python.

---

## 📁 Project Structure

```
.
├── Preprocessing.ipynb        # Main notebook for preprocessing
├── dicom/                     # Folder where you place your DICOM files
│   └── [Your DICOM files here]
├── README.md                  # This file
```

---

## 📦 Installation

To run this notebook, you'll need Python and the following libraries:

```bash
pip install pydicom matplotlib numpy
```

Or inside Google Colab:

```python
!pip install pydicom matplotlib numpy
```

---

## How to Use

1. Clone this repository or upload your own DICOM files into the `dicom/` folder.
2. Open `Preprocessing.ipynb` using Jupyter or Google Colab.
3. Run the cells in order:
   - Mount Google Drive (if using Colab)
   - Install dependencies
   - Read and parse DICOM files
   - Visualize slices using `matplotlib`

---

##  Features

- Load and parse `.dcm` files using `pydicom`
-  Visualize DICOM slices using `matplotlib`
-  Normalize and extract image data
-  Error handling for common DICOM issues
-  Directory iteration to process batches of files

---

## 📸 Example Code

```python
import pydicom
import matplotlib.pyplot as plt

# Load a DICOM file
ds = pydicom.dcmread("dicom/sample.dcm")

# Display the image slice
plt.imshow(ds.pixel_array, cmap='gray')
plt.title("DICOM Slice")
plt.axis('off')
plt.show()
```

---

## 🛠 Troubleshooting

- **`IsADirectoryError`**: Make sure to skip system folders like `.ipynb_checkpoints`.
- **`AttributeError: 'pydicom' has no attribute 'read_file'`**: Use `pydicom.dcmread()` instead of `read_file`.
- **Multi-frame / 3D DICOMs**: For multi-slice images, consider using libraries like `SimpleITK` or `dicom2nifti`.

---

##  References

- 📘 [pydicom Documentation](https://pydicom.github.io/)
- 🔧 [SimpleITK Docs](https://simpleitk.readthedocs.io/en/master/)
- 🔁 [dicom2nifti GitHub](https://github.com/icometrix/dicom2nifti)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
