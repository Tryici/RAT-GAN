## 以训练flower数据集为例

## （复制以下代码可以直接运行）：

```
conda create -n RAT-GAN3 -y python=3.8 &&
conda activate RAT-GAN3 &&
conda install -y pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch &&
pip install pandas easydict nltk scikit-image pyyaml &&
git clone https://github.com/Tryici/RAT-GAN.git &&
cd RAT-GAN/code/  &&
wget -c https://github.com/Tryici/RAT-GAN/releases/download/flower/flower.zip -P ../data/ &&
wget -c https://github.com/Tryici/RAT-GAN/releases/download/text_encoder250/text_encoder250.pth -P  ../bird/ &&
unzip ../data/flower.zip -d ../data/ &&
python main.py --cfg cfg/flower.yml
```

## 分步骤教程：

1. 创建环境，使用conda创建运行环境，环境名为`RAT-GAN`，python版本设置为3.8

   ```
   conda create -n RAT-GAN -y python=3.8
   ```

2. 激活创建的环境，并安装运行需要的包

   ```
   conda activate RAT-GAN &&
   conda install -y pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch &&
   pip install pandas easydict nltk scikit-image pyyaml
   ```

3. 从github上clone项目到本地

   ```
   git clone https://github.com/Tryici/RAT-GAN.git
   ```

4. 进入到项目目录`RAT-GAN/code/`中，分别下载数据集`flower.zip`到目录`../data/`，下载预训练文本编码器文件`text_encoder250.pth`到目录`../bird/`中

   ```
   cd RAT-GAN/code/  &&
   wget -c https://github.com/Tryici/RAT-GAN/releases/download/flower/flower.zip -P ../data/ &&
   wget -c https://github.com/Tryici/RAT-GAN/releases/download/text_encoder250/text_encoder250.pth -P  ../bird/
   ```

5. 解压数据集压缩包`flower.zip`到目录`../data/`中

   ```
   unzip ../data/flower.zip -d ../data/
   ```

6. 运行环境和数据配置完成，开始训练模型，flower.yml 文件为存储了模型参数的文件

   ```
   python main.py --cfg cfg/flower.yml
   ```

