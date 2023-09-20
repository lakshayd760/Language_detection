# Language_detection
* This is language detection project for detection of language for a given text
* This can be used to identify the language of the text from the given languages using machine learning and natural language processing

## Dataset :
Dataset link: 
(https://raw.githubusercontent.com/amankharwal/Website-data/master/dataset.csv)<br/>
You can import the dataset directly by using the following code:
>data = pd.read_csv("https://raw.githubusercontent.com/amankharwal/Website-data/master/dataset.csv")<br/>
>data.head()

![](https://github.com/lakshayd760/Language_detection/blob/main/Images/Annotation%202023-09-20%20131815.png)<br/>
Our dataset consist of 22 different languages with 1000 sentences for each language
> data["language"].value_counts()

![](https://github.com/lakshayd760/Language_detection/blob/main/Images/Annotation%202023-09-20%20132109.png)<br/>
## Model Training
### Preprocessing 
For preprocessing firstly we have to remove null values from the data<br/>
After that, we have to convert the text data to vectors that can be trained using our model, for this process we have used CountVectorizer() given by sklearn
>cv = CountVectorizer()<br/>
>X = cv.fit_transform(x)

To know more about count vectorizer refer to :
(https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.CountVectorizer.html)
<br/>
### Model Building
For text classification we have used Multinomial naive bayes model given by sklearn
>model = MultinomialNB()<br/>
>model.fit(X_train,y_train)

To know more about Muiltinomial Naive Bayes, refer to :
(https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.MultinomialNB.html)

### Model testing
To calculate the accuracy score of the model use the following code:
>model.score(X_test,y_test)

Our model is giving us 95.3168044077135% accuracy score<br/>
We can test our model on real life examples as:
>user = input("Enter a Text: ")      <br/>
>data = cv.transform([user]).toarray()      <br/>
>output = model.predict(data)            <br/>
>print(output)

By running this code we can take input from the user and make prediction as in which language the input text is written
