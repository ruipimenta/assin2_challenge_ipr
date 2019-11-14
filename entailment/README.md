Here you have instructions and scripts to either 1) use our trained model to generate our predictions or 2) train a model, as we did, fine-tunning Bert's model.

# Generate predictions


Instructions to (almost*) reproduce our entailment submission1

We used the Bert model and adapted the code in https://github.com/google-research/bert to the task.

It requires  python tensorflow 1 (we used python3 and tensorflow-1.14).

1 - You must create four directories : bertDir and modelDir, dataDir and outputDir .

2- bertDir, for bert configuration files: 
      Download the https://drive.google.com/file/d/1S1B-TR0E0H1zXDvA7iedm49H_iJwP_Uw/view?usp=sharing and put all the files in the bertDir .

3-  modelDir, for final neural network weights:
      Download the entailment weights zip file: https://drive.google.com/file/d/1la7UY2mtY55dws5ORsVcIHspnx5tjhsI/view?usp=sharing 
      
      and put all the files in the modelDir .
 4- inputDir: where the train, dev and test tsv files are.
 
 5- outputDir: where the predictions file  will go. 
 
 6- Edit the file github_cpuPredictAssin2Entail.py to define the strings bertDir, modelDir, inputDir and outputDir.

 7- Run the above script: 
 
          python3 github_cpuPredictAssin2Entail.py
 
 8- The predictions will go to  a three columns file, test_entail_results.tsv, where the columns contain the predicted probabilities of: 'Entailment', 'None' and 'Paraphrase' (this last option should never occur in ASSIN2).  
 
 
Our submission used a cloud TPU, if you run this code on the cpu the output will have a small difference on each prediction (it will give a slightly better result than our submission).


# Train a model on the Entailment Task
As above we used the Bert model and adapted the code in https://github.com/google-research/bert to the task.

1 - You must create four directories: bertDir, dataDir and outputDir .

2- bertDir , where bert configuration files are.

We used as starting point Bert-Base Multilingual Cased that we fine tuned to portuguese language
Download the zip file, https://drive.google.com/file/d/1S1B-TR0E0H1zXDvA7iedm49H_iJwP_Uw/view?usp=sharing 
and put all the files in the bertDir.

3- dataDir: where the train dev and test tsv files are

4- outputDir: where the new weights files will go

5- Edit the file github_cpuTrainAssin2Entaiment.py to define the strings bertDir, dataDir and outputDir.

You must also assign a value to the variable 'num_train_epochs'. In our submission1 we used 25 epochs. The accuracy of the model on the development data was 0.95% (assin script values, tensorflow reported values are worse). There is random component on training so you may achieve different values (on the development and test data) with the same number of epochs. Perhaps you may need to restart the training from scratch a few times before we can achieve similar results. In our submission we used the weights that corresponded to our best results on the development set...


7- Run the script:

  python3 github_cpuTrainAssin2Entail.py


8- The initial script run on 64Gb TPU. You may get errors due to the fact that you dont have enought memory. In that case you may reduce the parameters batch_size ( train, eval and predict). With 12Gb GPU we set train_batch_size=16. However, reducing train_batch_size may reduce the performance. 
