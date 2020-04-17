# movie-recommendation-engine
Machine learning powered model to recommend movies based on your interests written in python.

#### Libraries :

- **sklearn.feature_extraction.text.CountVectorizer :**

Convert a collection of text documents to a matrix of token counts

- **sklearn.metrics.pairwise.cosine_similarity(X, Y=None, dense_output=True) :**

Compute cosine similarity between samples in X and Y.
Cosine similarity, or the cosine kernel, computes similarity as the normalized dot product of X and Y:


**Notes :**

1.
```python
def combine_features(row):
	try:
	  return row['keywords']+ " "+row['cast']+" "+row['genres']+" "+row['director']
	except:
		print("Error", row)
```

This method is used because the kewords in the dataset has a "NaN" in it. We need to replace it with an empty string (You can do whatever you want). We make a for loop for that.

```python
for feature in features:
	df[feature] = df[feature].fillna('') 
```

2.
Simple system to break the loop after we get 50 suggestions
```python
i=0
for movie in sorted_similar_movies:
	print(get_title_from_index(movie[0]))
	i=i+1
	if i>50:
		break
```       
  
  
Usage : Unzip the dataset zip file and then use it.
