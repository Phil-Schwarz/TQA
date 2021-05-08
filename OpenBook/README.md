# Bert and other variants on OpenBook dataset
## Explanations of `Albert`Folder
Only Experiment 7 uses pre-trained weights **albert-large-v2**, other expriments use pre-trained weights **albert-base-v2**. More information see please under [this link](https://huggingface.co/albert-base-v2).

## Explanations of `Bert`Folder
All experiments with Bert model use pre-trained weights **bert-base-uncased**.
## Explanations of `DistilBert`Folder
All experiments with DistilBert model use pre-trained weights **distilbert-base-cased**.

## Result on the test dataset 
1. TPU or GPU
    - All experiments with AlbertModel are made with Google Colab using TPU from Google.
    - All experiments with BertModel are made with Google Colab using GPU from Google.
    - All experiments with DistilbertModel are made with Google Colab using TPU from Google.
2. Notation of Albert, Bert or DistilBert
    - All Experiments with AlbertModel will be in the following with the notation A. For example, E1 stands for Experiment 1.
    - All Experiments with BertModel will be in the following with the notation B. For example, B1 stands for Experiment 1.
    - All Experiments with DistilbertModel will be in the following with the notation D. For example, D1 stands for Experiment 1.
3. Special Mark
    - Experiment with base version of albert will not be marked. Experiment with large version of alber will be marked additional with L. For example, A7L means experiment 7 with large version model.
    - Experiment uses the context or fact from OpenBookQA dataset will not be marked. If Experiment uses facts from the Document Retriever by Phillippe, it will be additionally marked with *. For example, A8* means that it uses facts from the Document Retriever part.
4. Epoch
    - For all experiments, the epoch will be set to 100. 
5. Learning rate
    - According to ZeroQA paper, the learning rate is been chosen with 2e-5.
6. Optimizer
    - Acoording to ZeroQA paper, the optimizer is been chosen Adam.
5. Accuracy score on test dataset
    - The accuracy on the test dataset is calculated with the weights which has a lowest loss on validation dataset. 

| MAX_LEN | Batch size = 8 | Batch size = 32|
| :---:   |    :----:      |         :---:  |
| 64      |      A1(52%)<br /> A3(59%) <br> A7L(37%) <br>B1(29%)<br>D(53%)  | A2(60%)<br /> A3(64%)    |
| 256     | A6(57%) <br> A8*(61%)          | A5(56%)       |



