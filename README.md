# Agtuary Machine Learning Technical Challenge


The purpose of this challenge is to test your ability in working with satellite imagery, imbalanced datasets and machine learning models.


## Problem


You must implement a machine learning model to perform crop classification, and determine what crop types are grown where in an image of farm paddocks (also known as one-shot in-season crop classification). 

Sentinel-2 is a satellite that captures 12 different wavelengths of light (also known as bands) in an image. These range from visible light (red, green, blue) to infra-red. The values for each band changes depending upon the material/object that is on the ground. 

## The Task

1. Download the dataset at: https://agtuary-data-public.s3.ap-southeast-2.amazonaws.com/machine-learning-challenge/agtuary-ml.gz

2. Prepare the data for training and testing. The `pixels.csv` file has 14 columns, and each row is a different pixel from satellite imagery. The first 12 columns are the different bands `B01..B12`, then the `cloud_prob` column which is the probability that the pixel of satellite imagery is cloud (ranges from `0. to 100.`), and finally the `label` column which is the ground-truth crop type.

    The band values go from `0. to 1.` Remove any pixels that have a cloud probability of over 2. Split the dataset into a train and test set as you feel is appropriate. Encode the crop type labels into a numeric value.

3. Create a plot showing the mean band values of each crop type, as well as +- 2 standard deviations.

4. Create/use a machine learning model of your choice to perform multiclass classification, and train it on the band values you just prepared.

5. Inside the dataset, there are also satellite imagery band files from a test region in Australia (`B01.tif to B12.tif`). These image files are in `uint16` data type and have values that go from `0 to 10000`, which must be rescaled to fit the training data range. There is also a cropland mask file (`mask.png`), which is `int8` data type and the values go from `0 to 255`. A value greater than `0` represents pixels of the band files where you will use your model and perform inference on the band values.

6. Plot a confusion matrix and print a classification report of your model. Plot/print any other interesting metrics you may have (optional).

7. From your inference results, create an image which contains purple pixels where the result was `Other`, red pixels where the result was `Sorghum` and white pixels where the result was `Cotton`. Save it as a PNG file.


## Evaluation


Explain your approach inside your code (write it as a comment block or notebook cell). Some of the following questions are good places to start:

How would you improve the model? Are there any specific areas in the satellite imagery where you see the model not performing as well as other areas? Are there farm paddocks where there is a lot of noise in the output (e.g. lots of mixed crop type pixels). Are there any other features you could use as inputs? Could you use the different band values to engineer new features/inputs (such as the difference between particular bands)? What machine learning model or type would best suit this problem?


## Submission

Save your notebook/code as well as output images into a `.zip` file and send it to matthew@agtuary.com


