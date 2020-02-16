# Overall survival prediction of non-small cell lung cancer by integrating microarray and clinical data with deep learning
This repository provides a reference implementation of *Bimodal DNN* as described in the paper submitted to *Scientific Reports*: *Overall survival prediction of non-small cell lung cancer by integrating microarray and clinical data with deep learning*.

Non-small cell lung cancer (NSCLC) is one of the most common lung cancers worldwide. Accurate prognostic stratification of NSCLC can become an important clinical reference when designing therapeutic strategies for cancer patients. With this clinical application in mind, we developed a deep neural network (DNN) combining heterogeneous data sources of gene expression and clinical data to accurately predict the overall survival of NSCLC patients. Based on microarray data from a cohort set (614 patients), seven well-known NSCLC biomarkers were used to group patients into biomarker- and biomarker+ subgroups. Then, by using a systems biology approach, prognosis relevance values (PRV) were then calculated to select eight additional novel prognostic gene biomarkers. Finally, the combined 15 biomarkers along with clinical data were then used to develop an integrative DNN via bimodal learning to predict the 5-year survival status of NSCLC patients with tremendously high accuracy (AUC: 0.8163, accuracy: 75.44%). Using the capability of deep learning, we believe that our prediction can be a promising index that helps oncologists and physicians develop personalized therapy and build the foundation of precision medicine in the future.


## Examples

<div align="center">
  <img width="600px" height="auto" src="images/architecture.png">
</div>
</br>
---


## ccc
<div align="center">
  <img width="600px" height="auto" src="images/biomarkers.png">
</div>


## Basic Usage

### Data availability
The combined GSE cohort is available [here](https://drive.google.com/file/d/1dnqQEahODuZpFPiIaZO86ucFRcGuFgAA/view?usp=sharing). The data were first pre-processed and split into train/test splits.

### Examples
You can train the microarray/clinical subnetworks with the following lines. Trained model and its details are saved in */models*.
```python
python3 pretrain_x.py
python3 pretrain_c.py
```
After pre-training, the merged *Bimodal DNN* can be trained with
```python
python3 merge.py
```
### Results
<div>
  <figure>
  <img width="300px" height="auto" src="results/error_x.png">
  <figcaption>Fig.1 - Trulli, Puglia, Italy.</figcaption>
  </figure>
</div>
<div>
  <img width="300px" height="auto" src="results/error_c.png">
</div>
<div>
  <img width="300px" height="auto" src="results/error_merge.png">
</div>



