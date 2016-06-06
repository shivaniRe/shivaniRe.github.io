---
layout: post
title: An Unsupervised Translation Engine
---

It is interesting to note that there are 3000+ spoken languages in the world and a few hundred written languages. We still have hundreds of languages that do not have an online translator. Even though there are online translators available, they do not address languages spoken in various parts of the world. For example, there is a language called 'Dogri' which is spoken by about 3 million people in northern India. Not having an online translator is a hindrance to accessing online content by millons of people. This problem inspired me to build an algorithm that can translate text between any two languages. 

The data source for this project is UN documents. The input data consists of English UN documents with their exact Spanish translations. For this project, I used English and Spanish languages but this model can be applied to any language. Before building the model, it is important to have clean data which means converting text to lowercase, eliminate special characters, accents etc. One very important thing that I learnt through this project is to have clean data. Even a single punctuation mark or an apostrophe can give inaccurate results. 

Once the data is clean, tag all the Spanish words. This makes it easy to compare all the English words with only Spanish words and not with other English words. Now that the data is clean and tagged, give English and Spanish text as one document to the model. Giving English text with its corresponding Spanish translation in the same document helps the algorithm identify words that coexist.

##### Example of input document (Multilingual Corpus):
![](/images/Example_of_input_doc.png)

The above multilingual corpus is given as input to the LSI(Latent Semantic Index) model which is a vector space model. In the vector space model, terms form dimensions of an indexing space. Documents and queries are represented by vectors in this space. An LSI model consists of 4 main steps 
. Creating a Term-Document Matrix
. Transform the Term-Document Matrix
. Dimension Reduction (Singular Value Decomposition SVD)
. Retrieval in Reduced Space

Thus, the output of the LSI model is a reduced space multilingual term document matrix. These vectors for every English and Spanish word in the corpus can be compared using a measure of similarity such as cosine or inner product. Terms from the reduced multilingual matrix are compared using cosine similarity to get similar words based on score. 

##### Technical procedure:
![](/images/LSI_Model_Procedure.png)

Below are the three highest scoring Spanish translations for sample English words based on above algorithm. 

|English word           |Spanish translations                                       |
|-----------------------|-------------------|-------------------|-------------------|
|facilitating	 					|	facilitando       | facilitar         | aprovechando      |
|imported	 					    |	importadas        | importaciones     | exportada         |
|often	 					      |	menudo            | frecuencia        | frecuentemente    |
|language	 					    |	idioma            | dialecto          | lengua            |
|communication	 				|	comunicaci\u00f3n | fundo             | fongum            |
|began	 					      |	inicia            | comienza          | prosigue          |
|documentation	 				|	documentaci\u00f3n| yuki              | basse             |
|helped	 					      |	ayudado           | contribuido       | permitido         |
|written	 					    |	escrito           | conciliar\u00e1n  | escritas          |
|translators	 					|	traductores       | revisores         | auxiliares        |
|between	 					    |	entre             | interparlamentaria| mutuo             |
|substantially	 				|	sustancialmente   | considerablemente | significativamente|
|which	 					      |	cual              | claramente        | literalmente      |

We can discern that this algorithm not only captures regular words but also captures verb forms and plurals accurately. To make these translations available to everyone I have built a chrome extension. Code for this extension is available [here](https://github.com/shivaniRe/seekna-chrome-extension). For future work, it is worth trying n-gram translations and implementing text translation using word2vec neural network. Another area worth exploring is translating idioms. Code for my unigram translation algorithm is available on [github](https://github.com/shivaniRe/Text_translator).
