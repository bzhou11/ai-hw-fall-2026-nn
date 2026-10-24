Assignment #4.1: MNIST Recognition by NN  
Author: Bo Zhou 

**code:**    
MNIST_recognition_by_NN_code.ipynb: contains all code for data loading, training, testing, and performance evaluation.  
The Jupyter notebook was constructed and run in Google Colab with a T4 GPU.   

**Testing Results:**   

**for training performance:**
- all_results/train/train_performance.png: training/validation loss and accuracy curves for all three models with/without augmentation.  
- all_results/train/train_performance_stats.json: all training epoch statistics. 

**for testing performance:**
- all_results/test/test_performance_no_augmentation.png: testing performance for models trained on data without augmentation. 
- all_results/test/test_performance_augmentation.png: testing performance for models trained on data with augmentation.  
- all_results/test/Confusion_Matrix.png: confusion matrix for all three models with/without augmentation.  
- all_results/test/test_performance_stats.json: all testing performance statistics, accuracy, precision, recall, F1, auc. 
