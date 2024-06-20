# ML-FraudModel

## Dataset
The dataset used in this project is Indonesian text messages, each of which has a label. This dataset consists of 1143 text messages categorized into three labels: Normal, Fraud, and Promo. Each text message has one label that corresponds to its content. The following is the distribution of the number of text messages for each label: Normal (569 messages), Fraud (335 messages), and Promo (239 messages).
## Preprocessing
To ensure the data is ready to be used in training machine learning models, we perform several preprocessing steps as follows:
- Lowercase: All text is converted to lowercase to avoid the distinction between uppercase and lowercase letters.
- Remove Punctuation: Punctuation marks are removed to clean up the text.
- Remove Extra Spaces: Excess spaces are removed for consistency.
- Stopword Removal: Using the Literature module, we remove Indonesian stopwords that have no important meaning in the context of text analysis.
- Stemming: Words are converted to their base form using the Literature module as well as abbreviated words are converted to their original form using the slang dictionary stored in the slang.txt file.
- Tokenization: The text is broken down into words or tokens to facilitate further analysis.
## Make Classification Model
The text labels in the dataset are converted into integer form to make it easier to process by machine learning models. Here is the label mapping:
* Normal: 0
*	Penipuan: 1
*	Promo: 2

To build the classification model, we used the Bidirectional Long Short Term Memory (BiLSTM) architecture. This architecture was chosen for its ability to capture long-term dependencies in text, which is important for natural language text analysis. Here are the details of the model architecture used:

`Model Architecture`
* Embedding Layer: Converts the words in the text into a vector representation.
* SpatialDropout1D Layer: Adds dropout to reduce overfitting.
* Bidirectional LSTM Layer: Captures context from both directions (forward and backward) in the text.
* Dense Layer: Fully connected layers to generate the final prediction.
* Activation Function: Uses softmax to generate probabilities for each class.

## Evaluation
The model was trained using the Adam optimizer with a learning rate of 0.001 and categorical cross-entropy as the loss function. After the training process, the model achieved a validation accuracy of 92%.

The following is an overview of the model performance for each epoch
<br>
<img src="https://github.com/Bangkit-Team-C241-PS499/ML-FraudModel/blob/main/Others/graphic%20model.png" lebar="300" />

The following confusion matrix is obtained
<br>
<img src="https://github.com/Bangkit-Team-C241-PS499/ML-FraudModel/blob/main/Others/confusion%20matrix%20model.png" lebar="300" />
