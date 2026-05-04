Introduction: Semantic segmentation involves assigning a class label to every pixel within an image and is fundamental to a range of applications, including tumour delineation in MRI, lesion detection in dermoscopic imaging, organ segmentation in CT scans, and the localisation of small objects in industrial inspection. In many of these settings, images exhibit low contrast, significant noise, or highly subtle anatomical or structural features. When this is coupled with the limited availability of expert-annotated datasets, there is a clear need for label-efficient, reliable, and robust segmentation techniques. 
Conventional supervised deep learning architectures such as U-Net and DeepLab deliver strong performance under well-annotated and high-quality imaging conditions. However, their effectiveness diminishes substantially when trained on sparse labels or low-contrast datasets, where they frequently fail to capture faint boundaries, rare classes, or fine-grained structural variation. This limitation becomes particularly evident in clinical imaging workflows, where annotation is costly, time-consuming, and requires specialist expertise. 
Recent progress in generative modelling, particularly diffusion models and generative adversarial networks (GANs), has demonstrated considerable potential to address these challenges. By learning the underlying distribution of images, these models are capable of generating realistic representations and enhancing boundary fidelity, even in low-data or noisy environments. Beyond simple augmentation, generative approaches can support semi-supervised and self-supervised learning frameworks, improve feature representation, and mitigate annotation scarcity. Such advances make generative-driven segmentation a promising direction for improving performance and generalisability in complex, data-limited segmentation tasks. 



Recent Literature on hybrid, semi-supervised, and generative segmentation 
1. Minaee et al. (2022) - Surveyed major deep learning segmentation methods and challenges 

2. Yang et al. (2022) - Proposed ST++ for improved pseudo-label based semi-supervised segmentation 

3. Kwon et al. (2022) - Highlighted regularized learning under limited-label segmentation settings 

4. Li et al. (2023) - Introduced UniMatch for strong-weak consistency regularization 

5. Zhou et al. (2023) - Emphasized the difficulty of preserving segmentation boundaries with limited supervision 

6. Yang et al. (2023) - Proposed Diff-UNet for diffusion-enhanced volumetric segmentation 

7. Wu et al. (2024) - Developed MedSegDiff for medical image segmentation using diffusion probabilistic models

Software Environment 
The software environment consists of Python-based deep learning frameworks and scientific computing libraries. PyTorch is used for tensor operations, model definition, automatic differentiation, and optimization, while MONAI supports healthcare-oriented data transforms, dataset abstractions, and segmentation workflow standardization. 

Python - Core programming environment 

PyTorch - Deep learning model development and training 

MONAI - Medical imaging preprocessing, transforms, loaders, and utilities 

NumPy - Numerical computation 

OpenCV / scikit-image - Image preprocessing and augmentation 

Matplotlib / Plotly - Visualization of training curves and results 


Hardware Setup 
The experiments are intended to run on GPU-enabled computing infrastructure to support computationally intensive training of segmentation, diffusion, and adversarial models. A CUDA-capable environment is preferred for efficient training, mixed-precision execution, and batch-wise optimization of high-resolution image data. 


CPU - Multi-core processor 
GPU - NVIDIA CUDA-enabled GPU 
RAM - 16 GB or higher 
Storage - SSD for high-throughput dataset access 
OS - Linux or Windows with CUDA support 

Datasets:
ISIC 2018 Skin Lesion Segmentation 
URL: https://www.kaggle.com/datasets/yatharthtripathi56/isic-2018-skin-lesion-segmentation
Images: 2,594 dermoscopic images 
Classes: Skin lesion vs. background 
Challenges: Variable lighting, hair artifacts, low contrast regions 
Split: 70% train, 15% validation, 15% test 
Annotation setting: Simulate limited labels (10%, 30%, 50%) 
 
Synapse Multi-Organ CT Segmentation 
URL: https://www.kaggle.com/datasets/yatharthtripathi56/brats2020
Images: abdominal CT scans 
Classes: Spleen, right kidney, left kidney, gallbladder, esophagus, liver, stomach, aorta, inferior vena cava, portal vein, pancreas 
Challenges: Low contrast between organs, class imbalance 
Split: Leave-one-out cross-validation (typical in small dataset scenarios) 
 
BraTS 2020 Brain Tumor Segmentation
URL: https://www.kaggle.com/datasets/yatharthtripathi56/brats2020
Images: multimodal MRI scans (T1, T1c, T2, FLAIR) 
Classes: Necrotic/non-enhancing tumor, edema, enhancing tumor, background 
Challenges: Low contrast between tumor regions, variable image quality 
Split: 70% train, 15% validation, 15% test 
Annotation setting: Simulate limited labels 
