
# Image Segmentation through U-Net

This repository presents a project on **brain tumor image segmentation** using the **U-Net** architecture. The data is annotated in COCO format and preprocessed to generate masks for training, validation, and testing. TensorFlow and Keras are used to construct and train the U-Net model on medical imaging data.

## 📁 Dataset

The dataset used includes MRI images of brain tumors. It is structured into:
- `train/` and `train_mask/`
- `valid/` and `val_mask/`
- `test/` and `test_mask/`

Annotation files are in COCO JSON format.

## 🛠 Preprocessing

- **COCO conversion**: COCO annotations are converted to binary masks.
- **Image normalization**: All images and masks are resized to 256×256.
- **TensorFlow Dataset API**: Efficient data pipeline with caching, prefetching, and parallel mapping.

## 🔍 Model

The project implements the **U-Net** architecture, which is well-suited for biomedical image segmentation due to its encoder-decoder structure with skip connections.

### Model Features
- Input size: 256×256×3
- Encoder: Convolution + MaxPooling layers
- Decoder: Transposed Convolution + Concatenation with encoder features
- Output: Binary segmentation mask

## 📊 Training

- Optimizer: Adam
- Loss Function: Binary Crossentropy or Dice Loss
- Evaluation: Dice coefficient and visual validation
- Batch size: 10

## 🖼 Results

The segmentation outputs are visualized for qualitative evaluation. Each image is displayed side-by-side with its predicted mask.

## 🧩 Requirements

- Python 3.x
- TensorFlow 2.x
- OpenCV
- pycocotools
- imageio
- matplotlib
- seaborn

Install requirements:
```bash
pip install tensorflow opencv-python pycocotools imageio matplotlib seaborn
```

## 💡 Notes

- Avoided RAM crash during preprocessing by using TensorFlow's image loading functions instead of raw loops.
- Dataset caching and parallelism significantly improved performance.

## 📌 Future Work

- Integrate Dice loss for improved segmentation accuracy.
- Compare with other architectures like DeepLabV3+ or Attention U-Net.
- Integrate with Webapp
