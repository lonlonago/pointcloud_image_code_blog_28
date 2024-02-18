#  First, the principle of the algorithm 

##  1. Algorithm source code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574218232
  ```  
##  2. Special reminder 

>  PCL has two kinds of curvature calculation call function: 1.pcl :: PrincipalCurvaturesEstimation, that is, the method used in this article 2.pcl :: Normal Estimation, the specific use of the details see: PCL point cloud normal vector and display 3. About the main curvature of the main direction, PCL main curvature calculation method, known from the source code, only calculate the direction of a main curvature; if you want to find the main direction of two main curvature, then there is no need to waste time in the PCL call function, you can only modify the source code to achieve!!! (In other words, the main direction is determined to be two?) 4. If you want to write your own specific implementation code, you can refer to the source code or: use the normal vector of adjacent points to estimate the main curvature of a point 

##  3. Curvature display 

>  Currently addPointCloudPrincipalCurvatures only accept pcl :: Point XYZ and pcl :: Normal two parameters, can not display curvature information. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574218232
  ```  
>  Excellent blog recommendation: PCL to obtain the curvature of each point of the 3D point cloud model 

#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574218232
  ```  
 ![avatar]( 6570bbf995594f3fb12fb4f3cc8453a8.png) 

