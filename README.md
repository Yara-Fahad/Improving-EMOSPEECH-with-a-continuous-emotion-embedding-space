# Improving EMOSPEECH with a Continuous Emotion Embedding Space

This project presents a novel approach to **emotional text-to-speech (TTS) synthesis** by combining a fine-tuned BERT-based text emotion classifier, a Conditional Variational Autoencoder (CVAE) for speech emotion representation, and a CLIP-style adapter model to align both modalities. Our goal is to generate more expressive, emotionally rich synthetic speech.

---

## Key Highlights

-  Fine-tuned BERT on a custom text emotion classification dataset.
-  Developed a Conditional Variational Autoencoder (CVAE) for emotion-based speech embeddings.
-  Designed an adapter module to align text and speech embeddings using contrastive learning.
-  Achieved strong classification accuracy and meaningful emotion clustering in the latent space.

---

##  Model Architecture

The system is composed of three core components:

1. **BERT-based Emotion Classifier**
   - Trained on text to predict emotion labels and extract embeddings.
   - Fine-tuned using the "Emotion Analysis from Text" dataset with 5 emotion classes.

2. **CVAE for Speech Emotion Embedding**
   - Trained on the Emotional Speech Dataset (ESD).
   - Generates emotionally-conditioned speech embeddings.
   - Incorporates residual blocks for deep and stable training.

3. **Adapter Module**
   - Bridges 768-dim BERT embeddings and 256-dim CVAE embeddings.
   - Uses a bottleneck + residual design.
   - Trained with a CLIP-style contrastive loss.


## Dataset 

### Emotional Speech Dataset (ESD)
- Subset: 10 English speakers, 5 emotions (angry, sad, neutral, happy, surprise) available at: https://github.com/HLTSingapore/Emotional-Speech-Data
- Created a custom subset of 280 samples (28 unique, manually labeled sentences × 10 speakers)

### Emotion Analysis from Text
- Cleaned and balanced for 5 emotion classes
- Used for fine-tuning the BERT classifier
- Available at: https://www.kaggle.com/datasets/simaanjali/emotion-analysis-based-on-text

## Acknowledgements
This project is inspired by the work of [EmoSpeech](https://github.com/deepvk/emospeech). We thank the authors of EmoSpeech for open-sourcing their codebase, which provided a valuable foundation for our experiments.
