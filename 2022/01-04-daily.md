
## ODQA Project

### DPR-based repos

- [DPR Original Repo](https://github.com/facebookresearch/DPR), from facebook, correspoinding to the original [DPR](https://arxiv.org/abs/2004.04906) paper.
- [Gradient Cached Dense Passage Retrieval](https://github.com/luyug/GC-DPR), this approach could increase in-batch negatives far beyond GPU RAM limitations.
- [DPR-scale](https://github.com/facebookresearch/dpr-scale), from facebook, corresponding to [this](https://arxiv.org/abs/2107.13602) paper.

### Understand training details of `DPR` `FiD` etc.

#### FiD and FiD for distillation

- [FiD Repo](https://github.com/facebookresearch/FiD).
- `get-data.sh`: as said in the above repo's readme file, this bash script *"In addition to the question and answers, this script retrieves the Wikipedia passages used to trained the released pretrained models."*
  - `preprocess.py`:
    -  `passages`   : is the whole 13G wikipedia passage collection preprocessed by `DPR Repo`
    -  `NQ_passages`: is the retrieved passages for each question in train/dev/test set
    -  `NQ_idx`     : is paired with `NQ_passages`, which is the question_id

```python
NQ_test = select_examples_NQ(originaldev, NQ_idx['test'], passages, NQ_passages['test'])
```
- Train an FiD model with 8 GPU P8, each 24G GPU ram, training script:
```bash
CODE=/home/cqduan/workspace/odqa/FiD
DATA=/home/cqduan/workspace/odqa/FiD/open_domain_data/NQ
EXP=/home/cqduan/workspace/odqa/FiD_experiment
python $CODE/train_reader.py \
  --train_data $DATA/train.json \
  --eval_data  $DATA/dev.json \
  --model_size base \
  --per_gpu_batch 1 \
  --n_context 100 \
  --name $EXP \
  --checkpoint_dir $EXP/checkpoint \
```

- When running the above script, several following errors should be resolved.
- 
```bash

# HuggingFace Transformer package

Traceback (most recent call last):
  File "/home/cqduan/workspace/odqa/FiD/train_reader.py", line 10, in <module>
    import transformers
ModuleNotFoundError: No module named 'transformers'

# SentencePiece
Traceback (most recent call last):
  File "/home/cqduan/workspace/odqa/FiD/train_reader.py", line 156, in <module>
    tokenizer = transformers.T5Tokenizer.from_pretrained(model_name)
  File "/home/cqduan/anaconda3/lib/python3.7/site-packages/transformers/utils/dummy_sentencepiece_objects.py", line 173, in from_pretrained
    requires_backends(cls, ["sentencepiece"])
  File "/home/cqduan/anaconda3/lib/python3.7/site-packages/transformers/file_utils.py", line 822, in requires_backends
    raise ImportError("".join([BACKENDS_MAPPING[backend][1].format(name) for backend in backends]))
ImportError:
T5Tokenizer requires the SentencePiece library but it was not found in your environment. Checkout the instructions on the
installation page of its repo: https://github.com/google/sentencepiece#installation and follow the ones
that match your environment.

```
