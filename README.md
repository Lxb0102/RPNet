# RPNet: Relation-aware pre-trained network with hierarchical aggregation mechanism for cold-start drug recommendation


## Installation


1. A new [conda environment](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/environments.html) is suggested. 

   ```bash
   conda create --name RPNet
   ```

2. Activate the newly created environment.

   ```bash
   conda activate RPNet
   ```

3. Install the required modules.

   Make sure your local environment has the following installed:

   ```bash
   sh install.sh
   ```


## Download the data

1. You must have obtained access to [MIMIC-III](https://physionet.org/content/mimiciii/) and [MIMIC-IV](https://physionet.org/content/mimiciv/) databases before running the code. 

2. Download the MIMIC-III and MIMIC-IV datasets, then unzip and put them in the `data/input/` directory. Specifically, you need to download the following files from MIMIC-III: `DIAGNOSES_ICD.csv`, `PRESCRIPTIONS.csv`, and `PROCEDURES_ICD.csv`, and the following files from MIMIC-IV: `DIAGNOSES_ICD.csv`, `PRESCRIPTIONS.csv`, and `PROCEDURES_ICD.csv`.

3. Download the [drugbank_drugs_info.csv](https://drive.google.com/file/d/1EzIlVeiIR6LFtrBnhzAth4fJt6H_ljxk/view?usp=sharing) and [drug-DDI.csv]( https://drive.google.com/file/d/1mnPc0O0ztz0fkv3HF-dpmBb8PLWsEoDz/view?usp=sharing) files, and put them in the `data/input/` directory.

## Process the data

Run the following command to process the data:

```bash
python process.py
```

If things go well, the processed data will be saved in the `data/output/` directory. You can run the models now!

## Run the models

Example:
```bash
python main_RPNet.py -nsp -mask    # pretrain and train      
python main_RPNet.py -t -l=log0    # test                   
```


For Baselines:
```bash
python main_GBert_pretrain.py
python main_GBert.py -p=0
python main_GBert.py -t -l=log1
```
```bash
python main_GAMENet.py
python main_GAMENet.py -t -l=log0
```

## Acknowledgement


This repository is partially based on the [RareMed](https://github.com/zzhUSTC2016/RAREMed) repository, you can find some additional details in the original repository.

Welcome to contact me xiaobo.li@dlmu.edu.cn for any question.
