Intructions to (almost) reproduce our similarity submissions,submission1 and submission3 (submission2 contained an error).
We used bert model in the similarity task and adaped the code in https://github.com/google-research/bert to the task.

1 - You must create two directories where bert configuration files and neural network weights will go: bertDir and modelDir .
2- You must create two other directories for input and output: dataDir and outputDir

3- bertDir

  - Submission1: as starting point we used Bert-Base Multilingual Cased. 
    
  Download the zip file,   https://storage.googleapis.com/bert_models/2018_11_23/multi_cased_L-12_H-768_A-12.zip
  and put all the files in the bertDir.
  
  -Submission3: as starting point we used a fine tuned Bert model trained with  portuguese texts (Wikipedia, CETELEMPublico and Folha de São Paulo).
  
  Download and put the following files in bertDir:
  model.ckpt-60475.data-00000-of-00001= https://drive.google.com/drive/folders/1HuuRkcS9r9k6ODRwozoWngr8-BdRLR70?usp=sharing
  model.ckpt-60475.index= https://drive.google.com/file/d/1OAP-catkd1PZtQHO9-qIU6UgVoRO70cs/view?usp=sharing
  model.ckpt-60475.meta = https://drive.google.com/file/d/1VzMenEgDudDSuPwdybnUcsXFi0i1ddRg/view?usp=sharing
  vocab.txt =
  "bert_config.json =
  
