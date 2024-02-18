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

