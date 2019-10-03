Intructions to (almost*) reproduce our similarity submission1 predictions.

We used the Bert model and adaped the code in https://github.com/google-research/bert to the task.

1 - You must create two directories where bert configuration files and neural network weights will go: bertDir and modelDir .
2- You must create two other directories for input and output: dataDir and outputDir

3- bertDir
  - We used as starting point Bert-Base Multilingual Cased. 
    
  Download the zip file,   https://storage.googleapis.com/bert_models/2018_11_23/multi_cased_L-12_H-768_A-12.zip
  and put all the files in the bertDir.
  
4- modelDir
   Download the zip file, https://drive.google.com/file/d/1cbfdQJz7q4Nd2e3aNMv2t17RFr3xNNOo/view?usp=sharing
   and put all the files in the modelDir
   
5- inputDir: where the train dev and test tsv files are

6- outputDir: where the predictions file will go



* Our submission used a cloud TPU, if you run this code on the cpu the output will have a small difference on each prediction.
