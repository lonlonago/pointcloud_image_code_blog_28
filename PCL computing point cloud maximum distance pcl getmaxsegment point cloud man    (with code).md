#  First, the principle of the algorithm 

##  1. Overview 

   Calculating the maximum distance between points in the same point cloud is an important step to estimate the overlap degree in the 4PCS registration algorithm, and is the basis for realizing handwritten 4PCS and improving it. 

##  2. Main functions 

    PCL :: get Max Segment () takes the maximum distance in a given point cloud set and returns the minimum and maximum coordinate points. It is different from pcl :: get MinMax 3D () in common, because the distance from the minimum point to the maximum point is not necessarily the maximum distance. This function has two overloading methods, the second one has one more indices than the first, and mainly selects the point with the largest distance in the indices, rather than in the entire point cloud. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574226871
  ```  
#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574226871
  ```  
#  III. Display of results 

 ![avatar]( 54f8f42c27594e5bb451b84d2182e463.png) 

