# Classification of Composers Using Convolutional and Long Short-Term Memory Networks

## Project Overview
This project is designed to classify composers using MIDI files through two distinct computational approaches: 1) Convolutional Neural Networks (CNN) and 2) Long Short-Term Memory networks (LSTM) that utilize fixed sequence tokens, akin to methods used in Natural Language Processing (NLP). Evaluating these methods with accuracy, precision, and recall metrics, the results reveal that while all approaches are insightful, the LSTM using fixed sequence tokens excels in identifying unique musical styles, offering more precise composer classification. This enhances automated music analysis and supports the development of advanced digital musicology and interactive educational tools.

## Dataset

We have used the "midi_classic_music" dataset from Kaggle, focusing specifically on MIDI files from four renowned composers: Bach, Beethoven, Mozart, and Chopin. The dataset comprises 925 MIDI files from Bach, 211 from Beethoven, 136 from Chopin, and 256 from Mozart, totaling 1,528 files.

To address the imbalance and enhance the diversity of our training dataset, we implemented data augmentation techniques for MIDI files associated with composers Beethoven, Mozart, and Chopin. Recognizing the need to bolster the dataset for these composers, we generated additional variations of the existing MIDI files by applying transformations such as time stretching which alters the tempo while maintaining the original pitch of the audio. These augmentations not only increased the volume of data but also introduced a richer set of examples that capture a broader spectrum of each composer's style. Conversely, to maintain a balanced dataset, we strategically reduced the number of MIDI files for Bach, who was over-represented in our initial dataset. This approach ensured that our model was trained on a more evenly distributed dataset, which is crucial for avoiding bias towards any particular composer's style and enhancing the model's ability to generalize across different musical compositions. 

## Methodology
### Data Representation for LSTM (NLP style)
MIDI files are preprocessed to extract pitch and pitch variation data. These are transformed into sequences that resemble words in natural language processing, making them suitable for sequence learning in the LSTM model.

### Model Architecture

#### LSTM (NLP style) model
- **Embedding Layer**: Maps tokens to a higher-dimensional space.
- **LSTM Layers**: Two layers that process sequences to capture temporal dependencies.
- **Dropout Layer**: Mitigates overfitting by randomly omitting elements of the data during training.
- **Output Layer**: Classifies sequences into composer categories using a softmax function.

### Training and Validation

The LSTM (NLP style) model was trained/validated/test on a split of the data sequences, while oveall testing was performed on a separate unseen dataset that was set aside before sequence generation. Parameters were tuned through extensive experimentation with different batch sizes and sequence lengths to optimize performance.

## Results

### LSTM (NLP style) model

- **Accuracy**: Reached up to 93% on unseen test dataset.
- **Confusion Matrix**: Showed high precision and recall across multiple composer categories, particularly effective at distinguishing between composers with distinct styles.
- **Parameter Tuning**: Best results were achieved with a batch size of 256 and sequence length of 100.

## Future Enhancements

### LSTM (NLP style) model
- **Bidirectional LSTM**: To capture more complex patterns by processing data in both directions.
- **Cross-Genre Training**: To increase the robustness and applicability of the model across different musical styles.

## How to Run the Project
1. Download the dataset (keep only Bach, Beethoven, Chopin and Mozart folders in "data" directory). 
2. Clone the repository.
3. Install dependencies:
   
    pip install -r requirements.txt
4. Run the model.


```python

```
