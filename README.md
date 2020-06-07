## DeepCOVIDExplainer: Explainable COVID-19 Diagnosis from Chest X-rays
Supplementary materials for "DeepCOVIDExplainer: Explainable COVID-19 Diagnosis Based on Chest X-ray Images" submitted to IEEE International Conference on Data Science and Advanced Analytics (DSAA'2020) to be held virtually in Australia this year. We provide details of dataset, preprocessing, network architectures, and some additional results. Nevertheless, we'll provide trained models, preprocessed data, interactive Python notebooks, and a web application showing live demo. As planned, we keep this repo updated. 

### Datasets
We consider 2 different versions of the datasets: first, we used the COVIDx v1.0 dataset by Wang et al. used to train and evaluate the COVID-Net, comprised of a total of 13,975 CXR images across 13,870 patient cases (as of June 6, 2020). COVIDx is mainly based on RSNA Pneumonia Detection Challenge (Link: https://www.kaggle.com/c/rsna-pneumonia-detection-challenge), ActualMed COVID-19 Chest X-ray Dataset Initiative (Link: https://github.com/agchung/Figure1-COVID-chestxray-dataset), COVID-19 radiography database (Link: https://www.kaggle.com/tawsifurrahman/covid19-radiography-database), giving 219 COVID-19 positive images, 1,341 normal images, and 1,345 viral pneuomonia images. This gives 358 CXR images from 266 COVID-19 patient cases and total of 8,066 patient cases who have no pneumonia (i.e., normal) and 5,538 patient cases who have non-COVID19 pneumonia. 

The updated dataset, which we refer to COVIDx v2.0 is categorized as normal (i.e., no-findings), pneumonia, and COVID-19 viral are enriched with CXR images of adult subjects of COVID-19, pneumonia, and normal examples, leaving 15,959 CXR images across 15,854 patients: 

    1. COVID chest X-ray-dataset: by Joseph P.C. et al, Link: https://github.com/ieee8023/covid-chestxray-dataset, contains 660 PA (i.e., frontal view) CXR images. 
    2. COVID-19 patients lungs X-ray images (Link: https://www.kaggle.com/nabeelsajid917/covid-19-x-ray-10000-image), contains 70 COVID-19 and 70 normal CXR images. 
    3. Chest X-ray images by Ozturk et al. (Link: https://github.com/muhammedtalo/COVID-19), contains 125 COVID-19, 500 normal, and 500 pneumonia CXR images. 
    
### Methods
The pipeline of "DeepCOVIDExplainer" consist of preprocessing, classification, snapshot neural ensemble, and decision visualizations.
After necessary preprocessing of CXR images, DenseNet, ResNets, and VGGNets are trained in a transfer learning setting, creating their model snapshots, followed by neural snapshot ensemble based on averaging Softmax class posterior and the prediction maximization of best performing models. Finally, class-discriminating attention maps are generated using gradient-guided class activation maps (Grad-CAM++) and layer-wise relevance propagation (LRP) to provide explanations of the predictions and to identify the critical regions on patients chest.  

### Data availability
We will open source the preprocessed data in npy file format to ease the community to build the model with ease. However, it'll take a few more days. 

### Availability of pretrained models
We plan to make public all the pretrained models and some computational resources available, but it will take time. For the time being, we made only VGG-19 and ResNet-18 upon reasonable request. 

### A quick instructions
A quick example on a small dataset will be shown in next few days.  

### Citation request
If you use the code of this repository in your research, please consider citing the folowing papers:

    @inproceedings{DeepCOVIDExplainer,
        title={DeepCOVIDExplainer: Explainable COVID-19 Diagnosis based on Chest X-ray Images},
        author={Anonymized for review},
        conference={IEEE International Conference on Data Science and Advanced Analytics (DSAA'2020)},
        publisher={Under review},
        year={2020}
    }

### Contributing
In future, we'll provide an email address, in case readers have any questions. 
