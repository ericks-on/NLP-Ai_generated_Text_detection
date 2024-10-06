# Business Understainding
As more AI-powered tools that can produce essays, reports, and other academic content become available, students might be employing these technologies to do their assignments. While in some situations AI can improve learning, when these tools are abused for academic dishonesty, the educational process is compromised. Schools must recognize assignments that were created by AI instead of by students in order to protect academic integrity.

## Problem statement
The school's goal is to create a system that can identify assignments that were probably created using artificial intelligence (AI) tools automatically. The objective is to guarantee that students turn in their own work in order to uphold academic standards.

## Objectives
- Get the model with high recall
- Get a model with high precision
- High accuracy

## Success criteria
- Precision -> above 90%
- Recall -> above 90%
- Accuracy -> above 90%

# Data Understanding
The data consist of four datasets with text of varying word count.
- Part1 -> 20 - 100 Words
- Part2 -> 100 - 200 Words
- Part3 -> 200 - 300 Words
- Part4 -> 300+ Words

The first column of CSV contains the text and the second holds its respective class. The class column contains a binary value.
Here, `0 denotes human-written` and `1 AI-generated text`.

Source of the data is [Github](https://github.com/aakash-dl/HWAI)

# Results
 - The baseline model was the Naive bayes which had an accuracy of about 88% at first.
 - After removing the stopwords, the model slightly improved to 89%.
 - Stemming and lemmatization resulted in lower performance with accuracy dropping to 86%
 - So finally the effective preprocessing steps include; 
    1. Removing stopwords and punctuation
    2. Adding POS tags

 Other models:
 | Model              | Accuracy   | Recall     | Precision  |
|--------------------|------------|------------|------------|
| Logistic Regression| 0.9652     | 0.9560     | 0.9740     |
| Random Forest      | 0.9533     | 0.9523     | 0.9545     |
| XGBoost            | 0.9570     | 0.9490     | 0.9647     |
| `Keras  `          | `0.9793  ` | `0.9738  ` | `0.9848`   |

The keras model(Logistic regression as a neural network) was the final model with the highest performance.



# Deployment
This [Web-app](https://github.com/ericks-on/AiDetect) Provides prompt to enter text then detect if its Ai-generated or not.
