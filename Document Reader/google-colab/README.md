### Short introduction 
There are three subfolders. CosmosQA dataset, OpenBook dataset and RACE dataset. Limited to computational resources, i.e memory and GPU or TPU, fine-tuning are redone in unicluster. In this folder, some experiments with smaller batch size. e.g. batch size = 8 is chosen.
Please refer to each subfolder for more information of experiments on this dataset.

Note:
- Experiments in `google-colab` folder donot use fixed seed. This bug has been solved for experiments in `unicluster` folder, which means all models will be initialised with fixed seed in order to make sure reproducibility.
- Since in `google-colab` folder, limited to coputational resource, smaller batch size 8 will be used. But suggested from ZeroQA paper, batch size should be set to 32. So actually only checkpoints files from `unicluster` folder will be used for our transfer learning model. But the experiments give me the first intuition of how to do fine-tuning on these datasets for NLP tasks. 