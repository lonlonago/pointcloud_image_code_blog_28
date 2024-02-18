#  First, the principle of the algorithm 

##  1. Algorithm flow 

 CropBox is a filter that allows users to filter all the data within a given box. 

>  The algorithm is also integrated in CloudCompare software, so the code implementation and operations in CloudCompare software are given. 

 ![avatar]( 20201230110128972.gif) 

 Related implementation operations in CloudCompare software  

##  2. Function analysis 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 constructor 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Sets the minimum value of the given cube coordinates min_ _pt. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Gets the minimum value of the user-set cube coordinates. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Sets the maximum value ax_pt for the given cube coordinates. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Gets the maximum value of the user-set cube coordinates. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Set the cube translation vector translation to the amount of translation of the cube in three directions. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Gets the amount of translation of the cube. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Set the cube rotation transformation through the input vector, and the rotation is the rotation amount of the cube. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Gets the amount of rotation entered. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Set the cube affine transformation matrix transform, which is an affine transformation applied to the point cloud before filtering. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Get the user-set cube affine transformation matrix transform. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Sets whether the final output point cloud is a filtered point or a reserved point. The parameter negative defaults to false, that is, the points that need to be culled by the filter algorithm design are culled. If set to true, the points that need to be preserved by the filter algorithm design are culled. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Obtain the Boolean value of whether the final output point cloud returns the filtered out or reserved points. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Sets whether to maintain the structure of the filtered point cloud, if set keep_organized to true, keep the points that need to be culled and assign the value set by setUserFilterValue (default: NaN), if set to false, delete the filtered points in the output point cloud, thereby changing its organizational structure. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Gets a Boolean value for whether to maintain the structure of the filtered point cloud. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
 Provide a value that filtered points should be set to, rather than deleting them, in conjunction with setKeepOrganized 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957413058
  ```  
#  III. Display of results 

 ![avatar]( b302b30a73eb4c3a92cd4decf2e6eda4.png) 

