# Guitar Tuning Classification 

## Synthetic Audio
An audio example from the dataset, which was generated by sending guitar tablature data to a sample-based guitar plugin, is available [here](https://drive.google.com/file/d/1sld2el13B0VeYA9sjzKLi_HCPG3Fka83/view?usp=sharing).

## Model Evaluation

The evaluation procedure described below has only been tested on a Linux system.

### Install Requirements
You will need at least Python 3.8. We recommend installing Python and the required packages in a virtual environment using *venv* or *conda*, and *pip*.   	

Install the following packages after setting up your environment:
```bash
pip install tensorflow matplotlib scikit-learn seaborn
```

Clone the repo and change directory:
```bash
git clone https://github.com/edhulme/guitar-tuning-classification.git 
cd guitar-tuning-classification 
```

### Download Models and Datasets 
The test sets and trained models used for evaluation of the 5-class chromagram system can be downloaded from [here](https://drive.google.com/drive/folders/1gJy7CD2cFPLNiXujibc15rrqROtXH1kT?usp=sharing). After the *test-sets* and *models* folders have been downloaded and unzipped, put both folders inside the *guitar-tuning-classification* directory. 

### Evaluate Model
Run model evaluation on synthetic data in your local environment:
```bash
python3 eval_synthetic_songs.py
``` 
 
Run model evaluation on authentic data in your local environment:
```bash
python3 eval_authentic_songs.py
```

## Model Training

The training procedure described below has only been tested on a Linux system.

*Perform all of the steps in the Model Evaluation section before training a model*. The training procedure provided here is a simplified version of the procedure used in the *Multiclass Study* (i.e., a 5-class CNN is trained on chromagram representations of synthetic guitar audio data). Once you have trained a model you can then test it using the code and synthetic/authentic guitar data provided in the Model Evaluation section. 

### Download the training data
The dataset used to train a 5-class chromagram model can be downloaded from [here](https://drive.google.com/drive/folders/1gJy7CD2cFPLNiXujibc15rrqROtXH1kT?usp=sharing). After the *train-sets* folder has been downloaded and unzipped, put the folder inside the *guitar-tuning-classification* directory.

### Train Model
Run model training on synthetic data in your local environment:
```bash
python3 train.py
```
Once training has ended, a *model.h5* file should appear in your *guitar-tuning-classification* repository.  

### Evaluate Your Trained Model
The model will be tested automatically on the *test-synthetic.json* data after model training, and the accuracy score will be printed. However, if you wish to conduct a more detailed evaluation of the model, this can be done with the *eval_synthetic_songs.py* and/or the *eval_authentic_songs.py* file(s); please note, to do this you will need to comment out the *model_num* variable line, and change the *model_path* variable so that it reflects the path and filename of the model you intend to evaluate.  
