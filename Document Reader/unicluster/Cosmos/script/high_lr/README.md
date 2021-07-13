# higher learning rate
Inspired by the idea of other group, very large learning rate is been used. Detailed results see in `eval_train_dev_dataset_cosmos.ipynb`.
## learning rate = 3e-3
Two models are availiable after fine-tuning which have the least loss value or second least value on dev dataset. 
1. `ex01-albert-cosmos-epoch=01-val_loss_epoch=1.39.ckpt` has accuracy score 24.7% on dev dataset, 25.6% on train dataset.
2. `ex01-albert-cosmos-epoch=00-val_loss_epoch=1.39.ckpt` has accuracy score 22.1% on dev dataset, 25.1% on train dataset.
The results show that the models are heavily overfitting when using very large learning rate.

## learning rate = 1e-3
Two models are availiable after fine-tuning which have the least loss value or second least value on dev dataset. 
1. `ex01-albert-cosmos-epoch=03-val_loss_epoch=1.39.ckpt` has accuracy score 25.9% on dev dataset, 29.5% on train dataset.
2. `ex01-albert-cosmos-epoch=04-val_loss_epoch=1.39.ckpt` has accuracy score 26.8% on dev dataset, 26.5% on train dataset.
The results show that the models are heavily overfitting when using very large learning rate.
