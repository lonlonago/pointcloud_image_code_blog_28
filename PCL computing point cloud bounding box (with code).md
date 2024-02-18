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

