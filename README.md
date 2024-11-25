# Breast_cancer

## About the dataset

This dataset contains **3,383 mammogram images** focused on breast tumors, annotated in a folder structure (70% negative, 30% positive).
The dataset was exported from Roboflow, a platform for computer vision projects.
It is ideal for building and testing Deep-learning models aimed at detecting breast tumors through mammograms.

The dataset was augmented using techniques such as horizontal and vertical flips, rotations, and the application of random black rectangles on the images.

<p align="center">
  <img src="https://github.com/user-attachments/assets/a6011be5-fcea-40e6-8a32-dfd724cae72a" alt="Description de l'image">
  <br>
  <em>4 mammographic images after augmentation with their labels (1 positive, 0 negative)</em>
</p>

## Neural networks

I used transfer learning on the following CNN architectures : ResNet50, ResNet101, EfficientNetV2 and ConvNeXt by fine-tuning the classification layers and some of the last feature layers.

<p align="center">
  <img src="https://github.com/user-attachments/assets/a5665943-458b-425c-a288-8dc24b7a0343" alt="Description de l'image">
  <br>
  <em>Classification using CNN (C-H-W)</em>
</p>

## Metrics and evaluation

My final model achieved an **accuracy of 69%** on the test dataset, with a **recall of 67%** and a **precision of 59%** for the positive class. These results are promising, considering the limited amount of data and the class imbalance in the dataset.

<p align="center">
  <img src="https://github.com/user-attachments/assets/c6adacd9-c160-4359-bf7a-b5d1b7f7fa1e" alt="Description de l'image">
  <br>
  <em>Some predictions on the test dataset (80% accuracy here)</em>
</p>

## Moving forward

Despite these promising results, there is still room for improvement.

### Balancing and adding data

One approach is to balance the data by adding more positive class images. However, it's important to be cautious about the quality and type of the added images. Indeed, cancer can be benign or malignant, and depending on its type, the cancerous cells will likely appear different. According to the results, it appears that the classifier struggles to detect benign cancers : false negatives may occur when no abnormal mass of cells is present. However, false positives can arise from detecting an abnormal mass that is not cancerous. It is challenging to assess the quality of the data without extensive medical knowledge in this field.

### Computing power

With a better GPU and increased RAM, it becomes possible to train deeper feature layers and conduct more extensive tests on the neural networks. However, more data is also required for this.
