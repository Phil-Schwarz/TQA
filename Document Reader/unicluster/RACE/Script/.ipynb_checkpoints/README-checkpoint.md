# Adaptive learning rate method on RACE dataset
`generate_race_cahce` generates caches of RACE dataset, which saves the time for processing dataset and initialise `dataloader`.
`eval_test_dataset_race.ipynb` and `eval_test_dataset_race_2.ipynb`evaluate chechpoints files on test dataset.

## General hyperparameter setting for fine-tuning on RACE dataset
1. MAX_LEN = 512
2. NUM_LABELS = 4
3. label_map = {"A": 0, "B": 1, "C": 2, "D": 3}
4. BATCH_SIZE = 32
5. no_decay = ['bias', 'LayerNorm.weight']
   weight_decay = 0.0
   adam_epsilon = 1e-8
   optimizer_grouped_parameters = [
        {
            'params': [p for n, p in self.model.named_parameters() if not any(nd in n for nd in no_decay)],
            'weight_decay': weight_decay
            },
        {
            'params': [p for n, p in self.model.named_parameters() if any(nd in n for nd in no_decay)],
            'weight_decay': 0.0,
            }
        ]
   optimizer = AdamW(optimizer_grouped_parameters, lr=LEARNING_RATE, eps=adam_epsilon)

## Adaptive learning rate on `ex01.ipynb`, `ex02.ipynb` and `ex03.ipynb`
### `ex01.ipynb`
First `learning rate = 2e-5` is used and the base model is `albert-base-v2`. It was designed to do fine-tuning with 10 epoches. But it crushed because of time limit of unicluster. So the checkpoint file which was automatically saved by `callbackfuntion` is used in `ex02.ipynb`. 

### `ex02.ipynb`
Then `learning rate = 2e-5` is also used and the base model is `e1-albert-race-epoch=00-val_loss_epoch=0.78.ckpt`. It is trained with 3 epoches. And the checkpoint file will be used in `ex03.ipynb`.

### `ex03.ipynb`
At last `learning rate = 2e-6` is used and the base model is `e2-albert-race-epoch=00-val_loss_epoch=0.77.ckpt`. It is trained with 10 epoches. The checkpoint file which has the least loss value on test dataset will be saved automatically by `callbackfunction`.

## Results
1. The best model of `ex01.ipynb` is `e1-albert-race-epoch=00-val_loss_epoch=0.78.ckpt`. Since the kernel of unicluster crushed. Its accuracy on test dataset is 67.1%.
2. The best model of `ex02.ipynb` is `e2-albert-race-epoch=00-val_loss_epoch=0.77.ckpt`. Its accuracy on test dataset is 68.0%.
3. The best model of `ex03.ipynb` is `e3-albert-race-epoch=00-val_loss_epoch=0.97.ckpt`. Its accuracy on test dataset is 72.0%.