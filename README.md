# NoisyABSA: Domain Generalization on ABSA task via utilizing noisy student architecture

## Introduction
This repository contains the implementation of NoisyABSA, which achieved high domain generalization performance in ABSA tasks. We applied the Noisy Student architecture in the NLP task, specifically Aspect Based Sentiment Analysis. With this approach, our model NoisyABSA surpasses the existing SOTA model and achieves new SOTA in the cross-domain tasks of ABSA.


## Paper
Our research results are written [here](https://github.com/NoisyStudents/NoisyABSA/blob/main/Teacher!%20Don't%20punish%20the%20Noisy%20Student.pdf).


## Dataset
We used SemEval 2014 Task 4 dataset for our experiment. The dataset is used as a benchmark for ABSA tasks and contains customer reviews from two domains - laptops and restaurants. We preprocessed the dataset as below format.
<image src="https://github.com/NoisyStudents/NoisyABSA/assets/74613565/267b8445-5dea-4d22-952c-789bc760cfae" width="8700" height="70">


## Tasks
We conducted our experiments on three novel domain tasks: Cross, Semi-Cross1 and Semi-Cross2.
### Cross Domain
Cross Doamin Task referss to when the domain of the test dataset is different from the train, and unlabeled dataset. In our model, unlabeled data is used to train the model with pseudo labeling.
### Semi-Cross Domain1
In Semi-Cross1 Domain Task, the teacher model is trained with train data on domain A and unlabeled data on domain B, then tested on domain B.
### Semi-Cross Domain2
Semi-Cross2 Doamin Task is the same as Semi-Cross1 except that unlabeled data on domain A is added to train the student model.

|Domain Task|Train|Unlabeled|Test|
|:---:|:---:|:---:|:---:|
|Cross|A|A|B|
|Semi-Cross1|A|B|B|
|Semi-Cross2|A|A,B|B|
|Joint|A,B|A,B|B|


## Model Use
To use our model, you can follow [NoisyABSA_example](https://github.com/NoisyStudents/NoisyABSA/blob/main/NoisyABSA_example.ipynb).
This example code is based on cross domain task with default noisy setting (weight_decay=0.01, max_grad_norm=1.0). If you want to test our model on different settings, you should change the dataset and configuration.
In the configuration, noisy is injected into the model by adjusting the weight_decay and max_grad_norm.
If you want to change domain tasks, you should change the training and test dataset as you intended.

