Both multi-layer perceptrons (MLPs) and convolutional neural networks (CNNs) perform exceeedingly well on the original MNIST digits dataset. So well in fact, that it is not hard to find simple models with very differing parameters regularly achieving >95% on the dataset across kaggle, primarily with stock keras architecture. There is good reason to then apply these model architectures built for the original MNIST on its derivatives - such as the fashion-MNIST, which was the original basis for this notebook submitted as an assignment for a Master's course at the University of Sydney. This notebook has been overhauled since then to investigate another MNIST-derivative of even greater challenge - 15 handwritten chinese characters. 

There are several key differences from the original MNIST set that make this challenge difficult. Namely, there are 5 more digits added while we also have to deal with the base similarity of several of the first three numbers in the Chinese lexicon:
* 零 - for 0  
* 一 - for 1
* 二 - for 2  
* 三 - for 3  
* 四 - for 4  
* 五 - for 5  
* 六 - for 6  
* 七 - for 7  
* 八 - for 8  
* 九 - for 9  
* 十 - for 10
* 百 - for 100
* 千 - for 1000
* 万 - for 10 thousand
* 亿 - for 100 million

Highly complex digits, such as 五 - 5, should be easier to classify for both models given high difference when training, while the CNN filters will have a particularly difficult time differentiating 一, 二 and 三. 

As seen in this notebook, initial accuracies are far lower than that which we might see in a typical MNIST setup. All architectures in this notebook are referenced from sources originally applying them to MNIST datasets, before I have made my own tunings based on suitability for the Chinese MNIST.

We start by quickly exploring the data and setting up our neural networks, before doing some exploratory models that help us decide which parameters are suitable to carry forward to hyper-parameter tuning, which can be a very expensive exercise, as seen in the runtimes. 

The final and best parameters delivered via the GridSearchCV form the evaluative model that is performed on the test set, having been trained and validated on a train & validation split. 

High accuracies are almost delivered by the hyper-parameter tuning, and unsurprisingly the computationally-expensive CNN performed the best, as it should for image recognition. 

萬歲!
