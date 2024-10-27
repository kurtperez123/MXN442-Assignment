# MXN442-Assignment
Compares EfficientNetV2 with other CNNs and non-DL methods (taught in MXN442) on EMNIST-Letters dataset. 

EfficientNetV2 paper is referenced/can be found here:
Tan, Mingxing, and Quoc V. Le. "EfficientNetV2: Smaller Models and Faster Training." 2021. arXiv preprint arXiv:2104.00298. 
Available at :https://arxiv.org/abs/2104.00298

-----

Brief description and runtime of the codes (based on running on an A100):

**Exploration.ipynb:** Provides an EDA and visualises the datasets and models. Runtime: a few minutes

**Non_DL_Techniques:** Converts the tensor datasets into arrays and trains/tests an SVM and a Random Forest Classifier: Runtime: 1 hour (can be ran without using a GPU)

**TrainTest_EfficientNet_models:** Trains an EfficientNetV2-S and EfficientNet-B4 network for 10 epochs. Runtime: 2 hours (requires a CUDA GPU)

**Evaluate:** Can be used to evaluate the saved models on the training set. Runtime: 20 minutes. 

The files do not need to be ran in any particular order. They all have a different purpose.

-----
Folder structure: 

/Report/ contains my project report. 

/Models/ are where some of the models are saved. Note that you need to download the RF classifier and SVM classifier from Google Drive as Github has a 100mb file limit. 

/data/ is where the datasets used get saved. 

-----

Requirements: 

1. The datasets needs to be downloaded once into the "./data" folder. The codes should already do this. 

    e.g. You should see blocks like below at the start of every .ipynb file:
    
    dataset_train = datasets.EMNIST(root='./data', split='letters', train=True, download=True, transform=transforms.ToTensor())
    dataset_test = datasets.EMNIST(root='./data', split='letters', train=False, download=True, transform=transforms.ToTensor())

    I have not extracted the datasets as uploading it on Github is difficult but if you run any of these blocks, it should download the datasets (if not present already). 

3. The SVM and RandomForest models also need to be downloaded and saved into the "/Models" folder. They are above the 100mb limit that GitHub has. 

    https://drive.google.com/drive/folders/1AtxXnANCRgR6-5x4hOjaYNMOkqrlLanR?usp=sharing

    I have saved my models in the above link. You can download them and save it into the "/Models" folder. The Eval code rely on models being available in that folder. 

All codes in this repo have been ran using the Google Colab environment and so all the codes are jupyter notebooks (.ipynb). 
I have used an A100 in the Google Colab environment to train the CNNs. I would strongly recommend having access to a CUDA GPU. 


-----

----------------------------

