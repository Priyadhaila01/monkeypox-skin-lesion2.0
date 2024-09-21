Mpox Skin Lesion Dataset Version 2.0 (MSLD v2.0)
Expanded Mpox Skin Lesion Dataset: 6 Distinct Classes for Robust Classification Benchmarking
License

The global outbreak of the virus previously called 'Monkeypox', now referred to as mpox, has caused widespread concern over the past year and continued to be a major topic in public health news headlines. During the peak transmission period back in July 2022, the World Health Organization (WHO) declared it a Public Health Emergency of International Concern (PHEIC). To obstruct its expeditious pace, early diagnosis was a must at that time. In that scenario, computer-aided monkeypox identification from skin lesion images could be a beneficial measure.

Nevertheless, no such datasets were available initially. Realizing the significance of instant release of such a dataset, we then pineered the creation of the "Moneypox Skin Lesion Dataset (MSLD)" by collecting and processing 'monkeypox' and 'non-monkeypox' (measles, chickenpox)images from different means of web-scrapping i.e., from news portals, websites and publicly accessible case reports. Now that the cases have come under control, ensuring the clinical soundness of the data through expert verification and feedback incorporation is crucial for developing effective algorithms to tackle any future cases of monkeypox or diseases with similar skin lesions. Therefore, we introduce an updated version, "Mpox Skin Lesion Dataset Version 2.0 (MSLD v2.0)". Instead of placing the non-mpox cases in a single class, we have added definite class labels such as, chickenpox, measles, cowpox, hand-foot-mouth disease, and healthy.


Graphical representation of our intended working pipeline:

Working pipeline

Contents
This repository gives access to the Mpox Skin Lesion Dataset Version 2.0 (MSLD v2.0). The creation of this dataset is primarily focused on distinguishing the monkeypox cases from the similar non-monkeypox cases. Therefore, along with the 'Monkeypox' class, we included skin lesion images of 4 other disease classes (and the healthy class) because of their resemblance to the monkeypox rash and pustules in initial state. These classes can be put together in to perform binary classification or we can use them for performing differential diagnosis via multi-class classification.

The dataset itself is available for download at the Kaggle or the Google Drive.

Some sample images from the dataset:

Sample Images

Dataset Description
The dataset contains a total number of 755 images from 541 unique patients. The class distribution is presented as follows:

Class label	No. of Original Images	No. of Unique Patients
Mpox	284	143
Chickenpox	75	62
Measles	55	46
Cowpox	66	41
Hand, foot and mouth disease	161	144
Healthy	114	105
Total	755	54
There are 2 folders in the dataset.

Original Images: This folder includes a subfolder named "FOLDS" containing five folds (fold1-fold5) for 5-fold cross-validation with the original images. Each fold has separate folders for the test, train, and validation sets.

Augmented Images: To aid the classification task, several data augmentation methods such as rotation, translation, reflection, shear, hue, saturation, contrast and brightness jitter, noise, scaling etc. have been applied using MATLAB R2020a. Although this can be readily done using ImageGenerator/other image augmentors, to ensure reproducibility of the results, the augmented images are provided in this folder. It contains a subfolder called "FOLDS_AUG" with augmented images of the train sets from each fold in the "FOLDS" subfolder of the "Original Images".The augmentation process resulted in an approximate 14-fold increase in the number of images.

Naming Convention of the Images
Each image is assigned a name following the format of DiseaseCode_PatientNumber_ImageNumber. The corresponding disease codes assigned to each of the six disease classes are - Mpox -> MKP, Chickenpox -> CHP, Cowpox -> CWP, Measles -> MSL, Hand,foot and mouth disease -> HFMD, Healthy -> HEALTHY. Assignment of the keywords is illustrated in the provided image "Keywords.jpg". For instance, an image named "MKP_17_01" indicates that it belongs to the Mpox class and is the first image captured from a patient with the ID 17.

Data Organization
The dataset includes an Excel file named "datalog.xlsx" consisting of 5 sheets (Sheet1-5), with each sheet corresponding to a specific fold (fold1-5). Each sheet contains three columns: train, validation, and test. These columns contain the names of the images belonging to the respective train, validation, and test sets for a particular fold.

Provenance
Sources
In the acquisition of images for MSLD v2.0, the same technique as in the previous version was employed, utilizing web-scraping to gather skin lesion images belonging to the six classes. Automated web-scrappers have not been used for ensuring image quality and data label. The dataset was constructed by sourcing images from reputable and reliable online platforms, including trusted news portals, websites, and academic journals. Each image was meticulously recorded along with its respective source information to facilitate further verification and ensure proper attribution. Copyright considerations were duly addressed, adhering to appropriate protocols to safeguard intellectual property rights.

Collection Methodology
In MSLD v2.0, a two-fold verification process was implemented to ensure the quality and reliability of the acquired skin lesion images. The first step was verification via Reverse Image Search. This technique of verification via reverse image search is similar to the one employed in MSLD v1.0. This involved conducting a comprehensive reverse image search using tools such as Google's Reverse Image Search. By cross-referencing the sources of the images with reputable platforms such as journals and renowned websites, the authenticity and credibility of each image were examined. This rigorous verification process ensured that only images with verified and trustworthy sources were included in the dataset. The second step was Verification by a Professional Dermatologist. In MSLD v2.0, a professional dermatologist played a crucial role in the verification process. Each image was carefully scrutinized by the dermatologist to ensure its accuracy and reliability. Any images that were difficult to understand or had mislabeling were eliminated from the dataset.

Web-Application
Since we intend to build an end to end solution - starting with dataset creation and ending with a live web app, a prototype of the web-app has already been developed using the open-source python streamlit framework with a flask core and has been hosted in the streamlit provided server for better user experience. In the app, Skin Lesion Detector, users can get, not only a suggestion but also the accuracy of the suggestion.

The codes required to build and train the model, all the javascript, css and html files as well as the trained model will be made opem-source soon. The app's dynamic and future updates will incorporate the ability to store user data and use them to train the model realtime.

Sample Images

Citation
If this dataset helped your research, please cite the following papers:
Ahmed, M. T., Paul, J., Jahan, T., Ali, S. N., Sani, S. M. Sakeef, Noor, N., Asma, A. N., & Hasan, T. (2023). Monkeypox Skin Lesion Detection Using Deep Learning Models: A Preliminary Feasibility Study. arXiv preprint arXiv:xxxx.xxxxx.

@article{Ahmed2023,
title={A Study on Mpox Skin Lesion Detection Using State-of-the-art Deep Learning Models},
author={Ahmed, Md. Tazuddin and Paul, Joydip and Jahan, Tasnim and Ali, Shams Nafisa and Sani, S. M. Sakeef and Noor, Nawshaba and Asma, Anzirun Nahar and Hasan, Taufiq},
journal={arXiv preprint arXiv:xxxx.xxxxx},
year={2023}
}

Priya Dhaila,Sakshi Bhatt and Saumya garg (2024). A Web-based Mpox Skin Lesion Detection System Using State-of-the-art Deep Learning Models Considering Racial Diversity. Biomedical Signal Processing and Control, 98, 106742.

@article{Priya2024,
title={A Web-based Mpox Skin Lesion Detection System Using State-of-the-art Deep Learning Models Considering Racial Diversity},
author={Priya Dhaila,Sakshi Bhatt and Saumya garg},
journal={Biomedical Signal Processing and Control},
volume={98},
pages={106742},
year={2024},
publisher={Elsevier}
}
