**Gender Detection From Bangla Handwritten Images**
 
Handwriting is a unique quality of human being, every person has unique handwriting that is very hard to copy but there can be some similarities
Between male and female handwriting. we will classify the difference between Male and Female Handwritting Digit using logistic regression.
 
Differences between Male and Female Handwriting Digit can be used in various applications like Archeology, forensic department. In this assignment, our main goal will be to achieve a good result using logistic regression and tuning hyperparameters correctly to get a better result.
 
 
 
 
 
**Dataset**
 
 
> For this experiment, we will use the dataset [Ekush](https://shahariarrabby.github.io/ekush/#download) which is available in **Github**. 
There will be a total of **30830** images, and it was split in a **90:10** ratio. **90%** (**27747**) of data is used in training and **10%** (**3083**) was used in testing.Whole dataset was shuffled before spliting , so that traning and testing dataset can have both label data. 
 
**Snapshot from Dataset**

><div align="center">
<img src="https://drive.google.com/uc?id=1GhuJfYchOjfNoBtwkpWivPRQinegMYwy" width="600">
</div>
 
 
**Experimental Setup**
 
 
> All of these experiments were performed using Google Colab free GPU, Models were created in PyTorch. 
 
 
During the whole experiment,
* The height and width of the input was **28*28 =784** 
* Output dimension was **(0,1)=2**
* Each batch size was **256**
* The number of iteration was **4000**
* **Softmax** activation function was used 
* GPU **Tesla T4** was available 
* Number of Epochs **332**
 
- **totaldata:** 30830
 
 
 
 
> - **minibatch:** 256
- **iterations:** 4,000
- **epochs**
  - $epochs = iterations \div \frac{totaldata}{minibatch} = 4000 \div \frac{30830}{256} = 332.14 == 332 $
 
We will use different optimizer(SGD and Adam) and learning rate to achieve better performance
 
**Result**

**Using Logistic Regression**
 
| Experiment Number      | Optimizer     | Learning Rate    |  Accurecy of last 500 iterations    |
| ------------- | ---------- | ----------- | ----------- |
|  1 |SGD   | 0.0001    | 51.41 |
|  2 |SGD   | 0.0005    |   50.02 |
| 3   | SGD | 0.0010 | 49.92 |
|  4 |Adam   | 0.0001    | 51.05 |
|  5 |Adam  | 0.02   |  50.86 |
|  6 |Adam   | 0.05    | 48.3 | |
 

**Using Deep Neural Network**

| Experiment Number      | Optimizer     | Learning Rate     |  Num of Hidden Layer   | Btach Size |Num of epoch    |   Accurecy of last 1000 iterations    |
| ------------- | ---------- | ---------- | ----------- | -----------  | ----------- | ----------- |
|  1 |SGD   | 0.02 | 4| 256 | 830   | 50.14  |
|  2 |SGD   | 0.01 | 4| 512 |  1660  | 49.17  |
|  3 |SGD   | 0.10 | 3| 256 | 830   | 50.66  |
|  4 |SGD   | 0.01 | 2| 1024 | 3321   | 49.82  |




 
 
