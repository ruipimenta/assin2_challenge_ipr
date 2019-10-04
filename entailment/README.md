Instructions to (almost*) reproduce our entailment submission1

We used the Bert model and adaped the code in https://github.com/google-research/bert to the task.

It requires  python tensorflow 1 (we used python3 and tensorflow-1.14).

1 - You must create four directories : bertDir and modelDir, dataDir and outputDir .

2- bertDir, for bert configuration files: 
      Download the multilingue bert model (fine tuned to portuguese vocabular) zip file:https://drive.google.com/file/d/1S1B-TR0E0H1zXDvA7iedm49H_iJwP_Uw/view?usp=sharing and put all the files in the bertDir .

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
