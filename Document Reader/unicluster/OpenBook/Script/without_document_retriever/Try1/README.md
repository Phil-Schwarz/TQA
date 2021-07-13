### A short description of *Try1* folder
Those four hyperparameters are used for all three experiments.
1. MAX_LEN = 512
2. NUM_LABELS = 4
3. label_map = {"A": 0, "B": 1, "C": 2, "D": 3}
4. BATCH_SIZE = 32

The only difference between three experiments are learning rate.
Two models with least loss values on dev dataset are saved using callback function from `pytorch_lightning`.

#### hyperparameters of `Ex01.ipynb`: 
1. LEARNING_RATE = 2e-5

Results are:
1. `ex01-albert-openbook-epoch=01-val_loss_epoch=0.76.ckpt`
2. `ex01-albert-openbook-epoch=02-val_loss_epoch=0.78.ckpt`

#### hyperparameters of `Ex02.ipynb`: 
1. LEARNING_RATE = 2e-6

Results are:
1. `ex02-albert-openbook-epoch=04-val_loss_epoch=1.05.ckpt`
2. `ex02-albert-openbook-epoch=05-val_loss_epoch=1.07.ckpt`

#### hyperparameters of `Ex03.ipynb`: 
1. LEARNING_RATE = 1e-6

Results are:
1. `ex03-albert-openbook-epoch=05-val_loss_epoch=1.08.ckpt`
2. `ex03-albert-openbook-epoch=06-val_loss_epoch=1.08.ckpt`


