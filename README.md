# Acute Lymphoblastic Leukemia (ALL) Classification using CNN-Based Model
## Acute lymphoblastic Leukemia Problem
#### Definition:
- Acute lymphoblastic leukemia (ALL) starts from white blood cells in the bone marrow that become leukemic. 
- Leukemic Lymphocytes block the production of normal cells, multiply uncontrollably, and survive better than normal cells.
#### Motivation:
If caught early, leukemia can be cured by undergoing several cancer treatments. An AI system was trained to estimate 3-year lung cancer risk from radiologists’ computed tomography (CT) readings and other clinical information. These predictions could then be used to schedule follow-up CT scans for patients with cancer, augmenting current screening guidelines. Validation of such systems on multiple clinical sites and an increasing number of prospective evaluations have brought AI closer to being deployed and making a practical impact in the field of radiology.

According to the WHO, delays in cancer diagnosis and treatment can come at a cost of successful treatment. We believe that an AI-approach to leukemia diagnosis will reduce the human-errors when used as a tool by medical specialist and also reduce the logistical delays that are associated with turnaround time.

![alt text](/delays_in_cancer.png?raw=true)
## Leukemia Diagnosis:
### Blood Smear Test:
Changes in the numbers and the appearance of the cells often help diagnose leukemia. Most patients with ALL have too many immature white cells called lymphoblasts (or just blasts) in their blood, and not enough red blood cells or platelets. Lymphoblasts are not normally found in the blood, and they don't function like normal, mature white blood cells.

![alt text](/Lymphoblasts.png?raw=true "The dark purple cells are lymphocytes defined by their size and shape.")

A diagnosis of leukemia is usually made by analyzing a patient’s blood sample through a complete blood count (CBC) or microscopic evaluation of the blood. Patients with ALL have too many lymphoblasts in their blood, and not enough red blood cells or platelets.

### Challenges:
- Publicly Available Datasets: There is not a large quantity of publicly available dataset for this as it is a niche problem. Had to get creative to increase the number of images. the equipment needed to capture images of whole slides is costly and is therefore unavailable in many health systems
- Expertise: Lack the medical expertise to differentiate the cells, a medical diagnosis is a much harder classification problem for a novice than other image classification. Getting blood smears images is beyond our skill level.
- Resources: Models that accept whole medical images require expensive hardware with more memory to reduce time. So blood smear images need to resized so that we could meet time constraints. and this can come at the cost of the system drawing connections between different areas of the image. Systems for medical image classification often involve trade-offs to make inputs compatible with neural networks

## Leukemia Classifier
Our AI classifier would replace the most common microscopic analysis performed and would classify leukemia into the following categories.
- Benign:
- Malignant
  - Early ALL
  - Pre B ALL
  - Pro B All 
## The Data and its Limits
![alt text](/ALL_breakdown.png?raw=true)
- The data used to train our model and model the problem overall was the Acute Lymphoblastic Leukemia dataset collected by Aria et al
- Dataset contains more that 3200 images of peripheral blood smears exhibiting Benign, Early, Pre-B type, and Pro-B type ALL.
- Here, as we can see, 
  - Benign ALL consists of lymphoblasts, shown in purple, that may exhibit blastomic, or tumourous, qualities, but grow slowly enough and do not harm surrounding tissue enough for them to be considered cancerous or harmful to a patient. Our dataset contains 500 of these type of images
  - Early ALL involves the early stages of B-cell development where B-cells may not have spread far into the surrounding tissue but exhibit the precursor-B marker for B-type ALL. Detecting ALL at this stage of the cell development typically yields a survival rate of 89% according to cancer.net since there are many avenues for treatment.
  - Precursor B ALL occurs when cancerous B lymphocytes have effectively matured, appear much larger and less uniform than their benign forms and begin harming surrounding cells. At this stage of ALL, the cancer can develop quickly over mere days or weeks. The prognosis for this stage of ALL for adults over the age of 20 is 75% to enter remission, but roughly 30% relapse after 5 to 6 years.
  - Pro-B ALL is a rare sub-type of ALL where B-cells remain immature and do not grow the way their Pre-B counterparts do. They are still cancerous and harm nearby cells but are harder to detect. As a result only 40% of patients with Pro-B ALL even enter remission.
- Peripheral blood smearing involves examining a thin layer of blood smeared across a glass slide under a microscope
In the diagnosis of ALL, this can be an arduous process where a human lab technician must examine and make a diagnosis by eye, a process which is subjective and time-consuming, requiring much experience
  - As a result there are very few datasets and images publicly available that have any significant number of images and a large range of classification.
  - Many datasets are either small, or extremely costly to procure
- Furthermore, due the human error that comes with staining, imaging, and labelling these datasets, many of them are far from objective enough to feed to a neural network in their raw form.
  - Differences in slide colour
  - Poor image quality
  - Too much similarity between different cells

### Contrast Enhancement and Masking
![alt text](/Masking.png?raw=true)
### Data Augmentation
##### Effect on the dataset:
- Increase the size of the dataset
- Introduce imperfections to the dataset
##### Effect on the model:
- More data = Better training
- Better generalization
- Better prepared for flawed and imperfect real-life data
- Accuracy increase from 93% to 97%

![alt text](/augment1.png?raw=true)
![alt text](/augment2.png?raw=true)
![alt text](/augment3.png?raw=true)

## CNN Baseline Model
![alt text](/CNN_Classifier.png?raw=true)
### Baseline Model Testing Results
![alt text](/Baseline_Results.png?raw=true)
## Primary Model Choice
#### Alexnet
![alt text](/alexnet.png?raw=true)
#### VGG
![alt text](/vgg.png?raw=true)
#### ResNet18
![alt text](/resnet18.png?raw=true)
### Constructing a Deep Classifier
![alt text](/constructing_classifier.png?raw=true)
### Feature Extractor Performance Comparison:
![alt text](/extraction_results.png?raw=true)
### End-to-End Refinement + Hyperparameter Tuning
![alt text](/fine_tuned_model.png?raw=true)
#### Validation
![alt text](/fine_tuned_validation.png?raw=true)
#### Qualitative Analysis of Fine-Tuned ResNet
![alt text](/fine_tuned_quality.png?raw=true)
#### Testing
![alt text](/fine_tuned_test.png?raw=true)
### Baseline and Primary Model Comparison
![alt text](/fine_results.png?raw=true)

