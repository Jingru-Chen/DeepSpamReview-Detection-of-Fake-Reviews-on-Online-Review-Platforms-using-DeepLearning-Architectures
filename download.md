
## Download the dataset

### 选项1. Kaggle网站下载

[glove-global-vectors-for-word-representation](https://www.kaggle.com/datasets/rtatman/glove-global-vectors-for-word-representation)

[deceptive-opinion-spam-corpus](https://www.kaggle.com/datasets/rtatman/deceptive-opinion-spam-corpus)

[googles-trained-word2vec-model-in-python](https://www.kaggle.com/datasets/umbertogriffo/googles-trained-word2vec-model-in-python)

[Yelp Review Polarity CSV](https://s3.amazonaws.com/fast-ai-nlp/yelp_review_polarity_csv.tgz)

下载并解压到.\input文件夹下，解压后的文件树如下:

```
./input
├─deceptive-opinion-spam-corpus
│      deceptive-opinion.csv
│
├─glove-global-vectors-for-word-representation
│      glove.6B.100d.txt
│      glove.6B.200d.txt
│      glove.6B.50d.txt
│
├─googles-trained-word2vec-model-in-python
│      GoogleNews-vectors-negative300.bin
│      GoogleNews-vectors-negative300.bin.gz
│
└─yelp_review_polarity_csv
        readme.txt
        test.csv
        train.csv
```


### 选项2：通过命令行下载
如果系统已配置好 Kaggle 命令行工具，可以直接使用以下命令下载并解压所需的数据。

首先，下载 [Yelp Review Polarity CSV](https://s3.amazonaws.com/fast-ai-nlp/yelp_review_polarity_csv.tgz)，并按照上述的文件结构组织文件。

#### Windows
```cmd
# 确保您位于项目主目录下，例如 \path\to\DeepSpamReview-Detection

# 从 Kaggle 下载相应的数据
kaggle datasets download -d rtatman/deceptive-opinion-spam-corpus -p .\input
kaggle datasets download -d rtatman/glove-global-vectors-for-word-representation -p .\input
kaggle datasets download -d umbertogriffo/googles-trained-word2vec-model-in-python -p .\input

# 创建文件夹
mkdir .\input
mkdir .\input\deceptive-opinion-spam-corpus
mkdir .\input\glove-global-vectors-for-word-representation
mkdir .\input\googles-trained-word2vec-model-in-python

# 解压 ZIP 文件
tar -xf .\input\deceptive-opinion-spam-corpus.zip -C .\input\deceptive-opinion-spam-corpus
tar -xf .\input\glove-global-vectors-for-word-representation.zip -C .\input\glove-global-vectors-for-word-representation
tar -xf .\input\googles-trained-word2vec-model-in-python.zip -C .\input\googles-trained-word2vec-model-in-python
```

#### MacOS
```bash
# 确保您位于项目主目录下，例如 /path/to/DeepSpamReview-Detection

# 从 Kaggle 下载相应的数据
kaggle datasets download -d rtatman/deceptive-opinion-spam-corpus -p ./input
kaggle datasets download -d rtatman/glove-global-vectors-for-word-representation -p ./input
kaggle datasets download -d umbertogriffo/googles-trained-word2vec-model-in-python -p ./input

# 创建文件夹
mkdir -p ./input
mkdir -p ./input/deceptive-opinion-spam-corpus
mkdir -p ./input/glove-global-vectors-for-word-representation
mkdir -p ./input/googles-trained-word2vec-model-in-python

# 解压 ZIP 文件
unzip ./input/deceptive-opinion-spam-corpus.zip -d ./input/deceptive-opinion-spam-corpus
unzip ./input/glove-global-vectors-for-word-representation.zip -d ./input/glove-global-vectors-for-word-representation
unzip ./input/googles-trained-word2vec-model-in-python.zip -d ./input/googles-trained-word2vec-model-in-python
```

## 配置运行环境
1. 创建 Python 3.8 的 Conda 环境
```bash
conda create -n deep_spam_review python=3.8
conda activate deep_spam_review
```
2. 安装依赖库
```bash
pip install -r requirements.txt
```
3. 运行`test/attention_biLstm_glove.ipynb`