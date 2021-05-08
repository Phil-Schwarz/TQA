# Albert on OpenBook dataset
## Explanations of Folder
Only Experiment 7 uses "albert-large-v2", other expriments use "albert-base-v2".
### Result on the test dataset 
- All experiments are made with Google Colab using TPU from Google.
- Experiment will be in the following with the notation E. For example, E1 stands for Experiment 1.
- Experiment with base version of albert will not be marked. Experiment with large version of alber will be marked with L. E7L means experiment 7 with large version model.
- Experiment uses the context or fact from OpenBookQA dataset will not be marked. If Experiment uses facts from the Document Retriever by Phillippe, it will be marked with E*. For example, E8* means that it uses facts from the Document Retriever part.
- For all experiments, the epoch will be set to 100. 
- The accuracy on the test dataset is calculated with the weights which has a lowest loss on validation dataset. 

| MAX_LEN | Batch size = 8 | Batch size = 32|
| :---:   |    :----:      |         :---:  |
| 64      |      E1(52%)<br /> E3(59%) <br> E7L(37%)  | E2(60%)<br /> E3(64%)    |
| 256     | E6(57%) <br> E8*(61%)          | E5(56%)       |