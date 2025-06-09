# 🖼️ Image Captioning with Deep Learning (Flickr8k)

This project implements an image captioning model using deep learning. It generates human-like descriptions for images by combining a pre-trained CNN (Xception) for image feature extraction and an LSTM-based sequence model for text generation.

## 📂 Dataset
**We use the Flickr8k dataset, which consists of:**
8,000 images of everyday scenes.

You can download the dataset from https://forms.illinois.edu/sec/1713398.

## 📌 Project Structure
**1. 📁 Data Preparation**
- Mount Google Drive to access your dataset.

- Load and clean captions from Flickr8k.token.txt.

- Save processed descriptions to descriptions.txt.

**2. 🧠 Feature Extraction**
- Load the Xception CNN model (without top layer).

- Resize images to 299x299 and extract 2048-dimensional feature vectors.

- Save features in features.p using pickle.

**3. 📝 Caption Preprocessing**
- Create a tokenizer and compute max_length.

- Tokenize and pad caption sequences.

- Prepare training/validation sets based on provided splits.

**4. 🔧 Model Architecture**
- Image Encoder: Dense layer + dropout on Xception features.

- Caption Decoder: Embedding + LSTM for caption tokens.

- Fusion Layer: Combine both embeddings and decode the next word.

**5. 🧪 Training**
- Train using tf.data.Dataset + custom data generator.

-  Save the best model with ModelCheckpoint.

- Plot training/validation loss over epochs.

**6. 📸 Inference**
- Load trained model.

- Extract features from new images.

- Generate captions using top-k sampling.

## 💡 Future Improvements
- Add BLEU, METEOR, CIDEr metrics.

- Switch LSTM decoder to Transformer.

- Add beam search for better caption generation.

## 🧾 Citation
**If you use the Flickr8k dataset, please cite the following:**

M. Hodosh, P. Young and J. Hockenmaier (2013)
"Framing Image Description as a Ranking Task: Data, Models and Evaluation Metrics",
Journal of Artificial Intelligence Research, Volume 47, pages 853–899.
http://www.jair.org/papers/paper3994.html
