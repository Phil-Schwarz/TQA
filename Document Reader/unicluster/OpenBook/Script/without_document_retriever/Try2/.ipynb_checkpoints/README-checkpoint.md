# Adaptive learning rate method
## A short description of *Try2* folder
Those four hyperparameters are used for all three experiments.
1. MAX_LEN = 512
2. NUM_LABELS = 4
3. label_map = {"A": 0, "B": 1, "C": 2, "D": 3}
4. BATCH_SIZE = 32

The only difference between three experiments are learning rate.
Two models with least loss values on dev dataset are saved using callback function from `pytorch_lightning`.
According to ZeroQA paper, when `batch_size = 32` is chosen, `learning rate = 2e-5` is a good choice.
First larger learning rate `learning rate = 2e-5` is used to do fine-tuning to speed up convergence and then smaller learning rate is used to reach better performance. 

### hyperparameters of `Ex01.ipynb`: 
1. LEARNING_RATE = 2e-5

Results are:
1. `ex01-albert-openbook-epoch=00-val_loss_epoch=0.90.ckpt`
2. `ex01-albert-openbook-epoch=01-val_loss_epoch=1.04.ckpt`

### hyperparameters of `Ex02.ipynb`: 
Loading checkpint file `ex01-albert-openbook-epoch=00-val_loss_epoch=0.90.ckpt` from `Ex01.ipynb` to do fine-tuning.
1. LEARNING_RATE = 5e-6

Results are:
1. `ex02-albert-openbook-epoch=00-val_loss_epoch=0.98.ckpt`
2. `ex02-albert-openbook-epoch=01-val_loss_epoch=0.97.ckpt`

### hyperparameters of `Ex03.ipynb`:
Loading checkpint file `ex01-albert-openbook-epoch=00-val_loss_epoch=0.90.ckpt` from `Ex01.ipynb` to do fine-tuning.
1. LEARNING_RATE = 2e-6

Results are:
1. `ex03-albert-openbook-epoch=01-val_loss_epoch=0.87.ckpt`
2. `ex03-albert-openbook-epoch=06-val_loss_epoch=0.93.ckpt`