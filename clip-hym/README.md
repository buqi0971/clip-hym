
## Setup
Execute below scripts in the main folder, to avoid download conflict when doing distributed pretrain.

```bash
mkdir modules/bert-base-uncased
cd modules/bert-base-uncased/
wget https://s3.amazonaws.com/models.huggingface.co/bert/bert-base-uncased-vocab.txt
mv bert-base-uncased-vocab.txt vocab.txt
wget https://s3.amazonaws.com/models.huggingface.co/bert/bert-base-uncased.tar.gz
tar -xvf bert-base-uncased.tar.gz
rm bert-base-uncased.tar.gz
cd ../../
```

Prepare the conda environment:
```bash
conda create -n clip python=3.6.9 tqdm boto3 requests pandas
conda activate clip
pip install torch==1.10.2 torchvision --extra-index-url https://download.pytorch.org/whl/cu113
pip install git+https://github.com/Maluuba/nlg-eval.git@master
pip install pycocoevalcap
pip install pickle5
pip install opencv-python==4.5.5.62
```

Download the pretrained weight of UniVL:
```bash
mkdir -p ./weight
wget -P ./weight https://github.com/microsoft/UniVL/releases/download/v0/univl.pretrained.bin
```

