# start_lr=2e-6
For CosmosQA dataset, no labels for test dataset are availiable. So in order to choose a better model for transfer-learning model, the model will be evaluated in dev dataset. Detailed results of this experiments you can find in `eval_train_dev_dataset_cosmos.ipynb`.

## Experiments
Adaptive learning rate method doesnot work on OpenBook dataset, but works on RACE dataset. A possible reason might be that RACE dataset is much larger than OpenBook dataset. Although according to ZeroQA paper, learning rate should be chosen as 2e-5 with `batch size = 32`. A much smaller learning rate will be chosen for adaptive learning rate method considering the size of Cosmos dataset and the results from OpenBook dataset.

### `cosmos_adaptive_lr=2e-6_ex01.ipynb`
Start learning rate 2e-6 will be used. Base model is `albert-base-v2`.

### `cosmos_adaptive_lr=2e-6_ex02.ipynb`
A smaller learning rate 1e-6 will be used. Base model is `ex01-albert-cosmos-epoch=02-val_loss_epoch=1.08.ckpt` which has the lowest loss value on dev dataset.

## Results
1. `cosmos_adaptive_lr=2e-6_ex01.ipynb`, the best model on dev dataset is `ex01-albert-cosmos-epoch=02-val_loss_epoch=1.08.ckpt`, it has accuaracy score 53.5% on dev dateset. The model is used for second experiment.
2. `cosmos_adaptive_lr=2e-6_ex02.ipynb`, the best model on dev dataset is `ex02-albert-cosmos-epoch=00-val_loss_epoch=1.13.ckpt`, it has accuaracy score 54.4% on dev dateset.

So according to accuracy score on dev dataset, the adaptive learning rate method works on CosmosQA dataset.
