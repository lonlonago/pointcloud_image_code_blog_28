#  First, the principle of the algorithm 

##  1. Overview of the principle 

 ConditionalRemoval: Conditional Filter ConditionalRemoval filters data that meets a specific condition. You can delete all data points that meet one or more conditional metrics set for the input point cloud at once, and delete data points in the point cloud that do not meet one or more conditions specified by the user. The user must provide conditions for ConditionalRemoval. 

##  2. References 

>  [1] doc: Removing outliers using a Conditional [2] The PCL class pcl :: Conditional Remov a l implements this algorithm

There are two types of conditions:

ConditionAnd ——pcl::ConditionAnd ConditionOr——pcl::ConditionOr 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574272335
  ```  
#  III. Display of results 

 ![avatar]( 20210207101741311.png) 

>  The number of reading points is: 61603 points Before removing null, the number of points after conditional filtering: 61603 points After removing null, the number of points after conditional filtering: 19282 points 

