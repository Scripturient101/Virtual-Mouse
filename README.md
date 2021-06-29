# Virtual-Mouse
This project presents a simple and effective method for hand gesture recognition. The hand region is detected using MediaPipe library. The movement of index finger is traced to move the cursor and the clicking motion is performed by bringing index finger and middle finger together

# Libraries used:
1. MediaPipe
2. OpenCV
3. Numpy
4. AutoPy (Not supported by python 3.9 and up)


***Guide for the HAnd Tracking Module: 

# Steps to capture a video:
  •	Use cv2.VideoCapture() to get a video capture object for the camera.
  •	Set up an infinite while loop and use the read() method to read the frames using the above created object.
  •	Use cv2.imshow() method to show the frames in the video.
  •	Breaks the loop when the user clicks a specific key.

  ![image](https://user-images.githubusercontent.com/81686454/123776082-947c7d00-d8ec-11eb-930f-67869a117feb.png)

# Steps to detect the hand:
  •	Create an object from the class hand 
  •	To get the point/landmarks, create a module that will detect hand point 5, and return location.
  static_image_mode – when set to false: track (when confidence level is high) and detect (when confidence level is low) 

  ![image](https://user-images.githubusercontent.com/81686454/123776243-bd047700-d8ec-11eb-8eda-23e78cd62409.png)

# Change webcam image:
  Send RGB image to the Hand object, in the loop.
  ![image](https://user-images.githubusercontent.com/81686454/123776395-e02f2680-d8ec-11eb-8bfc-3d8f9f7e2939.png)

# To check the no of hands detected
  ![image](https://user-images.githubusercontent.com/81686454/123776460-f0470600-d8ec-11eb-9eae-c725911d3a96.png)
  
# Steps to draw handLandmarks on the image display:
  •	Using an if with results.multi_hand_landmarks and a for loop with handLandmarks combination. handLandmarks contains the landmarks for one of the hands (there are two by    default).
  •	Use a “built-in” method to draw the points (and lines between the associated points (i.e. knuckles), which make it easier to use, else a lot of maths would be required.
  
  ![image](https://user-images.githubusercontent.com/81686454/123776642-1c628700-d8ed-11eb-886d-2b1ebed8c52a.png)
  
# Steps to calculate live FPS: 
  •	For calculating FPS, we will be keeping the record of the time when last frame processed and the end time when current frame processed. So, the processing time for one frame     will be time difference between current time and previous frame time.
  
    ![image](https://user-images.githubusercontent.com/81686454/123776764-3734fb80-d8ed-11eb-9543-adae877c6336.png)
    
    So, fps at the current moment will be: 
    
    ![image](https://user-images.githubusercontent.com/81686454/123776828-46b44480-d8ed-11eb-9a82-a63605f498e1.png)
    
  •	Since FPS will be always Integer, we will be converting FPS to integer and after that typecasting it to string because it will be easy and faster to display the string           using cv2.putText() on frame. Now with the help cv2.putText() method we will be printing the FPS on this frame.
  
    ![image](https://user-images.githubusercontent.com/81686454/123776988-69def400-d8ed-11eb-96f1-f994e517ddff.png)
      
# Steps to extract and use the values of points:
  •	Landmark gives (x,y). We have ID numbers already listed in correct order, to check the index number and get each ID of each landmark. Use enumerate to get the ID of the landmarks.
  •	x and y are not in pixels, but in ratio – so to convert in pixels it needs to be multiplied by the width and the height respectively.
  •	Print out each id along with the (x,y)
  
    ![image](https://user-images.githubusercontent.com/81686454/123777190-9135c100-d8ed-11eb-93e0-b614bcd9916e.png)




    









