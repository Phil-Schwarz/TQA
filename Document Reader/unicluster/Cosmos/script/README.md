# Explanation of `adaptive_lr`, `high_lr` and `lr=2e-5`
Limited to time of this course and GPU-usage of Unicluster, only some basic experiments are been made.
`generate_cosmos_cache.ipynb` and `generate_cosmos_cache_1024.ipynb` are been used to generate cache files which can be used for fine-tuning. `operation.ipynb` is used as terminal to do some operations like copying or delete files. Detailed result analysis please refer to `README.md` in the subfolder.

## `adaptive_lr`
Adaptive learning rate method is been used.

## `high_lr`
Inspired by the idea of other group, very large learning rate is been used.

## `lr=2e-5`
According to ZeroQA paper, `learning_rate=2e-5` is been used.