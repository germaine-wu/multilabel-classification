# multilabel-classification
## Project description:
The project is to solve the multi-label classification task. Each sample in this dataset includes:  
* an image,  
* one or more (up 20) labels,  
* a short caption that summarizes the image.  

## The evaluation metric:
* Mean F1-Score  
>The F1 score, commonly used in information retrieval, measures accuracy using the statistics precision p and recall r. Precision is the ratio of true positives (tp) to all predicted positives (tp + fp). Recall is the ratio of true positives to all actual positives (tp + fn). The F1 score is given by:  
$$x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}$$  
`F1 = 2 pr/(p+r) where p = tf/ (tp+fp), r = tp/(tp+fn)`  
  
>The F1 metric weights recall and precision equally, and a good retrieval algorithm will maximize both precision and recall simultaneously. Thus, moderately good performance on both will be favored over extremely good performance on one and poor performance on the other.

## Runtime
The project is run in colab. The there datasets are uploaded into google drive.
* Verify the identity and create the PyDrive client:
```
auth.authenticate_user()
gauth = GoogleAuth()
gauth.credentials = GoogleCredentials.get_application_default()
drive = GoogleDrive(gauth)
```
* Load file from google drive to colab, remember the id refers to the file id in google drive:
```
downloaded = drive.CreateFile({'id': '1MQoBbuJANnSaZ5qzFGH5iqXpocYNgmOT'})
downloaded.GetContentFile('train.csv')

downloaded = drive.CreateFile({'id': '1L8AjKScAYvHIqIloI57vny17REAILfT4'})
downloaded.GetContentFile('test.csv')

downloaded = drive.CreateFile({'id': '1xg_Su0hWF2Dmw05-4mXTXBcxWOhKuCx_'})
downloaded.GetContentFile('data.zip')
```
* unzip the `data.zip`:
```
!unzip data.zip -d data
```
