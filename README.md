# Practicals FishGroup

This repository contains code and tutorials of the [i-Bio](http://ibio.sorbonne-universite.fr/) summer school on **"Advanced Computational Analysis for Behavioral and Neurophysiological Recordings"**, which took place in Banyuls-sur-Mer, August 6-12 2023. During that summer school, practicals were organized into two groups that worked on different datasets.  
The present repository corresponds to the group that worked on whole-brain LightSheet recordings of *Danionella cerebrum* larvae during visual stimulation evoking OptoMotor response, and Zebrafish (*Danio rerio*) larvae freely swiming behavioral tracking.

This repository is an archive of [EmeEmu/IBIO-Banyuls2023-Python](https://github.com/EmeEmu/IBIO-Banyuls2023-Python).

## Tutorials
This repo contains 4 tutorials in 4 notebooks :
- [day1](/day1_processing_and_visualizing_data.ipynb) : an introduction to Python, the data, and how to visualize the data.
- [day2](/day2_regression_and_decoding.ipynb) : linear and multi-linear regression between neuron activity and behavior/stimuli, and decoding of brain activity.
- [day3](/day3_dim_reduction_and_clustering.ipynb) : k-means clustering, hierarchicak clustering, and PCA of brain activity.
- [day4](/day4_HMMs.ipynb) : Markov Chain, Gaussian Mixture Models, and Hidden Markov Models of freely swimming zebrafish larvae.

Those notebooks are mostly complete, but contains empty cells which must be filled.  
The corrections can be found in the [correction folder](/corrections).


## Working with Google Colab

This section explains how to open the tutorials from this repo into Google Colab, as well as some helpfull bit of code to updload the data, functions, and librairies.

### Opening Colab

Got to [Colab's website](https://colab.research.google.com/), and in the popup window click on **Github**, then in the seach bar paste the following :
```
https://github.com/EmeEmu/IBIO-Banyuls2023-Python
```
You can then select the notebook you want to open, for example `day1_discovering_the_data.ipynb`.

### Downloding the Helper files

In this repo, you will find a buch of helper functions in the sub-directory `Helper_Functions`. To load them into Colab run the following code in a cell :
```
!mkdir /content/Helper_Functions/
!wget -P /content/Helper_Functions/ https://raw.githubusercontent.com/i-Bio-Summer-School-2023/Practicals-fishgroup/main/Helper_Functions/accessing_data.py
!wget -P /content/Helper_Functions/ https://raw.githubusercontent.com/i-Bio-Summer-School-2023/Practicals-fishgroup/main/Helper_Functions/hmm_plotters.py
!wget -P /content/Helper_Functions/ https://raw.githubusercontent.com/i-Bio-Summer-School-2023/Practicals-fishgroup/main/Helper_Functions/OrthoViewer.py
!wget -P /content/Helper_Functions/ https://raw.githubusercontent.com/i-Bio-Summer-School-2023/Practicals-fishgroup/main/Helper_Functions/dimred_helper.py
!wget -P /content/Helper_Functions/ https://raw.githubusercontent.com/i-Bio-Summer-School-2023/Practicals-fishgroup/main/Helper_Functions/plotting_functions.py
```

### Downloading Data

All the data for this Python workshop is located in the following [Google Drive](https://drive.google.com/drive/folders/1k21VhLoonOnoxxXyswrmE45VIB4FF00n?usp=sharing "Link to the Google Drive"). To work on this data from Colab, it needs to be downloaded to Colab's cloud storage.

Within Colab, you can download the entire folder by running the folling code :
```
!gdown --folder 1k21VhLoonOnoxxXyswrmE45VIB4FF00n
```
this will download all the files from the Google Drive to `/content/banyuls_data/`.

You can also download indivual files by providing the unique identifier in the url of the file in the following code. For example, for the file [https://drive.google.com/file/d/1jIQw8EEIoS516plFFXtRIwS-0oey7kFt/view?usp=sharing](https://drive.google.com/file/d/1jIQw8EEIoS516plFFXtRIwS-0oey7kFt/view?usp=sharing), the identifier is `1jIQw8EEIoS516plFFXtRIwS-0oey7kFt` :

```
!gdown 1jIQw8EEIoS516plFFXtRIwS-0oey7kFt
```
and the file will be downloaded as `/content/fish1_different_directions.hdf5`

### Setting up Matplotlib for interactive plots

Working with interactive plots in Colab requires a little bit of preparation. You should run the following code :
```python
!pip install ipympl
from google.colab import output
output.enable_custom_widget_manager()
%matplotlib widget
```


## Working locally

### Setting up the environnement

```bash
conda create --file ibio_env.txt --name ibio
```

## Code Liscence
The code and tutorials were developed by [Mattéo Dommanget-Kott](https://github.com/EmeEmu) and [Leonardo Demarchi](https://github.com/leonardo-demarchi). Everything in this repository is liscenced under the [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html).