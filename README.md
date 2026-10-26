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


**General description of the notebook:**   
This notebook covers the implementation of training three neural network models (MLP, CNN, and Transformer) on the MNIST dataset to recognize handwritten digits. The general goal is to check which architecture performs best and to see whether data augmentation improves performance.    

The 60k training data was split into 50k for training and 10k for validation, and all images were normalized with the standard MNIST mean and standard deviation. The 10k testing images were normalized without augmentation and only used for testing purposes.    

Each model (MLP, CNN, and transformer) was trained twice: once on the original training data and once on training data processed with augmentation (random rotation up to 15 degrees and random translation up to 10%). The training settings were identical for all models: learning rate of 0.001, Adam optimizer, batch size of 64, 15 epochs, and seed 42.   

Training and validation loss and accuracy were tracked every epoch, and the testing performance was evaluated with accuracy, macro-averaged precision, recall, F1, ROC-AUC, and confusion matrices.   


**Conclusion:**   
Overall, CNN is the best architecture for having the highest accuracy, F1, and ROC-AUC score in both non-augmentation and augmentation settings.   

Augmentation improved MLP and CNN performance specifically by increasing accuracy, F1, and ROC-AUC in the testing set. The training curves suggest that MLP and CNN were overfitting without augmentation, since their training accuracy reached 99.62% and 99.8% but their validation loss stopped improving and started to increase. Augmentation acted as an effective regularizer and kept validation loss dropping.    

Transformer performed worse with augmentation, as its test accuracy dropped from 98.02% to 97.46% and F1 from 0.98 to 0.9744. Transformer might be underfitting since its training accuracy with augmentation was only 94% and was still improving at the last epoch. It might still need more training epochs before it can show performance improvement with augmentation.    
