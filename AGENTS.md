# AGENTS.md — CNN vs Transfer Learning

## Project structure (required)
```
├── dataset/              # or link_dataset.txt pointing to Google Drive/Kaggle
├── notebook/
│   └── cnn_vs_transfer_learning.ipynb
├── report/
│   └── laporan.pdf       # max 10 pages, IEEE template
├── README.md
└── requirements.txt
```

Datasets are too large to commit — use a download link instead.

## Two experiments, two datasets

| Experiment | Dataset | Classes | Min images |
|---|---|---|---|
| **CNN from scratch** | CIFAR-10 (use 2 classes, e.g. cat vs dog, or pick any 2) | 2 | ≥200 total (100/100 split) |
| **Transfer Learning** | Cats vs Dogs (Kaggle) | 2 | ≥200 total (100/100 split) |

## CNN from scratch requirements
- Must include: Conv, Pooling, Activation, Flatten/GAP, Dense, Output layers
- No pretrained weights allowed
- Justify every architectural choice (layer count, filter size, optimizer, LR, batch size, epochs, regularization)

## Transfer Learning requirements
- Pick one: VGG16, ResNet50, MobileNetV2, EfficientNet, InceptionV3, or DenseNet
- Must apply at least one of: feature extraction (freeze all), fine-tuning (unfreeze some), or both (compare)
- Justify model choice

## Data split
- Train 70%, Validation 15%, Test 15%

## Required evaluation output (in notebook)
- Training/validation accuracy plot
- Training/validation loss plot
- Confusion matrix for both models
- Correct & incorrect prediction examples for both
- Training time, parameter count
- Overfitting risk assessment

## Required report sections (PDF, IEEE template)
1. Title + identity
2. Dataset description
3. Preprocessing
4. CNN implementation
5. Transfer Learning implementation
6. Results
7. Model comparison (use the 11-row table from rubric)
8. Analysis (when to use which)
9. Case study answers (4 scenarios)
10. Conclusion + personal reflection (5 reflection questions)

## Analysis questions the notebook must answer
- Which model performed best? Is high accuracy always better?
- Overfitting signs? Stability during training?
- When to use CNN vs transfer learning — consider: dataset size, domain similarity to ImageNet, compute/time budget, accuracy needs, overfitting risk, deployment ease
- 4 case study scenarios on medical (300 images), 1M product images, 2-day prototype (500 images), large dataset with GPU

## Key constraints from rubric
- A grade (≥80): strong architecture rationale, proper freeze/fine-tune strategy, thorough evaluation with all visualizations, objective comparison, analysis grounded in experimental data, personal reflection
- Must have preprocessing + augmentation explained
- Transfer learning without understanding strategy = low score
- "Which model has higher accuracy" alone is not enough — need deep comparison

## Tools
- Python 3.x, TensorFlow/Keras or PyTorch
- Install from `requirements.txt` (gunakan venv)
- Run notebook end-to-end; all outputs (plots, metrics) must be visible after execution

## Known issues
- CIFAR-10 official download URL (cs.toronto.edu/~kriz) returns HTTP 403.
  Notebook has fallback to synthetic data. Untuk data asli: download manual
  dan simpan di `~/.keras/datasets/cifar-10-batches-py.tar.gz`
- Gunakan `source venv/bin/activate` sebelum menjalankan notebook
- PDF bisa dibuat via: `jupyter nbconvert --to html notebook/... && python3 -c "from weasyprint import HTML; HTML('report/laporan.html').write_pdf('report/laporan.pdf')"`
