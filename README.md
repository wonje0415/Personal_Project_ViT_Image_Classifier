# Personal_Project_ViT_Image_Classifier

## Goal

- Reproduct Visual Transformer and applying it to classify CIFAR-10

## Constraints

- GPU : 1 NVIDIA T4 (by using Colab)
- Storage limitation : 100MB (by using Colab)

## Duration

- 2025.09.15 ~ 2025.09.17 (During Military Services)

## Members

- Wonje Jang (Solo)

## Details

- CIFAR-10 dataset was used as train and valid dataset.
- Due to the number of training epochs, scheduler was not used.
- The model’s width is the same as ViT-Base and the depth is smaller: 12 → 4.
- I tried to closely follow the model architecture in the paper.
- After training, I applied simple online data augmentation to see how much it improves the model’s performance.
    - RandomHorizontalFlip
    - RandomCrop

## Results

<img width="1189" height="490" alt="image" src="https://github.com/user-attachments/assets/b9112fa5-b3a9-4742-a760-984c8db909dd" />


- In loss, data augmentation improved model’s performance.

|  | Best Valid Loss | Valid Accuracy where Best Valid Loss |
| --- | --- | --- |
| No Augmentation | 1.0736 | 0.627 |
| Using Augmentation | 0.8710 | 0.6970 |
- Also in Accuracy, data augmentation improved model’s performance.

## What I Learned

1. Learn the exact ViT’s architecture
    - especially, Image patch and positional embedding, transformer encoder in ViT, [CLS] token in ViT, Classification Head.
    - Reading paper and Realization to code is very different. In code, we should reflects on how to realize the content from paper to the code.
    - The each field of AI such as vision, LM, etc can have impact on other fields.
2. Data Preprocessing is also very important part.
    - Online Data augmentation can be simple but strong techniques to improve model’s performance.
