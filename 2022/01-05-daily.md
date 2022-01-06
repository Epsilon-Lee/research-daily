
## ODQA Project

### Runnning ColBERT

The ColBERT repos is [here](https://github.com/stanford-futuredata/ColBERT).

- Installation is simply facilitated by `conda` environment created from officially provided `yaml` file
- How to train and evaluate ColBERT on MS Marco
  1. Preparing data
    - 
  2. Train script
    ```bash
    TRAIN_DATA=/home/cqduan/workspace/dataset/msmarco
    EXP=/home/cqduan/workspace/odqa/ColBERT_experiment
    CUDA_VISIBLE_DEVICES="0,1,2,3" \
    python -m torch.distributed.launch --nproc_per_node=4 -m \
    colbert.train --amp --doc_maxlen 180 --mask-punctuation --bsize 32 --accum 1 \
    --triples $TRAIN_DATA/triples.train.small.tsv \
    --root $EXP/ --experiment MSMARCO-psg --similarity l2 --run msmarco.psg.l2
    ```

- Troubleshooting
  - Use `pip install faiss-cpu --no-cache` to solve `ModuleNotFoundError: No module named '_swigfaiss'` issue
