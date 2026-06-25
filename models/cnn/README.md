# CNN Models

This folder contains the convolutional neural network (CNN) classification models built to classify brain CT scans into hemorrhage subtypes.

Four CNN variants were implemented and compared:

- **Sigmoid CNN** — multi-label output treating each hemorrhage type as an independent binary classification problem; showed clear overfitting
- **SoftMax CNN** — more appropriate for the dataset's mutually exclusive label structure; served as the foundation for further training
- **AI-assisted CNN** — exploratory model incorporating class weighting, data augmentation, and batch normalization; ultimately underperformed
- **Final SoftMax CNN** — the best performing model overall, achieving ~59% validation accuracy after 20 epochs of training with early stopping and learning rate reduction

## Files

- `cnn_models.ipynb` — full implementation of all four CNN variants including training, evaluation, and results
- `CNNmodel1.keras` — saved weights from the initial SoftMax CNN (15 epochs)
- `CNNImprovedModel.keras` — continued training checkpoint
- `CNNImprovedModel_best.keras` — best weights from the final training run (20 epochs total)
