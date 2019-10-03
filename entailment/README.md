Instructions to (almost*) reproduce our entailment submission1

We used the Bert model and adaped the code in https://github.com/google-research/bert to the task.

1 - You must create two directories where bert configuration files and neural network weights will go: bertDir and modelDir . 2- You must create two other directories for input and output: dataDir and outputDir

3- bertDir

4-  modelDir

      Download the entailment weights zip file: https://drive.google.com/file/d/1la7UY2mtY55dws5ORsVcIHspnx5tjhsI/view?usp=sharing 
      
      and put all the files in the modelDir
 5- inputDir: where the train dev and test tsv files are
 6- outputDir: where the predictions file  will go 

Our submission used a cloud TPU, if you run this code on the cpu the output will have a small difference on each prediction (it will give a slightly better result than our submission)
