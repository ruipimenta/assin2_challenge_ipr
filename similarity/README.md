Intructions to (almost*) reproduce our similarity submission1 predictions.

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



* Our submission used a cloud TPU, if you run this code on the cpu the output will have a small difference on each prediction.
