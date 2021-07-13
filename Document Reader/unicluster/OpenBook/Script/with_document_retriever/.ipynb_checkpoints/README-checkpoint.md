# Short explanation of the name `with_document_retriever`
The models are fine-tuned with context from document retriever part of Phillippe Schwarz.
Different start learning rate will be used to find the best one.

## start_learning rate=1e-5
1. `Ex01_DR.ipynb` uses learning rate 1e-5, base model is `albert-base-v2`
2. `Ex02_DR.ipynb` uses learning rate 5e-6, base model is the model which loads the checkpoint file `dr_ex01-albert-openbook-epoch=02-val_loss_epoch=1.220.ckpt`. This checkpoint file has the second lowest loss value on dev dataset.
Based on the results of `Ex02_DR.ipynb`, no further experiments are not been made, since the model seems to be already overfitting.

Results:
1. After first fine-tuning with `learning_rate=1e-5`, the best model `dr_ex01-albert-openbook-epoch=02-val_loss_epoch=1.220.ckpt` on test dataset has the 52%. It is used as base model for second fine-tuning.
2. After second fine-tuning with `learning_rate=5e-6`, the best model `dr_ex02-albert-openbook-epoch=01-val_loss_epoch=1.766.ckpt` on test dataset has the 50%. After analysis the model is already overfitting. So no more experiments are made.

## start_learning rate=2e-5
1. `Ex01.ipynb` uses learning rate 2e-5, base model is `albert-base-v2`
2. `Ex02.ipynb` uses learning rate 5e-6, base model is the model which loads the checkpoint file `dr_ex01-albert-openbook-epoch=02-val_acc_epoch=0.557.ckpt`. This checkpoint file has the highest accuracy score on dev dataset.
3. `Ex03.ipynb` uses learning rate 5e-6, base model is the model which loads the checkpoint file `dr_ex01-albert-openbook-epoch=01-val_loss_epoch=1.106.ckpt`. This checkpoint file has the lowest loss value on dev dataset. 

Results:
1. After first fine-tuning with `learning_rate=1e-5`, the checkpoint file `dr_ex01-albert-openbook-epoch=02-val_acc_epoch=0.557.ckpt` on test dataset has the 55%. It is used as base model for second fine-tuning. The checkpoint file `dr_ex01-albert-openbook-epoch=01-val_loss_epoch=1.106.ckpt` on test dataset has the 51.7%. It is used as base model for third fine-tuning.
2. After second fine-tuning with `learning_rate=5e-6`, the best model `dr_ex02-albert-openbook-epoch=04-val_acc_epoch=0.589.ckpt` on test dataset has the 50.2%. After analysis the model is already overfitting. So no more experiments with smaller learning rate are not been made. Otherwise, the checkpoint file with highest accuracy score on dev dataset will be used for third fine-tuning.
3. After third fine-tuning with `learning_rate=5e-6`, the best model `dr_ex03-albert-openbook-epoch=02-val_acc_epoch=0.596.ckpt` on test dataset has the 53.5%. After analysis the model is already a little bit overfitting. So no more experiments are made.

## start_learning rate=2e-6
1. `Ex01_DR.ipynb` uses learning rate 2e-6, base model is `albert-base-v2`

## start_learning rate=3e-5
1. `Ex01_DR.ipynb` uses learning rate 3e-5, base model is `albert-base-v2`
2. `Ex02_DR.ipynb` uses learning rate 1e-5, base model is the model which loads the checkpoint file `dr_ex01-albert-openbook-epoch=00-val_loss_epoch=1.301.ckpt`. This checkpoint file has the lowest loss value on dev dataset. 
3. `Ex03_DR.ipynb` uses learning rate 5e-6, base model is the model which loads the checkpoint file `dr_ex02-albert-openbook-epoch=01-val_loss_epoch=1.233.ckpt`. This checkpoint file has the lowest loss value on dev dataset. 

Results:
1. After first fine-tuning with `learning_rate=3e-5`, the best model `dr_ex01-albert-openbook-epoch=00-val_loss_epoch=1.301.ckpt` on test dataset has the 42.3%. It is used as base model for second fine-tuning.
2. After second fine-tuning with `learning_rate=1e-5`, the best model `dr_ex02-albert-openbook-epoch=01-val_loss_epoch=1.233.ckpt` on test dataset has the 46.1%. It is used as base model for third fine-tuning.
3. After third fine-tuning with `learning_rate=5e-6`, the best model `dr_ex02-albert-openbook-epoch=00-val_loss_epoch=1.154.ckpt` on test dataset has the 47.8%. It is used as base model for third fine-tuning.

## start_learning rate=5e-6
1. `Ex01_DR.ipynb` uses learning rate 5e-6, base model is `albert-base-v2`
2. `Ex02_DR.ipynb` uses learning rate 2e-6, base model is the model which loads the checkpoint file `dr_ex01-albert-openbook-epoch=02-val_loss_epoch=1.307.ckpt`. This checkpoint file has the second lowest loss value on dev dataset. 

Results:
1. After first fine-tuning with `learning_rate=5e-6`, the checkpoint file `dr_ex01-albert-openbook-epoch=02-val_loss_epoch=1.307.ckpt` on test dataset has the 43.7%. It is used as base model for second fine-tuning. 
2. After second fine-tuning with `learning_rate=5e-6`, the best model `dr_ex02-albert-openbook-epoch=00-val_acc_epoch=0.399.ckpt` on test dataset has the 46.7%. After analysis the model is already overfitting. So no more experiments with smaller learning rate are not been made.