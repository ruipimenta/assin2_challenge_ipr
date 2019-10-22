Here you have instructions and scripts to either 1) use our trained model to generate our predictions or 2) train a model, as we did, fine-tunning Bert's model. 



# Generate predictions


Intructions to (almost*) reproduce our similarity submission1 predictions.

* Our submission used a cloud TPU, if you run this code on the cpu the output will have a small difference on each prediction.


We used the Bert model and adapted the code in https://github.com/google-research/bert to the task.

1 - You must create four directories: bertDir, modelDir, dataDir and outputDir .

2- bertDir , where bert configuration files are.
  - We used as starting point Bert-Base Multilingual Cased. 
    
  Download the zip file,   https://storage.googleapis.com/bert_models/2018_11_23/multi_cased_L-12_H-768_A-12.zip
  and put all the files in the bertDir.
  
3- modelDir, where final neural network weights will go.
   Download the zip file, https://drive.google.com/file/d/1cbfdQJz7q4Nd2e3aNMv2t17RFr3xNNOo/view?usp=sharing
   and put all the files in the modelDir
   
4- inputDir: where the train dev and test tsv files are

5- outputDir: where the predictions file will go

6- Edit the file github_cpuPredictAssin2Similarity.py to define the strings bertDir, modelDir, inputDir and outputDir.

7- Run the above script:

      python3 github_cpuPredictAssin2Similarity.py
8- The predictions will go to the file, test_similarity_results.tsv.


# Train a model on the Similarity Task

As above we used the Bert model and adapted the code in https://github.com/google-research/bert to the task.

1 - You must create four directories: bertDir, dataDir and outputDir .

2- bertDir , where bert configuration files are.
  - We used as starting point Bert-Base Multilingual Cased. 
    
  Download the zip file,   https://storage.googleapis.com/bert_models/2018_11_23/multi_cased_L-12_H-768_A-12.zip
  and put all the files in the bertDir.
  
3- dataDir: where the train dev and test tsv files are

4- outputDir: where the new weights files will go

5- Edit the file github_cpuTrainAssin2Similarity.py to define the strings bertDir, dataDir and outputDir. 

You must also assigne a value to the variable 'num_train_epochs'. In our submission1 we used 235 epochs. The of the pearson correlation on the development data was 0.96618927 and the mse was 0.080897026. There is random component on training so you may achieve different values (on the development and test data) with the same number of epochs. Perhaps you may need to restart the training from scratch a few times before we can achieve similar results. In our submission we used the weights that corresponded to our best results on the development set... 

6- Run the script:

      python3 cpuTrainAssin2Similarity.py
      

7- The initial script run on 64Gb TPU. You may get errors due to the fact that you dont have enought memory. In that case you may reduce the parameters batch_size ( train, eval and predict). With 12Gb GPU we set train_batch_size=16. However, reducing train_batch_size may reduce the performance.  




