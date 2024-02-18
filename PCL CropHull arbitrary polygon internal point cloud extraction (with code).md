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

