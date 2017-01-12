# the-nature-conservancy-fisheries-monitoring
kaggle competition: https://www.kaggle.com/c/the-nature-conservancy-fisheries-monitoring
+ [forums](https://www.kaggle.com/c/the-nature-conservancy-fisheries-monitoring/forums)
+ [kernels](https://www.kaggle.com/c/the-nature-conservancy-fisheries-monitoring/kernels)

In this competition, The Nature Conservancy asks you to help them detect which species of fish appears on a fishing boat, based on images captured from boat cameras of various angles.  

**Your goal is to predict the likelihood of fish species in each picture.**

Eight target categories are available in this dataset: Albacore tuna, Bigeye tuna, Yellowfin tuna, Mahi Mahi, Opah, Sharks, Other (meaning that there are fish present but not in the above categories), and No Fish (meaning that no fish is in the picture). **Each image has only one fish category,** except that there are sometimes very small fish in the pictures that are used as bait.

![species](https://kaggle2.blob.core.windows.net/competitions/kaggle/5568/media/species-ref-key.jpg)

**File descriptions**
+ **train.zip** - zipped folder of all train images. The train folders are organized by fish species labels.
+ **test_stg1.zip** - zipped folder of all test images in stage 1.
+ **test_stg2.zip** - zipped folder of all test images in stage 2 (not available until the second stage of the competition).
+ **sample_submission_stg1.csv** - a sample submission file in the correct format.
+ **sample_submission_stg2.csv** - a sample submission file in the correct format (not available until the second stage of the competition).

### Evaluation

Submissions are evaluated using the [multi-class logarithmic loss](https://www.kaggle.com/wiki/MultiClassLogLoss). Each image has been labeled with one true class. For each image, you must submit a set of predicted probabilities (one for every image). The submitted probabilities for a given image are not required to sum to one because they are rescaled prior to being scored (each row is divided by the row sum). In order to avoid the extremes of the log function, predicted probabilities are replaced with `max(min(p,1-10^{-15}),10^{-15})`.

### Submission

You must submit a csv file with the image file name, and a probability for each class.

The 8 classes to predict are: 'ALB', 'BET', 'DOL', 'LAG', 'NoF', 'OTHER', 'SHARK', 'YFT'.

The order of the rows does not matter. The file must have a header and should look like the following:

	image,ALB,BET,DOL,LAG,NoF,OTHER,SHARK,YFT
	img_00001.jpg,1,0,0,0,0,...,0
	img_00002.jpg,0.3,0.1,0.6,0,...,0
	...
