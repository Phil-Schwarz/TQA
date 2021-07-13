# Explanation of `Ex01.ipynb`, `Ex02.ipynb` and `Ex03.ipynb` folder
The models are fine-tuned with context from Cosmos dataset.
Common hyperparameter settings.
1. MAX_LEN = 512
2. NUM_LABELS = 4
3. label_map = {"A": 0, "B": 1, "C": 2, "D": 3}
4. BATCH_SIZE = 32

## Fixed LEARNING RATE
### `Ex01.ipynb`
In `Ex01.ipynb` LEARNING_RATE = 2e-6, base model is the model from `albert-base-v2`

### `Ex01.ipynb`
In `Ex02.ipynb` LEARNING_RATE = 5e-6, base model is the model from `albert-base-v2`

### `Ex01.ipynb`
In `Ex03.ipynb` LEARNING_RATE = 2e-5, base model is the model from `albert-base-v2`

## Result analysis
Detailed results you can find in `eval_train_dev_dataset_cosmos.ipynb`.
1. `Ex01.ipynb`, the best model is `ex01-albert-cosmos-epoch=02-val_loss_epoch=1.10.ckpt`, it has accuracy score 56.6% on dev dataset.
2. `Ex02.ipynb`, the best model is `ex02-albert-cosmos-epoch=03-val_acc_epoch=0.588.ckpt`, it has accuracy score 59.5% on dev dataset.
3. `Ex03.ipynb`, the best model is `ex03-albert-cosmos-epoch=01-val_acc_epoch=0.571.ckpt`, it has accuracy score 59.1% on dev dataset.