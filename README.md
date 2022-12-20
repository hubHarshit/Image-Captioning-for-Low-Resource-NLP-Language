Low resource languages are languages that have limited or insufficient data available for natural language processing (NLP) tasks. These languages often have small populations of speakers, and may not have a long history of written texts or a developed infrastructure for collecting and digitizing linguistic data.
Some examples of low resource languages include:
Indigenous languages: Many indigenous languages have small numbers of speakers and may not have a long history of written texts. Examples include Hawaiian, Maori, and Yucatec Maya.
Less widely spoken languages: There are many languages that are spoken by relatively small numbers of people, but are not necessarily indigenous languages. Examples include Basque, Estonian, and Welsh.
Low-income or developing countries: In some cases, low resource languages may be spoken in low-income or developing countries where there may be less infrastructure or funding available for language technology research and development.
Developing NLP tools and resources for low resource languages can be challenging, but it is important for preserving linguistic diversity and enabling equal access to information and communication. Researchers and organizations are working on developing techniques and resources to support the development of NLP tools for low resource languages.

Image captioning is the process of generating a textual description of an image or video. It involves using machine learning algorithms to analyze the content of an image and generate a natural language description of it. Image captioning can be useful for a variety of applications, including helping visually impaired people understand the content of images and videos, and improving the accessibility of visual media.There are several approaches to building image captioning systems. One common approach involves using a combination of convolutional neural networks (CNNs) and recurrent neural networks (RNNs). The CNN is used to extract features from the image, and the RNN is used to generate the natural language description based on the features extracted by the CNN.
Other approaches to image captioning involve using transformers or other types of neural networks. In general, the goal of image captioning is to produce descriptive and accurate captions that accurately describe the content of the image.

This project entailed generating captions for images in three different languages- Hausa( a chadic language), Kyrgyz( native anguage for Kyrgyzthan)  and Thai( native language of Thailand). 
The project takes three different approaches for doing so. 

Approach 1- Thai Language
Comparatively, Thai Language has much better resources than the other two languages. We worked on generating caption for our test data by supplementing our training data from image caption dataset found on HuggingFaces. The problem with approach was Tokenization. Thai language does not have any whitespaces hence tokenizing the caption became an issue. Microsoft Azure came to the rescue. We used Azure's language translator to convert captions in English Language. We then used transfer learning technique utilizing pre-trained InceptionV3 model and added a dense layer to train on our data. For the captions, a RNN was used to generate captions. 

Approach 2- Hausa Language
Hausa Language is a very low resource language hence it was very difficult to train the model. The training dataset was slightly imbalanced which made it even difficult to implement the model. The best approach we could come up with was playing with the neural network layers we initially trained. I also made use of BertTokenizer to do a word peice tokenization that gave better results.

Approach 3- Kyrgyz Language
This language gave the best result out of the three languages. We obsereved that this particular language had good resources on Azure. To utilize this, we first generated captions for the images using Azure Image captioning tool and then converetd these English captions to Kyrgyz using Language Translator. 


The final model was evaluated using the Levenshtein Distance for which the final score was 58.58074.


