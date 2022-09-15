# Expert-level detection of pathologies from unannotated chest X-ray images via self-supervised learning

<details>
<summary>
  <b>Expert-level detection of pathologies from unannotated chest X-ray images via self-supervised learning</b>, Nat. Biomed. Eng (2022). 
  <a href="https://www.nature.com/articles/s41551-022-00936-9" target="blank">[Paper]</a>
	<br><em><a href="https://www.linkedin.com/in/ekin-tiu-0aa467200/">Ekin Tiu</a>, <a href="https://www.linkedin.com/in/ellie-talius/">Ellie Talius</a>, <a href="https://www.linkedin.com/in/pujanpatel24/">Pujan Patel</a>, <a href="https://med.stanford.edu/profiles/curtis-langlotz">Curtis P. Langlotz</a>, <a href="https://www.andrewng.org/">Andrew Y. Ng</a>, <a href="https://pranavrajpurkar.squarespace.com/">Pranav Rajpurkar</a></em></br>
</summary>

```bash
Tiu, E., Talius, E., Patel, P. et al. Expert-level detection of pathologies from unannotated chest X-ray images via self-supervised learning. Nat. Biomed. Eng (2022). https://doi.org/10.1038/s41551-022-00936-9
```
</details>

<img width="848" alt="Screen Shot 2022-09-15 at 10 57 16 AM" src="https://user-images.githubusercontent.com/12751529/190451160-a919b363-6005-4cd4-9633-b194392bd728.png">

This repository contains code to train a self-supervised learning model on chest X-ray images that lack explicit annotations and evalute this model's performance on pathology-classification tasks.

## Dependencies
To clone all files:

```git clone https://github.com/rajpurkarlab/CheXzero.git```

To install Python dependencies:

```pip install -r requirements.txt```

## Data 
### Training Dataset
1. Navigate to [MIMIC-CXR Database](https://physionet.org/content/mimic-cxr/2.0.0/) to download the training dataset. 
2. Copy the dataset into the `data/` directory.
3. Run `python preprocess_train_data.py`
4. This should preprocess the chest x-ray images into a hdf5 format used for training stored at `data/cxr.h5` and extract the impressions section as text from the corresponding chest x-ray radiology report stored at `data/mimic_impressions.csv` .

### Model Checkpoints
Model checkpoints of CheXzero pre-trained on MIMIC-CXR are publicly available at the following [link](https://drive.google.com/drive/folders/19YH2EALQTbkKXdJmKm3iaK8yPi9s1xc-?usp=sharing). Download files and save them in the `./models/` directory.

## Running Training
Run the following command to perform CheXzero pretraining. 
```bash
python run_train.py
```

### Arguments
* `--cxr_filepath` Directory to load chest x-ray image data from.
* `--txt_filepath` Directory to load radiology report impressions text from.

Use `-h` flag to see all optional arguments. 


