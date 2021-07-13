# Albert models on RACE dataset

## Result on the test dataset 
1. TPU or GPU
    All experiments are made with Google Colab using TPU from Google.
2. Notation of Albertmodel
    - All Experiments with AlbertModel will be in the following with the notation A. For example, A1 stands for Experiment 1.
4. Epoch
    - Expect Experiment 6, the epoch for all other experiments is set to 100. 
    - For Experiment 6, the epoch is 20.
5. Batch size and max length of tokenizer
    - Subject to the limited computational resource, batch size is set to 8.
    - Acoording to ZeroQA paper, MAX_LEN of tokenizer is set to 256.
5. Optimizer
    - Acoording to ZeroQA paper, the optimizer is been chosen Adam.
5. Accuracy score on test dataset
    - The accuracy on the test dataset is calculated with the weights which has a lowest loss on validation dataset. 

| Epoch | lr = 2e-5 | lr = 1e-5 | lr = 5e-6 | lr = 2e-6 | lr = 1e-6 |  
| :---: | :----: | :---: | :---: | :---: | :---: |
| 10    | A1(44.87%)| A2(52.47%)|A3(54.36%)|A4(54.64%)|A5(50.93%)|
| 20    ||||| A6(53.11%)|



