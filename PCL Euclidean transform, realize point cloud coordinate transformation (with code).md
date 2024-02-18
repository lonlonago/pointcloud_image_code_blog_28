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

