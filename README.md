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



--------------------------------------------------------------------------------

 + 1. Basic graphics 1, arrow 2, ball 3, circle 4, cube 5, ring 6, cone 7, straight line 8, plane 9, polygon

#  First, the basic graphics 

##   1. Arrow 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  
 ![avatar]( 2021020123101588.png) 

##   2. The ball 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  
 ![avatar]( 20210201231134179.png) 

##   3. Circle 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  
 ![avatar]( 2021020123153819.png) 

##  4. Cube 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  
 ![avatar]( 2021020123170082.png) 

##  5. Circle 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  
 ![avatar]( 20210201231751947.png) 

##  6. Cone 

 ![avatar]( 20210201231845289.png) 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  
##  7. Straight line 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  
 ![avatar]( 20210201231939853.png) 

##  8. Plane 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  
 ![avatar]( 20210201232039944.png) 

##  9. Polygons 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  
 ![avatar]( 2021020207155272.png) 

#  II. Complete code 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574150381
  ```  


--------------------------------------------------------------------------------

 + 1. Header files in common modules 

 + 二、基本函数  1、angles.h2、centriod.h3、common.h4、distance.h5、copy_point.h6、geometry.h

   pcl_common library contains common data structures and methods used by most PCL libraries. The core data structures include the PointCloud class and many point types used to represent points, surface normals, RGB color values, feature descriptors, and more. In addition, it also contains calculation functions such as distance/norm, mean and covariance, angle transformation, geometric transformation, etc. This module is independent of other modules and can be compiled independently. 

#  Header files in common modules 

 Angles. H defines the angle calculation function of the standard C interface. Centriod.h defines the estimation of the center point and the calculation of the covariance matrix. The standard C and C++ classes of common.h are the parent classes of other common functions. Distance. H defines the standard C interface for calculating distances. copy_point. H has a simple copy function file_io. H defines some functions to help write or read files. Random .h defines some functions generated by random point clouds. H defines some basic geometric functions. Functions intersection.h defines functions where lines intersect. H defines the standard C method to calculate the regularization of matrices. Time.h defines functions for time calculation Point_types. H defines the types of data structures for all PCL implementations of point clouds 

#  Second, the basic function 

##  1、angles.h 

 Degrees and radians (angles and radians) 

 radian rotation angle 

 overload method 

>  To use this function, you need to add: #include < pcl/common/common_headers > header file or #include < pcl/common/angules.h > header file 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Angle curvature 

 overload method 

>  To use this function, add: #include < pcl/common/common_headers > header file 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Normalize the angle to between (-PI, PI), overloaded 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: 

##  2、centriod.h 

>  To use this function, add:/#include < pcl/common/transforms.h > or #include < pcl/common/centroid.h > header file 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL computing point cloud centroid 

>  To use this function, add: #include < pcl/common/centroid.h > header file 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL computing point cloud covariance matrix 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
>  To use this function, add: #include < pcl/common/centroid.h > header file 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: Normalized covariance matrix and three-dimensional centroid for PCL computing point cloud 

>  To use this function, add: #include < pcl/common/centroid.h > header file 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
  Application example: PCL point cloud centroid removal 

   The "mean" here represents not only the average of the 3D point coordinates, but also the average of the values in other data fields. The generic computeNDCentroid () function also implements this functionality, but it does so in an "unintelligent" way, that is, it simply averages the values regardless of the semantics of the data within the field. In some cases (e.g., for x, y, z, intensity fields), this behavior is reasonable, but in others (e.g., rgb, rgba, rgbl (labeled with labels)), it does not lead to meaningful results. This class is able to calculate the mean in an "intelligent" way, i.e., taking into account the meaning of the data within the field. The following fields are currently supported: 

 Application example: PCL calculates the mean value of data in each field of point cloud 

##  3、common.h 

>  To use this function, add the #include < pcl/common/common.h > header file 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
>  Note: The angle is expressed in radians and angle values. False means that the calculation result is expressed in radians, and the value range is [0, PI); true means that the calculation result is expressed in angles, and the value range is [0, 180 °). 

 Application example: PCL calculates the angle of point cloud normal vector 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL calculates the mean and standard deviation of point clouds 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL randomly selects a point and calculates the point farthest from it 

>  To use this function, add: #include < pcl/common/common.h > header file 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL computing point cloud optimization 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL calculates the radius of the circumscribed circle 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: 

##  4、distance.h 

   There are five functions in the distance header file, including lineToLineSegment, sqrPointToLineDistance, getMaxSegment, squaredEuclideanDistance, and euclideanDistance. 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL calculates the distance of a straight line with different planes 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL calculates the distance from a point to a straight line in 3D space 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL computing point cloud maximum distance 

##  5、copy_point.h 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL reading and saving point clouds 

##  6、geometry.h 

 Gets the minimum and maximum values on the point histogram. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Assign field data from Point_in to Point_out 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Determining the minimum eigenvalue and its corresponding eigenvector is not easy to use, not as good as Eigen, and will calculate incorrectly. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Determining the Eigenvector Corresponding to the Given Eigenvalue of Symmetric Positive Semidefinite Input Matrix 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Determining Eigenvector and Eigenvalue of Minimum Eigenvalue of Symmetric Positive Semidefinite Input Matrix 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Compute the inverse of a 2x2 matrix. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Compute the inverse of a 3x3 symmetric matrix. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Calculating the determinant of a 3x3 matrix 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 To get a unique 3D rotation, rotate the Z axis to (0, 0, 1) and the Y axis to (0, 1, 0) and the two axes are orthogonal. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Get the transformation that converts origin to (0, 0, 0) and rotates the Z axis into (0, 0, 1) and the Y direction (0, 1, 0). 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
>  The input is the transformation matrix, and the output is: roll barrel roll angle, pitch angle, yaw angle 

 ![avatar]( 20210204111556538.gif) 

  overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL extracts Euler angle from transformation matrix 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL extracts Euler angle and translation vector from given transformation matrix 

 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL creates a transformation matrix from a given translation and Euler angle 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Gets two 3D lines in space as the intersection of 3D points. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Get the index of the specified field (i.e. dimension/channel) 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL reading and saving point clouds 

 Gets the size (in bytes) of a specific field data type. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 overload method 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574110170
  ```  
 Application example: PCL point cloud merger (data or field connection in two point clouds) The above functions have a variety of overloading methods. Only the function name is shown here. In VS, use ctrl + the left mouse button to select the function name to view all the overloading methods of the function. 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview of the principle 

   See: PCL calculates point cloud normal vector and displays 

##  2. Main functions 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574273829
  ```  
#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574273829
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574273829
  ```  
 ![avatar]( 7f9c64f94ed44fbcb2f631b474ff38af.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Algorithm overview 

     The PCL :: MomentOfInertiaEstimation class is used to obtain descriptors based on moment of inertia and eccentricity. Another function of this class is to extract the directed bounding box OBB and the axis-aligned bounding box AABB. The directed bounding box OBB extracted here is not necessarily the smallest bounding box. The bounding box mentioned here is often referred to as collision detection used in physical simulation or visualization. 

##  2. Theoretical basis 

 Theoretical basis, first calculate the covariance matrix of the point cloud, then extract the eigenvalues and normalized eigenvectors. Taking the center of gravity of the point cloud as the coordinate origin, taking the main eigenvector as the X-axis and the minimum eigenvector as the Y-axis, construct a local coordinate system that conforms to the principle of the right-hand coordinate system. Then an iterative calculation is carried out, and in each iteration, the main eigenvector is rotated. The rotation order is always the same, and is executed around other eigenvectors, which provides the invariance of the point cloud rotation. The main vector of this rotation is called the current axis. The moment of inertia for each current axis is calculated. In addition, the eccentricity calculation is also performed using the current axis. Therefore, the current vector is regarded as the normal vector of the plane, and the input cloud is projected onto On this basis, the eccentricity of the projection is calculated. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574162720
  ```  
#  III. Display of results 

 ![avatar]( 20200706202006871.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Algorithm flow 

 CropHull is a filter that defines a two-dimensional graph and then clips the point cloud located within the graph. 

##  2. Function analysis 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574196199
  ```  
 empty constructor 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574196199
  ```  
 Set the vertices of the polygonal shell for filtering the points by entering polygons, which are vectors of ordered vertices of the polygonal shell. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574196199
  ```  
 Gets the vertices of the filtered polygon shell. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574196199
  ```  
 Sets the point cloud points corresponding to the shell index. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574196199
  ```  
 Get the point cloud pointer points corresponding to the shell index. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574196199
  ```  
 Sets the dimension to be used by the shell to correspond to the dimensions of polygonal shells produced by pcl ::  Convex Hull and pcl :: Concave Hull classes. The parameter dim is the dimension of the convex polygon used for point cloud filtering (value 2 or 3). 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574196199
  ```  
 Set whether to remove points outside the shell or inside, parameter crop_outside If set to true, the filter will filter out points outside the polygon, and if set to false, it will filter out points inside the polygon. The default value of the parameter is true. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574196199
  ```  
#  III. Display of results 

 ![avatar]( 20200625193139705.png) 

 From left to right are the original point cloud, the closed 2D polygon convex hull result, and the CropHull filtering result  



--------------------------------------------------------------------------------

 + 1. Mouse event 1. Button name 2. Event type 3. Callback function 4. Function function

 + 2. Keyboard events 1. Callback functions 2. Function functions

 + 3. Event registration 1. Mouse registration 2. Keyboard registration 3. Registration example

 + 4. Example code 

 + 5. Display of results 

#  Mouse events 

 pcl::visualization::MouseEvent Class Reference 

##  1. Button name 

##  2. Event type 

##  3. Callback function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294933
  ```  
>  Type event type button The button that triggers the event x The x position of the mouse pointer when the event is triggered y The y position of the mouse pointer when the event is triggered alt Whether the ALT key is pressed when the event is triggered ctrl Whether the CTRL key is pressed when the event is triggered shift Whether the Shift key is pressed when the event is triggered selection_mode whether it is in selection mode 

##  4. Functional functions 

>  setButton () Sets the button that caused the event setType () Sets the mouse event type getButton () The button that caused the action getKeyboardModifiers () Returns the keyboard modifier state when the event was triggered getSelectionMode () The state of the selection mode getType () The mouse event type getX () The x-coordinate position of the mouse pointer when the event is triggered getY () The y-coordinate position of the mouse pointer when the event is triggered 

#  Keyboard events 

 pcl::visualization::KeyboardEvent Class Reference 

##  1. Callback function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294933
  ```  
>  Action true indicates that the key is pressed, false indicates that the key name key_sym the key that causes the operation is released, whether the ALT key ctrl is pressed when the event is triggered, whether the CTRL key shift is pressed when the event is triggered, and whether the Shift key is pressed when the event is triggered 

##  2. Functional functions 

>  getKeyCode () The ASCII code of the key that generated the event. If it is 0, then it is a special key like ALT, F1, F2,... PgUp, etc. Then the key name is in the keysym field. getKeySym () The name of the key that caused the event isAltPressed () Whether the alt key isCtrlPressed () Whether the ctrl key isShiftPressed () Whether the shift key was pressed when this event was triggered keyDown () True if the key caused the event, otherwise falsekeyUp () True if releasing the key caused the event, otherwise false 

#  III. Event registration 

##  1. Mouse registration 

 registerMouseCallback () Mode 1: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294933
  ```  
>  Callback The user data passed to the callback function by the function cookie that will be registered as a mouse event callback 

 Method two: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294933
  ```  
>  Callback passes the member function instance instance registered as a mouse event callback to the class that implements the callback function cookie passes the user data to the callback function 

##  2. Keyboard registration 

 registerKeyboardCallback () Mode 1: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294933
  ```  
 Method two: 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294933
  ```  
##  3. Registration example 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294933
  ```  
>  Register the response keyboard and mouse events respectively, keyboardEventOccurred mouseEventOccurred callback function, the second parameter is the so-called cookies, which is the parameter passed to the callback function when the callback is called. You can pass any parameter to the callback function. When passing the window object itself as an argument to the callback function, you need to cast the boost :: shared_ptr to void *. 

#  IV. Sample code 

>  In this example code, a small text label is generated every time the left mouse button is clicked. Pressing the R key will delete the text label generated by the mouse, and the position of the 3D camera will also be reset. Therefore, the event response callback function registered in the PCL window will not overwrite the response of other members to the same event. 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574294933
  ```  
#  V. Display of results 

 ![avatar]( 20210222112740501.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Algorithm overview 

   If a point has more than one point within a certain distance threshold area, it is considered to have duplicate points. 

##  2. Main functions 

 [1] PCL KD树的使用 [2] c++中的std::set，是基于红黑树的平衡二叉树的数据结构实现的一种容器，其中所包含的元素的值是唯一的，可以用于去重。 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574156759
  ```  
#  III. Display of results 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574156759
  ```  
 ![avatar]( f111b17882be42e6b46e9ef4603c8c76.png) 



--------------------------------------------------------------------------------

#  First, the principle of the algorithm 

##  1. Overview of the principle 

   The ears of a simple polygon refer to a triangle composed of consecutive vertices, and (in this order) adjacent to each other. In computer geometry terms, the connection between and is called the diagonal of the polygon (this should be displayed in the editor to better see the triangle division), and the point is called the ear tip (the same is true for finding the ear tip). Although you can place the ear tip on any vertex of the triangle, we think that the triangle contains an ear tip. A multi-deformation composed of four vertices (or more) has at least two non-overlapping ear tips. This feature provides a way to recursively solve triangulation segmentation. For a polygon composed of fixed points, find its ear tip and remove the vertices on the unique ear tip. At this time, the remaining vertices form a simple polygon with vertices. We repeat this operation until there are three remaining vertices. This will produce an algorithm of great complexity. 

##  2. Main functions 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574253197
  ```  
#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574253197
  ```  
#  III. Display of results 

 ![avatar]( de03b72e810540f597ce76f470c91621.png) 



--------------------------------------------------------------------------------

#  Introduction to the algorithm 

   PCL :: registration :: CorrespondenceRejectorDistance, based on the distance between the set threshold correspondence relationship to achieve a simple error correspondence removal. 

  The core part of the ICP algorithm is based on this 

##  1. Main function 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957412923
  ```  
>  The algorithm also has two other parameters, namely: setInputCloud and setInputTarget, which literally means that the source and target point clouds of the input are set, and the input data must contain XYZ information. If setInputCloud and setInputTarget are given, then the distance between the corresponding relationships will be estimated using the given XYZ data, rather than being read from the corresponding relationship of the input. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957412923
  ```  
#  III. Display of results 

 Initial correspondence, correspondence based on distance rejection reservation  



--------------------------------------------------------------------------------

#  I. References 

>  [1] doc: Estimating VFH signatures for a set of points [2] PCL: pcl :: VFH Estim a tion [3] Ma Zhijun, Yang Junyou, Sun Yizhen. Research on object recognition based on multi-feature fusion [J]. Science and Technology and Innovation, 2021 (16): 33-35. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574191463
  ```  
#  III. Display of results 

 ![avatar]( 2020070617191427.png) 



--------------------------------------------------------------------------------

#  Point cloud transformation 

   Generally speaking, the rigid body transformation of two pieces of point cloud data is mainly divided into translation transformation and rotation transformation, without scaling transformation and distortion deformation. The purpose of rigid body transformation is to determine the transformation relationship of rotation translation between two pieces of point cloud data, and to unify the point cloud data into the same coordinate system. Therefore, rigid body transformation can be described as solving the transformation matrix of different coordinate systems. The point cloud data obtained by the three-dimensional scanning device, under the premise of not distorting the shape and size of the object, moves in the direction, which is expressed as translation transformation, as shown in Figure 1. If a translation transformation matrix representing point cloud data is used, that is, the transformation formula of the matrix located between different coordinate systems is: 

 ![avatar]( 20210516203628756.png) 

    Among them, the order is the three-dimensional point cloud data translation along the axis.  

   As shown in FIG. 2, the point cloud data acquired by the three-dimensional scanning device is rotated by an angle about the x-axis, the y-axis, and the z-axis in turn, which is expressed as a rotation transformation. 

 ![avatar]( 20210516204926218.png) 

    This refers to the rotation angle of the 3D point cloud data around the x-axis, y-axis, and z-axis in turn.  

##  1. Rotation matrix 

 The rotation matrix composed of rotation around the x-axis is: The rotation matrix composed of rotation around the y-axis is: The rotation matrix composed of rotation around the z-axis is: 

##  2. Euclidean transformation 

 The Euclidean transformation does not change the shape and size of the space object, but only the pose. The 3-latitude Euclidean transformation has 6 degrees of freedom (3 rotations and 3 translations), as follows: Written in the form of a transformation matrix, the Euclidean transformation requires the rotation matrix to be an orthogonal matrix. 

##  3. The meaning of the transformation matrix 

 ![avatar]( 2021020521363056.png) 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957422783
  ```  
#  III. Display of results 

 ![avatar]( 20210205200636928.png) 



--------------------------------------------------------------------------------

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



--------------------------------------------------------------------------------

##  First, the principle of the algorithm 

>  Necessary comments have been made in the code to define the method reference of the index: PCL index extractor, point cloud extraction using PCL index 

##  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 2024020309574176398
  ```  
##  III. Display of results 

>  From left to right, the original data, extract a plane, extract a second plane, and the remaining data 

 ![avatar]( 20200625161809932.png) 



--------------------------------------------------------------------------------

#  First, the algorithm description 

##  1. Function analysis 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957428411
  ```  
>  Correspondences: input corresponding point pair set indices: output corresponding point pair set corresponding to the index of setInputTarget () input point cloud 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957428411
  ```  
>  Correspondences: input corresponding point pair set indices: output corresponding point pair set corresponding to the index of setInputSource () input point cloud 

 ![avatar]( 2021030807502483.png) 

  The target point cloud, from the figure, you can intuitively see the non-overlapping parts of the two point clouds. The following code implements extracting the non-overlapping parts. 

#  Code implementation 

  ```python  
After clicking on the GitHub Sponsor button above, you will obtain access permissions to my private code repository ( https://github.com/slowlon/my_code_bar ) to view this blog code. By searching the code number of this blog, you can find the code you need, code number is: 202402030957428411
  ```  
#  III. Display of results 

 ![avatar]( 2021030807562620.png) 



--------------------------------------------------------------------------------

