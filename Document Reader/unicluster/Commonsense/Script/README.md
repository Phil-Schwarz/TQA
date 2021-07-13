# Explanation of `Ex01.ipynb`, `Ex02.ipynb` and `Ex03.ipynb` folder
The models are fine-tuned with context from document retriever part of Philippe Schwarze.
Common hyperparameter settings.
1. MAX_LEN = 512
2. NUM_LABELS = 4
3. label_map = {"A": 0, "B": 1, "C": 2, "D": 3}
4. BATCH_SIZE = 32

## LEARNING RATE
### `Ex01.ipynb`
LEARNING_RATE = 2e-5, base model is the model from `albert-base-v2`

### `Ex02.ipynb`
LEARNING_RATE = 5e-6, base model is the model from `dr_ex01-albert-commonsense-epoch=01-val_loss_epoch=1.066.ckpt`, it has lowest loss value on dev dataset.

### `Ex03.ipynb`
LEARNING_RATE = 5e-6, base model is the model from `dr_ex01-albert-commonsense-epoch=07-val_acc_epoch=0.609.ckpt`, it has highest accuracy score on dev dataset.

## Result analysis
1. For `Ex01.ipynb`, the best model with lowest loss value `dr_ex01-albert-commonsense-epoch=01-val_loss_epoch=1.066.ckpt` has accuracy score 60.9% on dev dataset. The model with highest accuracy score `dr_ex01-albert-commonsense-epoch=07-val_acc_epoch=0.609.ckpt` has accuracy score 56.4% on dev dataset.
2. For `Ex02.ipynb`, the best model is `dr_ex02-albert-commonsense-epoch=01-val_loss_epoch=1.437.ckpt`, it has accuracy score 59.6% on dev dataset.
3. For `Ex03.ipynb`, the best model is `dr_ex03-albert-commonsense-epoch=01-val_acc_epoch=0.574.ckpt`, it has accuracy score 61.5% on dev dataset.
