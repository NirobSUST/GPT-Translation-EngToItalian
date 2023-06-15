﻿# GPT-Translation-EngToItalian
# Colab Training

%load_ext tensorboard

!pip install datasets
!pip install tokenizers
!pip install torchmetrics

from google.colab import drive
drive.mount('/content/drive')

!git clone https://github.com/NirobSUST/GPT-Translation-EngToItalian.git

%cd /content/GPT-Translation-EngToItalian

%tensorboard --logdir runs

!mkdir -p /content/drive/MyDrive/Models/GPT-Translation-EngToItalian/weights

!mkdir -p /content/drive/MyDrive/Models/GPT-Translation-EngToItalian/vocab

from config import get_config

cfg = get_config()

cfg['model_folder'] = '..//drive/MyDrive/ModelsGPT-Translation-EngToItalian/weights'

cfg['tokenizer_file'] = '..//drive/MyDrive/Models/GPT-Translation-EngToItalian/vocab/tokenizer_{0}.json'

cfg['batch_size'] = 24

cfg['num_epochs'] = 100

cfg['preload'] = None


from train import train_model

train_model(cfg)


# Local Training

pip install tokenizer

pip install datasets

pip install tokenizers

pip install torchmetrics

pip install google-colab


from config import get_config

cfg = get_config()

cfg['batch_size'] = 6

cfg['preload'] = None

cfg['num_epochs'] = 30

from train import train_model

train_model(cfg)
