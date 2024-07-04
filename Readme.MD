## **Associated Notebooks**

The associated notebooks for this project are located within the main repository: https://github.com/andrespineda/UC_Berkeley_MLAI_Capstone


* **Data Prep Notebook:** WESAD_Data_Preprocessing.ipynb

* **Data Analysis and Modeling:** HRV_Stress_Detection.ipynb


## Table of Contents
* [Introduction](#Introduction)
* [Methodology](#Methodology)
* [Understanding the Business](#Understanding-the-Business)
* [Understanding the Data](#Understanding-the-Data)
* [Data Preparation](#Data-Preparation)
* [Modeling](#Modeling)
* [Evaluation](#Evaluation)
* [References](#References)


# **Introduction**

This project was developed as the Capstone Project to the UC Berkeley Professional Certificate in Machine Learning and Artificial Intelligence Program. The program provides practical insights into the business applications of ML and AI technologies(UC Berkeley Executive Education., n.d.)
## **Methodology**

The Data Analysis will use the Cross Industry Standard Process for Data Mining (CRISP-DM) method
(Schröer, et al, 2021) of data analysis.
<img src="https://drive.google.com/uc?export=view&id=1Yp9cIXrpcM5DzDSvAsFOSyjmx9HEc-h4" width="200" align="right">
**CRISP-DM**

The CRISP-DM (Cross-Industry Standard Process for Data Mining) approach
to data analysis involves six major steps as outlined below:

1. **Understanding the Business:** This initial step involves conducting an
    in-depth analysis of the business objectives and needs. It includes
    assessing the current situation, defining goals based on insights, and
    setting up a plan to proceed.

2. **Understanding the Data:** In this phase, data is collected from various
    sources, its format and type are determined, and the data is profiled.
    Tasks include exploring the data, describing it, and ensuring its
    quality, accuracy, and validity.

3. **Data Preparation:** Careful selection, cleansing, construction, and formatting of the data are carried out in this step. The data are organized for modeling, and information exploration is conducted to
identify patterns aligned with business insights.

4. **Modeling:** The modeling phase involves selecting modeling techniques,
    generating test scenarios for validation, building various models, and
    assessing them to ensure alignment with business objectives

5. **Evaluation:** During this phase, the results of the models are evaluated
    against business intentions. Multiple models are assessed to determine
    which one best meets the project's goals.

6. **Deployment/Communication:** The final step involves presenting the
    gathered information in a usable manner to stakeholders according to
    their expectations and business requirements. This phase may vary in
    complexity based on numerous factors.

  # **1. Understanding the Business**

## **Background**


Research shows that stress is a major issue for<img src="https://drive.google.com/uc?export=view&id=1lhWuOVyyRi0MuDxuDNNO4S6o6ny7XZ8s" width="200" align="right"> young adults. A 2022 survey found that young adults aged 18–24 reported 5.8 out of 10 stress-related symptoms, compared to a 3.8 score of those aged 65 and older. Stress is also linked to many health issues, including heart disease, cancer, lung ailments, accidents, cirrhosis of the liver, and suicide (Statista, 2023).

Some indications of the ill effects of stress can be visually identified without special equipment, but sustained long term stress may cause internal issues
that are not easily detected. The common method <img src="https://drive.google.com/uc?export=view&id=1j8YOQrziHwoCIfbzYkQ2XteYd3isumgK" width="80" align="right">of measuring underlying stress conditions requires a trip to a medical facility where expensive medical equipment is used by trained clinicians.

If there was a way that a person could accurately and inexpensively measure their stress levels without going to a clinic, they could use that information as feedback so that they could learn to monitor and control their stress levels on their own.
## **Capstone Research Question**

Can commonly available wearable devices be used to accurately self-monitor stress levels?

## **Business Objective**

The business objective is to develop a machine learning classification model that is capable of determining whether heart rate samples collected from a wearable device can accurately detect stress patterns.
<img src="https://drive.google.com/uc?export=view&id=1zFLLzvzUrRhbGLWCeul-OlYxkslJKq-0" width="100" align="right">
 The heart beat cadence, the time interval between beats, has been proven to be a reliable indicator of stress.  Counterintuitively, a predictive pattern of regular time intervals is indicative of a stress situation. A non stressful measurement will include a variation in the pattern of beats. HRV, or Heart Rate Variability, is a medical term for the measurement of the variation in time between each heartbeat.

Collected HRV data will be used to train a classification model. By <img src="https://drive.google.com/uc?export=view&id=1W2hHDY8_hInFz-_-raeMBFiXqphtDkjA" width="100" align="right">training a classification model  we will be able to take measurements of HRV and determine whether someone is stressed or not. We will use labeled datasets that have been captured during stressful conditions for training.  The labeled data will be used to teach the model to recognize patterns that differentiate between the two conditions. Once trained, the model will be able to classify new input files of HRV data with accuracy, allowing us to better understand the relationship between HRV and stress.

## **Why is this important?**

<img src="https://drive.google.com/uc?export=view&id=1xofI99rMfYiWtCE8PSsJXvzjCfgqjZn3" width="100" align="right">
The use of an inexpensive wearable device to capture, classify, and present a visual indicator of a person's stress level can help reduce a serious problem faced by young adults. This tool would allow a person to self-monitor and control their stress levels without the need for expensive clinical equipment or visits to a medical facility.

## **How can this be achieved?**

Heart Rate Variability (HRV) is a powerful physiological indicator<img src="https://drive.google.com/uc?export=view&id=1jeUsZPxOzvNFpd7VMAK3xyGm88wX7rEy" width="200" align="right"> that provides valuable insights into the functioning of the autonomic nervous system, particularly the parasympathetic branch (Cleveland Clinic, 2021). HRV measures the variation in time between successive heartbeats, reflecting the body's ability to adapt to changing circumstances and stress levels.


The parasympathetic nervous system, often referred to as the "rest and digest" system, plays a crucial role in maintaining balance and promoting relaxation in the body. When stress levels increase, the parasympathetic system's activity typically decreases, leading to a reduction in HRV.

Monitoring HRV can provide important clues about an individual's stress levels and overall well-being:

1. Stress detection: Lower HRV often indicates higher stress levels and reduced parasympathetic activity.<img src="https://drive.google.com/uc?export=view&id=1MsSCxt7vQmbkMZQxNFHIShIcDXqqDERH" width="400" align="right"> 

2. Recovery assessment: HRV can help evaluate how well the body recovers from physical or mental stressors.

3. Health indicator: Chronically low HRV may signal increased risk for various health issues, including cardiovascular problems and mental health disorders.

4. Biofeedback tool: HRV measurements can be used to help individuals learn to manage stress more effectively through techniques like deep breathing and meditation (Biofeedback-Neurofeedback-Therapy.com, n.d.).

By tracking HRV over time, individuals can gain valuable insights into stress levels and parasympathetic nervous system function. This information can be used to implement targeted interventions and lifestyle changes to improve overall health and well-being.

## **Business Expected Results**

It is expected that a classification model can be <img src="https://drive.google.com/uc?export=view&id=17T01ru8CDzj_pRrUQp9KhFqX8jnUFrzF" width="100" align="right">developed that can accurately classify stress level categories using a sampling of HRV data. Ideally, a short sampling period of one to three minutes will be sufficient for the model to classify the stress level during the sampling period.

With the proliferation of wearble technology, such as a wrist or arm-band heart rate monitor, an Apple watch, or even a smartphone with a camera, there are new opportunities to capture HRV data. The captured data can be used by the trained classification model to assess the stress level of <img src="https://drive.google.com/uc?export=view&id=1sFKYDVTvq4tzEb3t3hqCwSWAKGXZLmwN" width="50" align="right">the person immediately after the data was captured. The results of the classification model need to be presented to the user via a easy to i-understand visual stress indicator on their smartphone. For example, a circular gauge that goes from blue for low stress to red to indicate high stress. Other similar user interfaces will be considered for ease of use and  effectiveness.


## **Business Success Criteria**

The success criteria will be based on meeting the following measurable results:

1. A classification model will developed that can take as input a one to three minute recording of a person's heart rate.
2. Based on the data provided, the classification model will be able to classify the readings into stressful and non-stressful periods of time according to the following metrics:

3. A Recall score (Sensitivity or True Positive rate) of 85%. It is important for the model to correctly identify True Positives. Being able to correctly identify stress from the reading is important so the person can take corrective action. In this problem, a high recall value is preferable than a high accuracy score.

4. The classification model will be able to classify the data within 15 seconds. The model will eventually operate within a smartphone and it wil be important for the user to be able to get a stress reading with a short time after taking a heart rate sample.

# **2. Understanding the Data**
## ****Data Sources****
Developing an accurate machine learning model requires training data of heart rate signals during various target conditions, such as subjects that were relaxed or under stressful circumstances.

An ideal data source was identified:


**WESAD**

WESAD (Wearable Stress and Affect Detection) contains data of 15 subjects during a stress-affect lab study, while wearing physiological and motion sensors. WESAD is a publicly available dataset for wearable stress and affect detection. This multimodal dataset features physiological and motion data, recorded from both a wrist- and a chest-worn device, of 15 subjects during a lab study. The following sensor modalities are included: blood volume pulse, electrocardiogram, electrodermal activity, electromyogram, respiration, body temperature, and three-axis acceleration. Moreover, the dataset bridges the gap between previous lab studies on stress and emotions, by containing three different affective states (neutral, stress, amusement). In addition, self-reports of the subjects, which were obtained using several established questionnaires, are contained in the dataset.(Schmidt, et.al., 2018)

 The original paper and links to download the dataset can be found via this link: https://archive.ics.uci.edu/dataset/465/wesad+wearable+stress+and+affect+detection


## ****Data Content****


 The WESAD dataset include Electrocardiogram (ECG) measures of various subjects during hours of stressing, amusing, relaxing, and neutral situations. Below is a table listing the ECG data field acronyms with their definitions, although a smaller subset will used:

<img src="https://drive.google.com/uc?export=view&id=141L2sk49Ijk0Tp8tlpLBZcXPi6EAlPFW" width="400">

## ****Data Sample****

The selected data for this project consists of **2.1M rows** of ECG and related data elements.

The data is labeled in three categories: Baseline (no stress), Stress, an Amusement or Happy as depicetd by the following pie cart:

<img src="https://drive.google.com/uc?export=view&id=1-bJA4DtNO3UYlw6q7LrywquHg5aiiqKQ" width="200">


Below is a sample of the ECG signal from this data:

<img src="https://drive.google.com/uc?export=view&id=1b099kPnzgVwOsjYIITwKOK91UfO2YK0U" width="300">


## ****Data Prep****

Data preparation is a key step in the data analysis process, laying the foundation for accurate and meaningful insights. This phase involves several key tasks to ensure the data is clean, consistent, and ready for analysis. Initially, data must be collected from the WESAD datasetand consolidated into a unified format. Raw data often contains errors, missing values, and inconsistencies that need to be addressed through data cleaning techniques such as removing duplicates, handling missing values, and correcting formatting issues. Data transformation may be necessary to convert variables into appropriate formats or to create derived features that enhance the analysis. Normalization and standardization techniques are often applied to ensure comparability across different scales.  Finally, data reduction techniques like feature selection or dimensionality reduction may be employed to focus on the most relevant variables and improve computational efficiency. This comprehensive data preparation process is vital for producing reliable and actionable insights in subsequent analysis stages.

Below is the process that will be used in this project:


<img src="https://drive.google.com/uc?export=view&id=1o5_aqAuQWl_M5e7BRnIiHL_1m2vwR63x" width="900" >


## **Heart Rate Variability**

From this inital analysis of the data, we must isolate the heart beats. Our goal is to detrend the ECG time series data and then apply stationary algorythms to isolate the individual wave forms.

### **Identify the Peaks**

Identifying the peaks is critical to calulating the inter-beat interval. It must be calculated with accuracy as the variation between the beats is used to determine the HRV values.

Below is a sample plot showing the identification of the peaks.


<img src="https://drive.google.com/uc?export=view&id=11LCMYb-TeIgD1Nn0l6MDdrHRMJcFG9wJ" >


Now that the peaks are identified and the heart beat wave is stationary, we can calculate the distribution of RR Intervals. The RR Intervals are the distance between the peaks.

Below is a plot of the distribution of RR intervals in the dataset.  We must eliminate the outliers and then use the distribution to begin classification based on the labeled dataset.

<img src="https://drive.google.com/uc?export=view&id=1SBdilIaPJvgaIPsAkfyhG8jhMVXoY_Sr"  width= "200">

Another useful plotting method is to use a Poincaré Plot. This plot compares each RR interval with the previous and plots the result as a 2 dimensional plot.

<img src="https://drive.google.com/uc?export=view&id=1A-ZgRLHq0WyrSEjNqdetCvF0NFXbgGL_" width= "200" >

# **4. Modeling**

Modeling consists of several steps: splitting the data into training and test sets, selecting the models to be tested, choosing the hyperparameters, and executing a grid search pipeline. After the pipeline completes, the scores of the modeles are evaluated and a final model/configuration is selected.
<img src="https://drive.google.com/uc?export=view&id=1pEGYkeeU1Km40oB6aKgYwNqIGOlrnrMF" width="800" >

For this project the pipeline will include the following model classifiers:

* Logistic Regression as a baseline
* K-Nearest Neighbor (KNN)
* Random Forest
* Support Vector Decomposition (SVD)

The following parameters will be used for the training and evaluation"
<img src="https://drive.google.com/uc?export=view&id=15ouWML1Xo6RuAdf6INY0DnYB1v6tvglp" width="200" >

# **5. Evaluation**

** In Progress**

### **Evaluate Model Results**

** In Progress**

### **Model Results vs Business Criteria**



### **Next Steps**

We could continue to experiment with the hyperparameters to get a better result. At some point, you reach a score that meets your needs without further refinement. Factors such as time or computing resource constraints may dictate how much effort is expended to achieve a near perfecet model.
<p></p>
Another major decision is whether the model is ready for productional use. In this case we will ue the trained model to determione if it can directly classify a person's stress level from a minute's worth of data taken from a wearble device. 

# **6. Deployment**
In the deployment stage, the model is put into operational use. In this case, the model will be used to process data collected from a mobile app that is under development. The app will use Photoplethysmography (PPG)to capture heart rate data from a person's finger. Photoplethysmography (PPG) can be effectively utilized with a smartphone camera to measure heart rate, offering a convenient and accessible method for health monitoring. The process works by detecting subtle color changes in the skin that occur with each heartbeat.

After data capture, the recording will be sent from the app to a host for processing. The model that was developein this project will read the data from the host and use the trained model to determine the state of stress.

In future releases the model will be encoded dircty into the smartphone and the PPG data can be used to display an indicator of the level of stress.

Below are images of the app that has been developed for this purpose.

<img src="https://drive.google.com/uc?export=view&id=1IBDnHMRPgRDuc7QwmsfKKAyLXkv7_Npr" width="800" >




# **References**

* Biofeedback-Neurofeedback-Therapy.com. (n.d.). HRV biofeedback in the treatment of various disorders.  https://biofeedback-neurofeedback-therapy.com/hrv-biofeedback/

* Cleveland Clinic. (2021, September 1). Heart rate variability (HRV): What it is and how you can track it. https://my.clevelandclinic.org/health/symptoms/21773-heart-rate-variability-hrv


* Koldijk, S., Sappelli, M., Verberne, S., Neerincx, M.A., & Kraaij, W. (2014). The SWELL Knowledge Work Dataset for Stress and User Modeling Research. _Proceedings of the 16th International Conference on Multimodal Interaction_.

* Kraaij, Prof.dr.ir. W. (Radboud University & TNO); Koldijk, MSc. S. (TNO & Radboud University); Sappelli, MSc M. (TNO & Radboud University) (2014): The SWELL Knowledge Work Dataset for Stress and User Modeling Research. DANS. https://doi.org/10.17026/dans-x55-69zp

* Nkurikiyeyezu, K., Yokokubo, A., & Lopez, G. (2020). The Effect of Person-Specific Biometrics in Improving Generic Stress Predictive Models. Journal of Sensors & Material, 1–12. http://arxiv.org/abs/1910.01770

* Schmidt, P., Reiss, A., Duerichen, R., Marberger, C., & Van Laerhoven, K. (2018). Introducing WESAD, a Multimodal Dataset for Wearable Stress and Affect Detection. Proceedings of the 2018 on International Conference on Multimodal Interaction - ICMI ’18, 400–408. https://doi.org/10.1145/3242969.3242985

* Statista. (2023, November 29). People experiencing stress, depression, and anxiety symptoms by age group worldwide 2022_. Health, Pharma & Medtech_.
* UC Berkeley Executive Education. (n.d.). Professional Certificate in Machine Learning and Artificial Intelligence.  https://em-executive.berkeley.edu/professional-certificate-machine-learning-artificial-intelligence
