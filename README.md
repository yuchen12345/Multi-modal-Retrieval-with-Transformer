# Multi-modal-Retrieval-with-Transformer

## Overview
This project studies cross-modal retrieval by comparing a baseline dual-encoder model with an advanced model that incorporates cross-attention.

## Repository Structure
```text
.
├── baseline/ # baseline model training
├── other_attempts/ # additional experiments and trials
├── results/ # some evaluation results and figures
├── advanced_model_final.ipynb # final advanced model implementation and training
└── demo_baseline_vs_advanced.ipynb # evaluation script(including sample input-output)
```

## Dataset
The following 2 datasets are used:
- Flickr30k (initial experiments)
- MSCOCO (final training and evaluation)

## Environment Setup
Please refer to `requirements.txt` for all required packages. Install them using:
```bash
pip install -r requirements.txt
```
## How to Run
This project is mainly organized as Jupyter notebooks:
- Open the notebooks in Jupyter Notebook or VS Code.
- Run the cells in order from top to bottom.

### Main notebooks
- `baseline/baseline_ViT.ipynb`
  Notebook for the baseline model (ViT+BERT), including model setup, training and evaluation.
  
- `advanced_model_final.ipynb`  
  Main notebook for the final advanced model (ViT+BERT+cross attention), including final model setup, training and evaluation.

- `demo_baseline_vs_advanced.ipynb`  
  Main evaluation notebook for comparing the baseline and advanced models. This notebook includes:
  - Recall@K results for image-to-text and text-to-image retrieval
  - qualitative retrieval examples
  - comparison between baseline and advanced models
  
### Additional folders
- `baseline/`  
  Contains baseline model notebooks using both ViT and ResNet as visual encoders.

- `other_attempts/`  
  Contains exploratory experiments, ablation studies, and intermediate model variants.

- `results/`  
  Stores exported figures, tables, qualitative outputs, and other materials used in the final report.

## Results
Some example results can be found in the results folder.

All experiments are conducted on the MSCOCO test split. The team evaluate both image-to-text and text-to-image retrieval using 2000 test samples, with random seed fixed to 42. Also, caption max length is set as 64, and the re-ranking stage refines the top-20 candidates from the coarse retrieval results (with 20 as a hyperparameter).

Both quantitative and qualitative experiments on the MSCOCO dataset show that the advanced model significantly improves Recall@K over the baseline, while cross-attention based re-ranking provides limited additional gains. 
