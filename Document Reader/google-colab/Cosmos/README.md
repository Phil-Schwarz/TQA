# Albert models on CosmosQA dataset

## Results on the dev dataset 
1. TPU or GPU
    All experiments are made with Google Colab using TPU from Google.
2. Notation of Albertmodel
    - All Experiments with AlbertModel will be in the following with the notation A. For example, E1 stands for Experiment 1 which corresponding to Folder E1.
4. Epoch
    - Expect Experiment 6, the epoch for all other experiments is set to 10. 
    - For Experiment 5, the epoch is 20.
5. Batch size and max length of tokenizer
    - Subject to the limited computational resource, batch size is set to 8.
    - Acoording to ZeroQA paper, MAX_LEN of tokenizer is set to 256.
5. Optimizer
    - Acoording to ZeroQA paper, the optimizer is been chosen as Adam.
5. Loss value on dev dataset
    - Since no labels for test dataset are availiable for Cosmos, so loss value on dev dataset will be used.

| Epoch | lr = 2e-6 | lr = 5e-6 | lr = 7e-6 | lr = 1e-5 |  
| :---: | :----: | :---: | :---: | :---: |
| 10    | E2(1.13)| E1(1.01)|E4(0.93)|E3(1.09)|
| 20    ||| E5(0.99)||



