#  First, the principle of the algorithm 

##  1. Overview of the principle 

   The algorithm is based on the same strategy as the region growth algorithm. Compared with the region growth algorithm, the algorithm has two main differences: First, the algorithm replaces the normal with color, removing the upper limit of the point cloud size. It can be considered that the same color and close to each other are very likely to be a class, and no upper limit is required to limit it. Therefore, this method is more suitable for indoor scene segmentation, especially complex indoor scenes. Color segmentation can easily turn continuous scene point clouds into different objects. Even if the uneven ground cannot be removed by a uniform sampling splitter, the color segmentation algorithm can also complete the segmentation task. Second, use the merging algorithm to control over-segmentation or under-segmentation. During the segmentation process, if the average color difference between two adjacent clusters is small, the two clusters are merged. Then a second step of merging is performed. In this step, the number of points contained in each cluster is checked. If this number is less than the user-defined value, the current cluster is merged with its neighboring cluster. 

##  2. Algorithm steps 

 (1) Segmentation, if the color difference between the current seed point and the field point is less than the color difference threshold, it will be regarded as a cluster; (2) Merging, if the color difference between the clusters is less than the color difference threshold and is a cluster, and if the number of points in the current cluster is less than the number of cluster points, it will be merged with the nearest cluster. 

##  3. References 

>  Color-based region growing segmentationpcl::RegionGrowingRGB 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574169242
  ```  
#  III. Display of results 

##  1. Data 1 

 ![avatar]( 723fec93e66947df90af7cf31592d8c3.png) 

##  2. Data 2 

 ![avatar]( dc3c2511f2c24347b162df9e1ae7e6bc.png) 

