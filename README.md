# Hypothesis_Testing
Using R studio, we will perform a paired t-test of two means of sample populations. By comparing the means of the datasets, we are searching for the equality of means of the 2 samples with unknown variances, to see if the sets of data are somehow related.  In this exercise, we will test the effectiveness of a new training method used by a new athletic trainer at a school. This scenario shows 10 runners, before and after training results, with two different new coaches using the same population every time. We will be testing to see if there are variances between the 2 new coaches by comparing their means before and after training. 
## Step 1
To begin, we will input 2 sets of paired samples. We are looking to verify if there is any change of the means under new training coaches. 	
We begin with this data:
- Before training (a_training): 12.9, 13.5, 12.8, 15.6, 17.2, 19.2, 12.6, 15.3, 14.4, 11.3
- After training (b_training): 12.7, 13.6, 12.0, 15.2, 16.8, 20.0, 12.0, 15.9, 16.0, 11.1
We enter these commands:
- > a_training = c(12.9, 13.5, 12.8, 15.6, 17.2, 19.2, 12.6, 15.3, 14.4, 11.3) 
- > b_training = c(12.7, 13.6, 12.0, 15.2, 16.8, 20.0, 12.0, 15.9, 16.0, 11.1)
To output the paired t-test and to see if p-value is > than 0.05, to see significance, we enter:
 - > t.test(a_training, b_training, paired=TRUE)
 We see p-value > 0.05, therefore the new training did not make a significant improvement.
 Next, to calculate the t-tabulated value, we use 0.975 as the 97.5 percentile pt of a normal distribution and has a StdDev of about 1.96. Degrees of freedom is 9.
 We see an output of 2.262157, where t-computer > t-tabulated, so therefore we accept the null hypothesis.
 ## Step 2
We will input before and after results from another coach. For the initial results we will use the training population. The after results training population will show the results of the new coach. 
Here is the before and after data used:
- Before training (a_training): 12.9, 13.5, 12.8, 15.6, 17.2, 19.2, 12.6, 15.3, 14.4, 11.3 
- After the second training (b_training): 12.0, 12.2, 11.2, 13.0, 15.0, 15.8, 12.2, 13.4, 12.9, 11.0	
To look for an alternative hypo, and look for a p-value > 0.05, and see if there is results from the new training, we enter commands:
- > a_training = c(12.9, 13.5, 12.8, 15.6, 17.2, 19.2, 12.6, 15.3, 14.4, 11.3) 
- > b_training = c(12.0, 12.2, 11.2, 13.0, 15.0, 15.8, 12.2, 13.4, 12.9, 11.0) 
- > t.test(a_training, b_training, paired=TRUE, alt="less") # alt="less" is added to indicate that R needs to test the alternative hypo Looking at our results, the p-value is higher than 0.05, therefore we can reject the null hypo in favor of the alternative hypo – thus there is improvement in the new training.
#### Conclusion:
We see p-value is >0.05, therefore  it is showing improvement in the new training methods used by the new coach while comparing means of the 2 sample sets.

## Paired t-test 3 Dataset exercise:
Introduction:
We will test the new effects of a drug for blood pressure of the same 12 people. The first trial will determine if the blood pressure in drug XYZ has effects on the groups blood pressure. The second trial will test the same 12 people, and will be given drug ABC and we will see if it has a change in effect on their blood pressure. 
This is the dataset we will be using:

To begin, we will compare blood pressure to XYZ drug, we enter commands:
- > a_training = c(155,142,145,160,149,152,157,159,166,163,158,161)
- > b_training = c(152,142,144,159,150,153,156,160,165,162,159,160)
- > t.test(a_training, b_training, paired=TRUE)
command to conduct the t-test between the two samples. Results show that the p-value is greater than 0.05, therefore there are no changes in blood pressure using drug XYZ.
We see p-value>0.05, therefore no change in blood pressure in XYZ.
Next, we will compare blood pressure to ABC drug, we enter commands:
- > a_training = c(155,	142,	145,	160,	149,	152,	157,	159,	166,	163,	158,	161)
- > b_training = c(150,	135,	142,	153,	142,	147,	152,	149,	158,	155,	150,	150)
- > t.test(a_training, b_training, paired=TRUE, alt="less") # alt="less" is added to indicate that R needs to test the alternative hypo Looking at our results, the p-value is higher than 0.05, therefore we can reject the null hypo in favor of the alternative hypo
#### We reject null hypo, and accept that there is change in blood pressure using drug ABC.
#### Conclusion:
We notice that there is greater changes in means of blood pressure of the 12 patients using drug ABC. Drug XYZ has less effect on the patients blood pressure. 
