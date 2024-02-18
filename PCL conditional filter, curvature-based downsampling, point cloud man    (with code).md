#  First, the principle of the algorithm 

##  1. Overview of the principle 

 ConditionalRemoval: Conditional Filter ConditionalRemoval filters data that meets specific conditions. You can delete all data points that meet one or more conditional metrics set for the input point cloud at a time, and delete data points in the point cloud that do not meet one or more conditions specified by the user. The user must provide conditions for ConditionalRemoval. This article provides an implementation method based on curvature conditions. 

##  2. References 

>  [1] doc: Removing outliers using a Conditional [2] The PCL class pcl :: Conditional Remov a l implements this algorithm

There are two types of conditions:

ConditionAnd ——pcl::ConditionAnd ConditionOr——pcl::ConditionOr 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574292625
  ```  
#  III. Display of results 

 ![avatar]( 5ac5de6decb24720ae518bde9baf7bb4.png) 

