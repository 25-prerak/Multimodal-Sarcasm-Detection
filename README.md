# Multimodal-Sarcasm-Detection
Developed a multimodal sarcasm detection model, which can detect sarcasm from Audio as well as Text inputs. 

The dataset that we used for this project comprised of TV clips of famous sitcoms like FRIENDS, TBBT etc.

Sarcasm is often used by people to taunt or pester others. It is frequently expressed through inflection in speech or by using lexical, pragmatic, hyperbolic, and other features present in the text. Most of the work done by the researchers has been focused more on detecting sarcasm from the latter part, that is text data rather than the former that is audio. In this paper, we show that it is important to use both textual as well as audio features while detecting sarcasm. To carry out this task we propose a hybrid model, which takes a combined vector of extracted audio features as well as extracted text features from their respective models as an input. Our results indicate that the shortcomings of text were compensated by audio and vice-versa. The hybrid model outperforms both models where text and audio features were used individually.   

The types of features used for detecting sarcasm in text and audio are summarized in the below figure.

![](https://github.com/25-prerak/Multimodal-Sarcasm-Detection/blob/main/Images/1.jpg) 

Audio Model
In the preprocessing section for the Audio model, the mp4 files are converted to .wav files. Mfcc 
are created from the wav files and sliced into 1 second segments. These segments are trained on a 
LSTM Deep Learning model. The last layer of the rnn model is removed to convert it to an encoder 
and the encoded vectors of all segments are fetched and averaged out to create the vectors for the 
entire audio files. After this the vectors are trained in the audio model to predict the sarcasm for 
the entire audio files. The visual representation of this model is shown below.

![](https://github.com/25-prerak/Multimodal-Sarcasm-Detection/blob/main/Images/2.jpg)

Text Model
In the text model, first preprocessing was performed to remove unwanted characters from the text 
and clean it. Next through the help of a tokenizer, tokens were generated for the text. Further 
through the help of pre-trained word embeddings the text is converted into it’s vectors format. 
Now through the help of padding all the vectors are converted to a uniform length vector. Finally 
these padded vectors are used to train a CNN model in order to detect sarcasm from text. The 
visual representation of this model is shown below.

![](https://github.com/25-prerak/Multimodal-Sarcasm-Detection/blob/main/Images/3.jpg)

Hybrid Model
In the hybrid model the latent vectors generated in the audio model and the text model are fetched 
and combined. A 164 length vector is created from a 64 length audio vector and 100 length text 
vector. These vectors are then trained on a classifier to detect the sarcasm from both audio and text 
files. The visual representation of this model is shown in below.

![](https://github.com/25-prerak/Multimodal-Sarcasm-Detection/blob/main/Images/4.png)

The entire coding was done using python 3 and by using the google colab environment.

Complete information about the project and the results that we obtained can be found in the Report.pdf file.

This project was completed as a part of my final year project in order to obtain my undergraduate degree.
