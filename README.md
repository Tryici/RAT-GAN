## RAT-GAN usage demo:

### take training the flower dataset as an example

<font color="red">（You can copy the following code to run it directly）</font>

```
conda create -n RAT-GAN -y python=3.8 &&
conda activate RAT-GAN &&
conda install -y pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch &&
pip install pandas easydict nltk scikit-image pyyaml &&
git clone https://github.com/Tryici/RAT-GAN.git &&
cd RAT-GAN/code/  &&
wget -c https://github.com/Tryici/RAT-GAN/releases/download/flower/flower.zip -P ../data/ &&
wget -c https://github.com/Tryici/RAT-GAN/releases/download/text_encoder250/text_encoder250.pth -P  ../bird/ &&
unzip ../data/flower.zip -d ../data/ &&
python main.py --cfg cfg/flower.yml
```

## Step by step tutorial：

1. Create a running environment using `conda`, the environment name is set to`RAT-GAN`, and the python version is set to 3.8.

   ```
   conda create -n RAT-GAN -y python=3.8
   ```

2. Activate the created environment and install packages required for running.

   ```
   conda activate RAT-GAN &&
   conda install -y pytorch==1.11.0 torchvision==0.12.0 torchaudio==0.11.0 cudatoolkit=11.3 -c pytorch &&
   pip install pandas easydict nltk scikit-image pyyaml
   ```

3. Clone project from GitHub to the local.

   ```
   git clone https://github.com/Tryici/RAT-GAN.git
   ```

4. Enter the project directory `RAT-GAN/code/`, download the dataset `flower.zip` to the directory `../data/`, and download the pretraining text encoder file `text_encoder250.pth` to directory `../bird/` respectively.

   ```
   cd RAT-GAN/code/  &&
   wget -c https://github.com/Tryici/RAT-GAN/releases/download/flower/flower.zip -P ../data/ &&
   wget -c https://github.com/Tryici/RAT-GAN/releases/download/text_encoder250/text_encoder250.pth -P  ../bird/
   ```

4. Unzip the dataset package ` flower.zip` to the directory `../data/`.

   ```
   unzip ../data/flower.zip -d ../data/
   ```

5. After the above operation, configurations of environment and data are completed. Then you can start training the model. `cfg/flower.yml` is a file that stores model parameters.

   ```
   python main.py --cfg cfg/flower.yml
   ```

