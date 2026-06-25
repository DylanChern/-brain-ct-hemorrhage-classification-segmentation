# Baseline Models: Logistic Regression

This folder contains the baseline classification models implemented before moving to deep learning approaches. These models establish a performance benchmark and highlight the limitations of traditional machine learning methods for image-based classification tasks.

Three logistic regression variants were implemented:

- **Binary logistic regression** — classifies each CT scan as hemorrhage vs. normal; achieved ~93–95% test accuracy but cannot distinguish between hemorrhage subtypes
- **Multiclass SoftMax logistic regression** — predicts a single hemorrhage type per image; achieved ~31% test accuracy due to loss of spatial information when images are flattened into vectors
- **Multilabel sigmoid logistic regression** — one-vs-rest approach allowing multiple simultaneous class predictions; achieved ~14% test accuracy, reflecting a mismatch between the model formulation and the dataset's mutually exclusive label structure

## Files

- `baseline_models.ipynb` — full implementation of all three logistic regression variants including preprocessing, training, and evaluation
