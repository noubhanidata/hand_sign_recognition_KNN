# MNIST hand sign classifier

![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master) 

Mnist sign language classifier is an experimental project to test the performance of machine learning vs deep learning in the prediction of a given hand sign 
TensorflowV2.0-powered project

the CNN version is available at : [Cnn hand sign recognition](https://github.com/noubhanidata/hand_sign_recognition_CNN).
![hand sign](https://github.com/noubhanidata/hand_sign_recognition_KNN/blob/d49ec85934439d05f0d27153529c03ff7fc949c4/images/hand%20sign.jpg) 


## Features

- Import data and start training the model right away
- Augmente the data as you need (upto 10x ready to use)
- save your trained models or load a trained one 
- up to 99,78% accuracy

note : execution/training time relies heavily on your computer performance and wither you have gpu acceleration or not   
(refer to tensorflow v2.0 documentation)

## Tech

mnist hand sign classifier uses a number of open source libraries:

- [skitlearn] - for the PCA and Knn models , metrics 
- [pandas + numpy] - for data manipulation
- [joblib + pickle] - to save the trained models
- [scipy] - for image shifting
- [time] - to get time consumption by each approach
- [matplotlib] - to plut the results and graphs
- [IPython] - to display images

And of course Python 3.8


## Documentation 
```sh
to_image(array, label = True)
```
> takes : -`array` : numpy array containing pixel values of an image 
     -`label` : a boolean flag to check for header
     
```sh
shift_image(image, dx, dy)
```
> takes : -`image` : numpy array containing pixel values of an image 
     -`dx` : the shift along the x axis
     -`dy` : the shift along the y axis

```sh
train_df = pd.read_csv(r"taining-data-here")
test_df = pd.read_csv(r"test-data-here")
```
> takes : -`"taining-data-here"` : the path to the csv file containing the pixels of taining data
     -`dxtest-data-here` :  the path to the csv file containing the pixels of test data
```sh
 PCA(n_components='mle') 
```
> uses : -`"mle"` : Automatic choice of dimensionality for PCA
     -to apply the analysis to data use the methode `fit(x,y)` :  refere to the sckitlearn documentation 

    
```sh
    pk.dump(pca, open("pca.pkl","wb"))
```
> takes : -`"pca"` : the pca trained model 
     -to change the path/name of the file to save change the `pca.pkl` file 
     refere to the pickle documentaion

     
   ```sh
    knn.fit(pcatest.transform(X_train.reshape(data.shape[0],784)), y_train)
```
> takes : -`"X_train"` : the numpy array containing the pixel values 
-`y_train` : the numpy array containing the labels 
     refere to the sckitlearn knn documentaion
   ```sh
      model = load('knn.joblib') 
```
> takes : -`'knn.joblib'` : the path to the trained model 
     refere to the pickle knn documentaion

 ```sh
    cf_matrix = confusion_matrix(y_test, Knny_pred , normalize='true')
```
> takes : -`y_test` : the numpy array containing the correct labels
-`Knny_pred` : the numpy array containing the predicted labels
 `normalize` : boolean flag to set the normalisation of the matrix elements
 ```sh
 augmenteData(data,model)
```
> takes : -`data` : the numpy array containing the data to be augmented
-`model` : the model that will be using the augmented data 
 ```sh
pred = model.predict(X_test)
```
> takes : `X_test` :numpy array containing the values to be predicted  

## License

MIT

**open source*

