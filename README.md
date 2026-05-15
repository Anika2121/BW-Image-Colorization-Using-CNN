🪄🖼️ Deep Learning Based Image Colorization using Custom CNN Architecture

<div align="center">     

Automatic Black & White Image Colorization using Deep Learning

A custom-built CNN model capable of generating realistic colorized images from grayscale inputs using advanced attention mechanisms and U-Net architecture.

</div>
---

📌 Abstract

Image colorization is one of the most challenging computer vision tasks because a single grayscale image can correspond to multiple possible color combinations. This project presents a deep learning-based automatic image colorization system developed using a custom Convolutional Neural Network (CNN) architecture.

The proposed model combines:

U-Net Architecture

Residual Learning

CBAM Attention Mechanism

LAB Color Space Processing


to generate visually realistic colorized images from grayscale inputs.

The model was trained on the Oxford Flowers dataset obtained from Hugging Face and implemented entirely using PyTorch.


---

✨ Key Features

<table>
<tr>
<td width="50%">🧠 Deep Learning Features

Custom CNN from scratch

U-Net encoder-decoder structure

Residual blocks

CBAM attention module

Bilinear upsampling

LAB color space processing


</td>
<td width="50%">⚡ Performance Features

GPU acceleration support

Stable training with BatchNorm

Gradient clipping

SmoothL1 loss optimization

Saturation enhancement

Post-processing refinement


</td>
</tr>
</table>
---

🖼️ Project Demonstration

<div align="center">Input Image	Generated Output

Grayscale Image	AI Colorized Image


</div>> 📷 Add your project screenshots/results here for better GitHub presentation.




---

🏗️ System Architecture

Overall Workflow

Input RGB Image
       │
       ▼
Convert RGB → LAB
       │
       ▼
Extract L Channel
       │
       ▼
CNN Model Prediction
       │
       ▼
Predict a & b Channels
       │
       ▼
Combine L + ab
       │
       ▼
Convert LAB → RGB
       │
       ▼
Final Colorized Image


---

🧠 Model Architecture

The proposed architecture integrates multiple modern deep learning concepts into a unified framework.

🔹 U-Net Architecture

The network follows an Encoder–Decoder structure:

Encoder

Responsible for:

feature extraction

texture understanding

semantic representation


Decoder

Responsible for:

image reconstruction

color generation

spatial recovery



---

🔹 Skip Connections

Skip connections preserve low-level image details by directly transferring encoder features to the decoder.

torch.cat([decoder_feature, encoder_feature], dim=1)

This improves:

edge preservation

object consistency

output sharpness



---

🔹 Residual Learning

Residual blocks help stabilize deep neural network training.

Residual Formula

y = F(x) + x

Advantages

Prevents vanishing gradients

Improves feature propagation

Enables deeper architectures



---

🔹 CBAM Attention Module

CBAM (Convolutional Block Attention Module) improves feature selection by applying:

Channel Attention

Focuses on:

important feature maps


Spatial Attention

Focuses on:

important image regions


This significantly improves color prediction quality.


---

🎨 Why LAB Color Space?

Instead of RGB, the project uses the LAB color representation because it separates brightness from chromatic information.

<div align="center">Channel	Description

L	Lightness
a	Green ↔ Red
b	Blue ↔ Yellow


</div>
---

Colorization Strategy

The model learns:

Input = L \quad ; \quad Output = ab

Final reconstruction:

LAB = L + ab

Why LAB?

Easier learning process

Better color separation

Improved training stability



---

📂 Dataset

Oxford Flowers Dataset

Dataset Source: Hugging Face Dataset Repository

Dataset Characteristics

Diverse flower categories

Rich color distributions

High visual variability

Suitable for supervised colorization



---

🛠️ Technology Stack

<div align="center">Technology	Purpose

Python	Core programming language
PyTorch	Deep learning framework
torchvision	Image transformations
NumPy	Numerical computation
PIL	Image processing
scikit-image	LAB conversion
Matplotlib	Visualization


</div>
---

⚙️ Training Configuration

Hyperparameter	Value

Image Resolution	256 × 256
Batch Size	8
Epochs	30
Optimizer	AdamW
Learning Rate Scheduler	CosineAnnealingLR
Loss Function	SmoothL1Loss
Weight Decay	1e-4



---

📉 Loss Function

Smooth L1 Loss

Chosen because:

More stable than MSE

Less sensitive to outliers

Produces smoother convergence



---

Saturation Penalty

Additional saturation regularization was introduced to avoid dull grayscale-like outputs.

Benefits:

richer colors

enhanced vibrancy

improved realism



---

🚀 Optimization Techniques

✅ Batch Normalization

Improves:

convergence speed

training stability



---

✅ LeakyReLU Activation

Used instead of standard ReLU to avoid:

dying ReLU problem

zero-gradient regions



---

✅ Gradient Clipping

Prevents:

exploding gradients

unstable updates



---

✅ Bilinear Upsampling

Selected over transpose convolution because it reduces:

checkerboard artifacts

noisy reconstruction



---

📈 Results

The model successfully learned:

object structures

texture information

semantic color relationships


Generated outputs demonstrate:

realistic flower coloration

smooth transitions

visually appealing reconstruction



---

⚠️ Limitations

Despite strong performance, some limitations remain:

Ambiguous color prediction

Dependency on training dataset diversity

Difficulty handling unseen object categories



---

🔮 Future Improvements

Future work may include:

GAN-based colorization

Transformer architectures

Higher resolution support

Real-time deployment

Larger training datasets



---

▶️ Installation Guide

Clone Repository

git clone https://github.com/your-username/image-colorization-cnn.git
cd image-colorization-cnn


---

Install Dependencies

pip install torch torchvision numpy pillow matplotlib scikit-image datasets


---

Launch Notebook

jupyter notebook

Open:

imagecolorization.ipynb


---

📁 Repository Structure

├── dataset/
├── outputs/
├── saved_models/
├── notebooks/
│   └── imagecolorization.ipynb
├── README.md
├── requirements.txt
└── results/


---

👨‍💻 Contributors

<div align="center">Name	Role

Your Name	Model Development
Team Member	Data Processing
Team Member	Testing & Evaluation


</div>
---

📚 References

PyTorch Documentation

U-Net Research Paper

CBAM Attention Paper

Hugging Face Datasets



---

🏁 Conclusion

This project demonstrates the effectiveness of deep learning techniques for automatic image colorization. By integrating U-Net architecture, residual learning, and attention mechanisms, the model generates visually realistic colorized images from grayscale inputs while maintaining structural consistency and semantic understanding.

The project highlights the practical application of CNNs in computer vision tasks and serves as a strong foundation for future research in image restoration and generative AI systems.


---

<div align="center">⭐ If you found this project useful, consider giving it a star!

</div>