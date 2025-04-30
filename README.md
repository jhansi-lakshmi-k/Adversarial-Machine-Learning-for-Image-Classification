# Adversarial-Machine-Learning-for-Image-Classification

In the file R11896217_cs5331_ass1_fa24.py we have performed untargeted attacks (non-target white-box attacks)
This task aims to implement the following attacks: Fast Gradient Sign Method (FGSM), Projected Gradient Descent (PGD), Deep Fool, and C&W with L2 norm. 
with these attacks Adversarial classification accuracy is calculated wiht the base model being VGG-16.
and then performed Targetted attack with Fast Gradient Sign Method (FGSM), Projected Gradient Descent (PGD), and C&W with L2 norm

in the file cs5331_hw2_fa24.py 
implements randomized smoothing to certify the model.have used σ^2=[ 0.25,0.5,1] as Gaussian noise parameter. 
later Label-only privacy attack has been performed - it focuses on Membership inference attacks.
the label-only attack is developed based on the fact that it costs an attacker so much to generate a successful adversarial sample for a member sample. In contrast, the cost will be much less for a non-member sample. Thus, it uses HopSkipJump to generate a successful adversarial sample and then measure the perturbation using the L2 norm. 

With the query limit as 5 the overall accuracy was 65%, indicating moderate success rate in differentiating between member and non-member samples, upon increasing the value to 10 has slightly improved the overall accuracy to 65.8% showing that more queries allow for slightly better membership inference.
Also, the accuracy difference between member samples is higher than that of the nonmember samples, this reflects the fast that the model is better at identifying members but is struggling with classifying nonmembers.
Increasing the queries slightly improves accuracy but doesn’t make much bigger difference. The threshold here helped in maximizing the attacks’ ability to correctly classify the samples, but this also depends on the perturbation distribution between member and non-member samples.

Later Shadow Models attacks  has been done.

based on the DP attack few observations has been made 
There is the privacy accuracy tradeoff, due to which the added noise to the gradients during the training limits the model’s ability to learn specific details about the individual samples. This limitation helps against the membership inference attack, but the model’s overall performance is reduced. Thus, protecting privacy but it has costed the models performance. Due to which dp has a lower accuracy compared to the original VGG model.  
Though the vgg model has the high accuracy it is highly vulnerable to membership inference attack. The noise and the gradient have reduced the overfitting of training data in the DP, which is good for privacy. From the results, we can say that the original model has achieved higher accuracy for both members and nonmembers indicating that the model has learned data distribution well and generalizes effectively on unseen samples.   
The high accuracy differences between the members and non-members means that the original model is more vulnerable to membership inference attacks, and this is because the model might have retained specific information about its training samples.    
The DP has lower accuracy across, this reduction is reflecting the trade-off made for privacy. The close values for members and nonmembers indicate that the do model doesn’t differentiate between the members and the non-members. This shows a reduced vulnerability to the membership inference attack.


