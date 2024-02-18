 + 1. Algorithm principle 1. Implementation process 2. Implementation method 3. Core code 4. References

 + 2. Code implementation 

 + 3. Results display 

 + 4. Application cases 

 + 5. Save the result 

#  First, the principle of the algorithm 

##  1. Implementation process 

 ![avatar]( 20210516100352615.png) 

   Euclidean clustering is a clustering algorithm based on Euclidean distance metric, and the nearest neighbor query algorithm based on KD-Tree is an important preprocessing method to accelerate Euclidean clustering algorithm.

   For Euclidean clustering, the distance criterion is the Euclidean distance mentioned above. For a point P in space, the k points closest to the p point are found through the KD-Tree nearest neighbor search algorithm, and those points whose distance is less than the set threshold are clustered into the set Q. If the number of elements in Q does not increase, the whole clustering process ends; otherwise, the points other than the p point must be selected in the set Q, and the above process must be repeated until the number of elements in Q does not increase. Euclidean clustering is more suitable for point cloud clustering and segmentation without connectivity. Therefore, for real-life large-field scenic spot clouds, it is usually necessary to use progressive morphological filtering, simple morphological filtering (SMRF) algorithm or CSF fabric simulation algorithm to filter out ground points. 

##  2. Implementation method 

 The specific implementation method (the principle is to agglomerate a point cloud into a class): 

##  3. Core code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574277569
  ```  
#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574277569
  ```  
#  III. Display of results 

>  Note: The visualization results here are only given flat and non-flat. The specific blocks can be opened with visual tools in the folder. 

 ![avatar]( 20200725192736109.png) 

#  IV. Application cases 

   For the large-scale scenic spot cloud filtered out of the ground, the segmentation and classification of independent ground features are carried out and the segmentation results are saved to the local folder. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574277569
  ```  
#  V. Save the results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574277569
  ```  
 ![avatar]( 91e73c7ab9624308bca9a486be89356f.png) 

