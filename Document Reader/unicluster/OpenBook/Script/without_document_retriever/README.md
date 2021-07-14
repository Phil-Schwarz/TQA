# Explanation of `Try1`, `Try2` and `Try3` folder
The models are fine-tuned with context from OpenBook dataset.
Common hyperparameter settings.
1. MAX_LEN = 512
2. NUM_LABELS = 4
3. label_map = {"A": 0, "B": 1, "C": 2, "D": 3}
4. BATCH_SIZE = 32

## LEARNING RATE
### `Try1` folder
- In `Ex01.ipynb` LEARNING_RATE = 2e-5, base model is the model from `albert-base-v2`
- In `Ex02.ipynb` LEARNING_RATE = 2e-6, base model is the model from `albert-base-v2`
- In `Ex03.ipynb` LEARNING_RATE = 1e-6, base model is the model from `albert-base-v2`

### `Try2` folder with adaptive learning rate
- In `Ex01.ipynb` LEARNING_RATE = 2e-5, base model is the model from `albert-base-v2`
- In `Ex02.ipynb` LEARNING_RATE = 5e-6, base model is the model from `Try2/Ex01/ex01-albert-openbook-epoch=00-val_loss_epoch=0.90.ckpt`
- In `Ex03.ipynb` LEARNING_RATE = 2e-6, base model is the model from `Try2/Ex01/ex01-albert-openbook-epoch=00-val_loss_epoch=0.90.ckpt`

### `Try3` folder with adaptive learning rate
- In `Ex01.ipynb` LEARNING_RATE = 2e-6, base model is the model from `albert-base-v2`
- In `Ex02.ipynb` LEARNING_RATE = 5e-6, base model is the model from `Try2/Ex01/ex01-albert-openbook-epoch=00-val_loss_epoch=0.90.ckpt`
- In `Ex03.ipynb` LEARNING_RATE = 2e-6, base model is the model from `Try2/Ex01/ex01-albert-openbook-epoch=00-val_loss_epoch=0.90.ckpt`

## Result analysis
### fixed learning rate
| learning rate | name of checkpoint file | accuracy score on test dataset|
| :---:| :----:      |         :---:  |
| 1e-6 | Try1/Ex03/ex03-albert-openbook-epoch=05-val_loss_epoch=1.08.ckpt <br />  Try1/Ex03/ex03-albert-openbook-epoch=06-val_loss_epoch=1.08.ckpt  | 49.7%<br /> 48.8%|
| 2e-6 | Try1/Ex02/ex02-albert-openbook-epoch=04-val_loss_epoch=1.05.ckpt <br/> Try1/Ex02/ex02-albert-openbook-epoch=05-val_loss_epoch=1.07.ckpt <br/> Try3/Ex01/ex01-albert-openbook-epoch=04-val_loss_epoch=1.03.ckpt <br/> Try3/Ex01/ex01-albert-openbook-epoch=05-val_loss_epoch=1.03.ckpt| 61.7% <br/> 61.3% <br/> 59.2% <br/> 63.1%|
| 2e-5 | Try1/Ex01/ex01-albert-openbook-epoch=01-val_loss_epoch=0.76.ckpt <br/> Try1/Ex01/ex01-albert-openbook-epoch=02-val_loss_epoch=0.78.ckpt <br/> Try2/Ex01/ex01-albert-openbook-epoch=00-val_loss_epoch=0.90.ckpt <br/> Try2/Ex01/ex01-albert-openbook-epoch=01-val_loss_epoch=1.04.ckpt | 65.6% <br/> 64.1% <br/> 60.5% <br/> 64.6%|

### adaptive learning rate
Start learning rate is chosen with 2e-5 according to ZeroQA paper. So the model with checkpoint file `Try2/Ex01/ex01-albert-openbook-epoch=00-val_loss_epoch=0.90.ckpt` is chosen as base model.

| second learning rate | name of checkpoint file | accuracy score on test dataset|
| :---:| :----:      |         :---:  |
| 5e-6 | Try2/Ex02/ex02-albert-openbook-epoch=00-val_loss_epoch=0.98.ckpt <br/>  Try2/Ex02/ex02-albert-openbook-epoch=01-val_loss_epoch=0.97.ckpt <br/> Try3/Ex02/ex02-albert-openbook-epoch=04-val_loss_epoch=1.05.ckpt <br/> Try3/Ex02/ex02-albert-openbook-epoch=05-val_loss_epoch=1.07.ckpt | 58.3% <br/> 57.7% <br/> 56.9% <br/> 58.2%|
| 2e-6 | Try2/Ex03/ex03-albert-openbook-epoch=01-val_loss_epoch=0.87.ckpt <br/>  Try2/Ex03/ex03-albert-openbook-epoch=06-val_loss_epoch=0.93.ckpt <br/> Try3/Ex03/ex03-albert-openbook-epoch=05-val_loss_epoch=1.08.ckpt <br/> Try3/Ex03/ex03-albert-openbook-epoch=06-val_loss_epoch=1.08.ckpt | 60.4% <br/> 63.1% <br/> 61.2% <br/> 62.5%|
