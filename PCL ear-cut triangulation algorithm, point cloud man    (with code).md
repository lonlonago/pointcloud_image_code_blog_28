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

