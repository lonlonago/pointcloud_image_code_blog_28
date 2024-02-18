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

