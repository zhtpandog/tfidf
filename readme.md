# TFIDF #

## Introduction ##
Tf-idf stands for term frequency-inverse document frequency, and the tf-idf weight is a weight often used in information retrieval and text mining. This weight is a statistical measure used to evaluate how important a word is to a document in a collection or corpus. The importance increases proportionally to the number of times a word appears in the document but is offset by the frequency of the word in the corpus. Variations of the tf-idf weighting scheme are often used by search engines as a central tool in scoring and ranking a document's relevance given a user query. For more info, please check http://www.tfidf.com.  

## This code ##
tfidf.py implements tfidf algorithm and enables you to compare cosine tfidf similarity between your query document and all of the other documents you added.  
The code is tested in Python 2.7 environment. It requires numpy.  

## Usage demo ##
Create the tfidf object:  
```
table = tfidf()
```  
Add documents into corpus:  
```
table.addDocument(1, ["cat", "dog", "cat", "pig"])
table.addDocument(2, ["cat", "cat", "cat", "sheep"])
table.addDocument(3, ["cat", "dog"])
table.addDocument(4, ["sheep", "elephant"])
```
Do the preparation to calaulate idf when you finish adding documents:  
```
table.prep()
```
Get tfidf cosine similarities between document 1 and all other documents in corpus:  
```
print(table.similarities_by_name(1))
```
Get tfidf cosine similarities between an unseen document and all other documents in corpus:  
```
print(table.similarities_by_wordlist(["dog", "dog", "cat"]))
```
Output:  
```
{1: 1.0, 2: 0.27133820715336249, 3: 0.52063649363745212, 4: 0.0}
{1: 0.48122493653786197, 2: 0.15842159340701237, 3: 0.98223248815469177, 4: 0.0}
```