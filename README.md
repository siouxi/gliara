![Gliara Banner](images/banner.png)

---

# 🌑🧠 Gliara: An AI Classifier for Alzheimer's 🧠🌑

**Gliara** is an exciting neuroscience project aiming to develop a precise **AI classifier for Alzheimer's disease**. 🤖🔍 This progressive neurodegenerative condition impacts millions, making early and accurate diagnosis crucial. 🌟

By leveraging advanced **machine learning** and **neuroimaging data** (fMRI, PET, MRI), Gliara will detect subtle patterns indicative of Alzheimer's. 📊🧠 Our goal is to provide a more holistic predictive model, integrating insights into both neuronal connectivity and glial function. 🚀 This project represents a significant leap in applying AI to public health, transforming how we diagnose and understand this devastating disease. 💜

---

# Key Objectives

1.  **Develop a Highly Accurate AI Classifier:** Create and optimize an **AI-driven machine learning model** that precisely classifies Alzheimer's disease using **multi-modal neuroimaging data** (fMRI, PET, MRI).
2.  **Integrate Holistic Biomarkers:** Incorporate features related to both **neuronal connectivity and glial function** into the AI model to establish a more comprehensive and predictive diagnostic approach.
3.  **Validate Clinical Efficacy:** Rigorously validate the AI classifier's performance against clinical standards, aiming for high accuracy and low error rates to support **early and accurate diagnosis**.
4.  **Advance AI in Public Health:** Demonstrate the significant potential of this AI solution to **transform Alzheimer's diagnosis** and contribute to public health by enabling timely intervention.

## GliaraV1 | Begin utilizing volumetric data.

- [x] Redesign ResNet18 for Alzheimer's disease classification (e.g., healthy vs. AD). This requires replacing its segmentation-specific output layers with a classification head (e.g., global average pooling + fully connected layer + softmax/sigmoid).
- [x] Implement basic data augmentation for your dataset. This involves applying transformations like random rotations, flips (horizontal/vertical), shifts (width/height), and zooms to increase the dataset's size and variability.
- [x] Adapt a MedicalNet pre-trained model for your specific medical imaging classification problem.

---

# References

Open Access Series of Imaging Studies (OASIS): Cross-Sectional MRI Data in Young, Middle Aged, Nondemented, and Demented Older Adults. Marcus, DS, Wang, TH, Parker, J, Csernansky, JG, Morris, JC, Buckner, RL. Journal of Cognitive Neuroscience, 19, 1498-1507. doi: 10.1162/jocn.2007.19.9.1498  https://sites.wustl.edu/oasisbrains/home/oasis-1/

Chen, S., Ma, K., & Zheng, Y. (2019). Med3D: Transfer Learning for 3D Medical Image Analysis [Preprint]. arXiv. https://arxiv.org/abs/1904.00625


