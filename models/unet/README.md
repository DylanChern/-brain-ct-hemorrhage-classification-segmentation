# U-Net Segmentation

This folder contains the preprocessing pipeline and U-Net model used for pixel-level segmentation of brain hemorrhages. Unlike the classification models which predict hemorrhage type, the U-Net identifies the exact location of hemorrhagic regions at the pixel level.

The segmentation pipeline consists of two steps:

**Step 1 — Mask Generation (`data_mask_for_unet.ipynb`)**
Reads hand-annotated polygon coordinates from label CSV files and generates two types of segmentation masks for each CT image:
- **Binary masks** — white where hemorrhage is present, black elsewhere
- **Quad-level masks** — four distinct intensity levels representing background, brain tissue, skull, and hemorrhage region; provides richer supervision during training

3,000 normal (non-hemorrhage) CT images are also processed with all-black masks to address class imbalance.

**Step 2 — U-Net Model (`unet.ipynb`)**
Trains a U-Net architecture on the generated masks. The U-Net uses an encoder-decoder structure with skip connections that preserve fine-grained spatial detail, enabling precise pixel-level predictions. The model classifies each pixel into one of four anatomical categories: background, brain tissue, skull, and hemorrhage region.

The model achieved ~80% training accuracy and a Mean IoU of ~0.43 after 10 epochs, with no observed overfitting.

## Files

- `data_mask_for_unet.ipynb` — preprocessing pipeline for generating binary and quad-level segmentation masks
- `unet.ipynb` — U-Net model architecture, training loop, evaluation, and visualization of predictions
