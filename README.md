# PMMR
PMMR is a tool for drug-target binding prediction.

All benchmark datasets can be found at ./data/. Data preprocessing can be referred to ./preprocessing/.

## Requirements:
python 3.7<br>
cudatoolkit 10.1.243<br>
cudnn 7.6.0<br>
pytorch 1.4.0<br>
numpy 1.16.4<br>
scikit-learn 0.21.2<br>
pandas 0.24.2<br>
scipy 1.3.0<br>
numba 0.44.1<br>
rdkit 2023.09.2<br>
esm 2.0.0<br>
transformers 4.35.2<br>

## Data preprocessing
Before running, please generate pre-trained features of proteins and drugs. If you want to perform affinity prediction tasks, taking the Davis data set as an example, you need to execute the following command:
```
python preprocessing/protein_pretrain/protein_dta.py --dataset davis
python preprocessing/compound.py --dataset davis
```
And if you want to perform classification task, please run the following code:
```
python preprocessing/protein_pretrain/protein_dti.py --dataset bindingdb
python preprocessing/compound.py --dataset bindingdb
```
## Training & Evaluation
If you want to train and test the affinity prediction task based on the data set we provide, please execute the following code:
```
python main.py --objective regression --dataset davis 
```
And if you want to train and test classification tasks, please execute the following code:
```
python main.py --objective classification --dataset bindingdb
```
