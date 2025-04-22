# Cell-Segmentation-with-Multi-head-UNet

The aim of this project is to segment and classify individual cells from microscopy images, a crucial task in biomedical image analysis. Precise cell segmentation plays a key role in automated disease diagnosis, drug testing, and cellular behavior modeling. In this work, we leverage powerful deep learning architectures like **UNet with EfficientNetV2** as backbone and combine them with **self-supervised learning techniques** to produce a robust and generalizable model for cell segmentation.

We are making this an open-source repository, enabling others to contribute improvements—be it via new datasets, better loss functions, or optimized training pipelines!

---

## 🧬 About the Data

The dataset used is **LIVECell**, a challenging and diverse dataset containing various cell lines captured under different conditions. Due to inter-cell variability, class imbalance, and domain noise, training an accurate model requires thoughtful architecture design and domain-specific preprocessing.

We used **clinical-style augmentations** inspired by microscopy environments such as brightness shifts, blur, and spatial distortions to improve generalization on unseen samples.

---

## 🧠 Model Architecture

- **Encoder**: Pretrained **EfficientNetV2** backbone, trained using **self-supervised contrastive learning** and **image inpainting** tasks to capture robust feature representations.
- **Decoder**: A multi-head UNet decoder structure that predicts both segmentation masks and auxiliary classification labels.
- **Loss Functions**: Used domain-specific composite losses including Dice loss and BCE to handle class imbalance.
- **Input Pipeline**: Augmented features were generated using a combination of geometric and photometric augmentations to simulate real-world variations in microscope captures.

---

## 🛠️ Training

- Fine-tuned on the LIVECell dataset for 50+ epochs using PyTorch.
- Trained using Google Colab with a mixed precision training setup for efficient computation.
- Leveraged transfer learning to accelerate convergence and improve performance on limited labeled samples.

---

## 📊 Results

The model achieved the following results on the validation split of the LIVECell dataset:

- **F1 Score**: 0.85
- **Precision**: ~0.83
- **Recall**: ~0.87
- **Dice Coefficient**: 0.84

These results show strong performance on unseen data and robustness across cell types.

---

## 🔍 Future Work

- Explore transformer-based UNet hybrids for better contextual reasoning.
- Incorporate cell tracking and temporal data.
- Use few-shot learning to adapt to unseen cell types with minimal labels.

---

## 🤝 Contributing

We welcome contributions! Whether it’s adding new augmentations, improving the model, or bringing in new datasets, feel free to open a pull request or issue.

---

## 📚 References

- [LIVECell Dataset](https://livecell-dataset.github.io)
- [EfficientNetV2](https://arxiv.org/abs/2104.00298)
- [Self-supervised Learning in Bioimaging](https://arxiv.org/abs/2101.01629)

---

## 🧑‍💻 Author

**Varunsai Alaparthi**  
Project as part of research work at NITC, 2022

---

*This project is open-sourced under the MIT License.*
