# Lipneting

Lipneting is a deep learning-based lip‑reading model that translates silent video clips of lip movements into text. This repository contains the end‑to‑end implementation, from data preprocessing and model training to inference and evaluation.

---

## 📁 Project Structure

```txt
Lipneting/
├── data/                   # Raw and processed video data
│   ├── raw/                # Original video files (not tracked)
│   └── processed/          # Frame-extracted and preprocessed images
│
├── models/                 # Model definitions
│   ├── lipnet.py           # LipNet architecture definition
│   └── utils.py            # Helper functions (data loaders, augmentations)
│
├── notebooks/              # Jupyter notebooks for EDA and experiments
│   └── training_experiments.ipynb
│
├── checkpoints/            # Saved model weights
│
├── outputs/                # Training logs and evaluation results
│
├── README.md               # Project overview and instructions
├── requirements.txt        # Python dependencies
└── .gitignore
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/Lipneting.git
cd Lipneting
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Prepare the data

* Place raw video files in `data/raw/`.
* Run preprocessing to extract frames:

  ```bash
  python models/utils.py --mode preprocess --input data/raw/ --output data/processed/
  ```

### 4. Train the model

```bash
python models/lipnet.py --train --data_dir data/processed/ --epochs 50 --batch_size 16
```

### 5. Evaluate and Inference

```bash
python models/lipnet.py --evaluate --weights checkpoints/best_model.h5
python models/lipnet.py --infer --video samples/lip_clip.mp4
```

---

## 📄 Requirements

See `requirements.txt` for exact versions:

```
TensorFlow>=2.4.0
opencv-python
numpy
pandas
matplotlib
scikit-learn
```

---

## 📡 Dataset

This project uses the GRID corpus for lip-reading experiments. Download instructions:

1. Go to [GRID Corpus](https://spandh.dcs.shef.ac.uk/gridcorpus/) and request access.
2. Unzip into `data/raw/GRID/`.

---

## 🤝 Contributing

Feel free to open issues or submit pull requests for improvements.

---

## 📜 License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
