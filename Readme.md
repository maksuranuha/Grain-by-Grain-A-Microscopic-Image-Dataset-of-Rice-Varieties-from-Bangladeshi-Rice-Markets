Paper Link: https://doi.org/10.1016/j.dib.2025.112058

## Overview

This repository presents a comparative study of DenseNet201 model performance on the *Grain by Grain: A Microscopic Image Dataset of Rice Varieties from Bangladeshi Rice Markets** from Bangladeshi markets. The study evaluates the impact of data augmentation on classification accuracy across 10 distinct rice varieties.

## Dataset

The **Grain by Grain** dataset contains:
- **2,010 original high-resolution microscopic images** (640×480 pixels, JPG format)
- **10 rice varieties**: Aush, Beroi, BR-28, BR-29, Ghee Bhog, Katari Nazir, Katari Siddho, Swarna, Miniket, and Chinigura
- **200+ images per variety** from local Dhaka markets
- After augmentation: **8,010 total images**

## Motivation

Ensuring food security and fiscal stability is crucial among South Asian countries, such asChina, India, and Bangladesh, that live on rice as a regular dietary staple [1,11]. Rice is a richsource of starch, protein, amylose, zinc, iron, carbohydrates, as well as vitamins, phenolic acids,and antioxidants that aid in fighting diseases like metabolic system imbalances, obesity, dia-betes, cancer, and cardiovascular health issues. Although polishing rice has been a commonmarket practice to boost profit, it is often at the cost of undermining the main nutritional factor of rice consumption. Furthermore, rice milling takes away a substantial amount, around 8–10 %grain portion. About 80 % percent minerals (Fe, Zn, Mg, P) and vitamins drop with the removalof the outer husk. Another article reveals that steaming rice affects milled rice more sig-nificantly than plain rice. During steaming, the Zinc from the center of the grain goes to theoutermost layer. Since polishing rice removes the outer layer, the Zinc that wants to move disappears along with the discarded bran. Therefore, the more milling, the more minerals are lost[3].Addressing these concerns, our study presents an expertly handpicked and curated dataset of2010 rice kernels comprising 10 distinct rice categories, locally named as: (A) Aush, (B) Beroi, (C)BR-28, (D) BR-29, (E) Ghee Bhog, (F) Katari Nazir, (G) Katari Siddho, (H) Swarna, (I)Miniket, and(J) Chinigura. Most of these are commonly preferred for their sweet aroma, glossy texture, andthinness, ideal for daily use, traditional dishes, and festivities. This proposed dataset will act asan asset in balancing the rice refinement tactics. It can further facilitate a real-time importationmonitoring system to increase fiscal stability, public health assurance with quality, and mitigateunethical activities. 

## Overview

This repository presents a comparative study of DenseNet201 model performance on the **Grain by Grain** microscopic rice dataset from Bangladeshi markets. The study evaluates the impact of data augmentation on classification accuracy across 10 distinct rice varieties.

## Dataset

The **Grain by Grain** dataset contains:
- **2,010 original high-resolution microscopic images** (640×480 pixels, JPG format)
- **10 rice varieties**: Aush, Beroi, BR-28, BR-29, Ghee Bhog, Katari Nazir, Katari Siddho, Swarna, Miniket, and Chinigura
- **200+ images per variety** from local Dhaka markets
- After augmentation: **8,010 total images**

## Motivation

Rice polishing and milling practices remove approximately 80% of essential minerals (Fe, Zn, Mg, P) and vitamins. This dataset exposes structural differences in rice grains before and after milling, serving as a resource for quality assessment and food security research.

## Dataset Augmentation

Four augmentation techniques were applied:
- **Rotation**: 30° fixed degrees
- **Shearing**: ~20% intensity
- **Horizontal Flip**: Randomized
- **Vertical Flip**: Randomized
- **Randomization factor**: 4 (total 8,010 augmented images)

## Model Architecture

**DenseNet201** with the following configuration:
- Input size: 70×70 pixels
- Global Average Pooling layer
- Dense layer with softmax activation
- Loss function: SparseCategoricalCrossentropy
- Optimizer: Adam (learning rate: 0.001)
- Epochs: 50
- Batch size: 60
- Train-Test-Validation split: 80:10:10

## Results

### Original Dataset (Without Augmentation)
| Metric | Value |
|--------|-------|
| Accuracy | 93% |
| Loss | 0.248 |
| Training Time | 5 min 22 s |
| Total Images | 2,010 |

### Augmented Dataset (With Augmentation)
| Metric | Value |
|--------|-------|
| Accuracy | 94% |
| Loss | 0.230 |
| Total Images | 8,010 |

### Table : Label-wise Precision, Recall, F1-score, and Support - DenseNet201 on Original Dataset

| Sl. | Name | Precision | Recall | F1-score | Support |
|-----|------|-----------|--------|----------|---------|
| 1 | Aush | 0.96 | 0.96 | 0.96 | 25 |
| 2 | Beroi | 0.88 | 0.79 | 0.83 | 19 |
| 3 | Bri-28 | 0.95 | 0.91 | 0.93 | 19 |
| 4 | Bri-29 | 0.95 | 0.91 | 0.93 | 23 |
| 5 | Chinigura | 0.96 | 1.00 | 0.98 | 24 |
| 6 | Miniket | 0.97 | 0.94 | 0.95 | 33 |
| 7 | Katari Najir | 0.80 | 0.84 | 0.82 | 19 |
| 8 | Ghee Bhog | 0.87 | 0.83 | 0.85 | 24 |
| 9 | Katari Siddho | 0.97 | 0.94 | 0.95 | 30 |
| 10 | Swarna | 0.88 | 0.96 | 0.92 | 24 |
| **Accuracy** | | | | **0.93** | **240** |

### Table : Label-wise Precision, Recall, F1-score, and Support - DenseNet201 on Augmented Dataset

| Sl. | Name | Precision | Recall | F1-score | Support |
|-----|------|-----------|--------|----------|---------|
| 1 | Aush | 1.00 | 1.00 | 1.00 | 78 |
| 2 | Beroi | 1.00 | 1.00 | 1.00 | 91 |
| 3 | Bri-28 | 0.85 | 0.85 | 0.85 | 81 |
| 4 | Bri-29 | 0.92 | 0.91 | 0.91 | 87 |
| 5 | Chinigura | 0.99 | 0.99 | 0.99 | 78 |
| 6 | Miniket | 0.99 | 0.96 | 0.97 | 89 |
| 7 | Katari Najir | 0.89 | 0.87 | 0.88 | 86 |
| 8 | Ghee Bhog | 0.91 | 0.91 | 0.91 | 80 |
| 9 | Katari Siddho | 0.90 | 0.93 | 0.91 | 81 |
| 10 | Swarna | 0.91 | 0.96 | 0.93 | 89 |
| **Accuracy** | | | | **0.94** | **840** |

## Key Findings

- Data augmentation improved overall accuracy from 93% to 94%
- Loss decreased from 0.248 to 0.230, indicating better model convergence
- Augmentation achieved more balanced class-wise performance
- Classes like Aush and Beroi achieved perfect 1.00 precision and recall
- Model generalization improved with expanded training data


## Applications

- **Quality Control**: Automated rice grain classification and quality assessment
- **Market Monitoring**: Real-time importation monitoring and authenticity verification
- **Food Security**: Nutritional impact assessment from milling processes
- **Policy Making**: Data-driven recommendations for balanced market appeal and nutrition preservation

## Citation

```
Grain by Grain: A Microscopic Image Dataset of Rice Varieties from Bangladeshi Rice Markets
Available at: https://data.mendeley.com/datasets/sfp9s96prh/1
```
