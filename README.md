# Acute Lymphoblastic Leukemia (ALL) Classification using CNN-Based Model
## Acute lymphoblastic Leukemia Problem
#### Definition:
- Acute lymphoblastic leukemia (ALL) starts from white blood cells in the bone marrow that become leukemic. 
- Leukemic Lymphocytes block the production of normal cells, multiply uncontrollably, and survive better than normal cells.
#### Motivation:
If caught early, leukemia can be cured by undergoing several cancer treatments. An AI system was trained to estimate 3-year lung cancer risk from radiologists’ computed tomography (CT) readings and other clinical information. These predictions could then be used to schedule follow-up CT scans for patients with cancer, augmenting current screening guidelines. Validation of such systems on multiple clinical sites and an increasing number of prospective evaluations have brought AI closer to being deployed and making a practical impact in the field of radiology.

According to the WHO, delays in cancer diagnosis and treatment can come at a cost of successful treatment. We believe that an AI-approach to leukemia diagnosis will reduce the human-errors when used as a tool by medical specialist and also reduce the logistical delays that are associated with turnaround time.
![alt text](/delays_in_cancer.png?raw=true)
### Leukemia Diagnosis:
### Blood Smear Test:
Changes in the numbers and the appearance of the cells often help diagnose leukemia. Most patients with ALL have too many immature white cells called lymphoblasts (or just blasts) in their blood, and not enough red blood cells or platelets. Lymphoblasts are not normally found in the blood, and they don't function like normal, mature white blood cells.

A diagnosis of leukemia is usually made by analyzing a patient’s blood sample through a complete blood count (CBC) or microscopic evaluation of the blood. Patients with ALL have too many lymphoblasts in their blood, and not enough red blood cells or platelets.
![alt text](/Lymphoblasts.png?raw=true "The dark purple cells are lymphocytes defined by their size and shape.")


### Challenges:
## Leukemia Classifier
## The Data and its Limits
## Contrast Enhancement and Masking
## Data Augmentation
## CNN Baseline Model
## Baseline Model Testing Results
## Primary Model
### Alexnet
### VGG
### ResNet18
## Constructing a Deep Classifier
## Feature Extractor Performance Comparison:
### Validation (Before Fine-Tuning)
### End-to-End Refinement + Hyperparameter Tuning
### Qualitative Analysis of Fine-Tuned ResNet
## ResNet18 After Fine-Tuning: Testing
## Baseline and Primary Model Comparison

