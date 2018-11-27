Be careful with the order of OpenCV initialization. Wrong order may lead to parameters not taken into account (see [this](https://stackoverflow.com/questions/16092802/capturing-1080p-at-30fps-from-logitech-c920-with-opencv-2-4-3 "") thread).

This how to initialize OpenCV capture with Python on a Windows platform:
```
camera_number = 0
cap = cv2.VideoCapture(camera_number + cv2.CAP_DSHOW)
cap.set(cv2.CAP_PROP_FOURCC, cv2.VideoWriter_fourcc(*"MJPG"))
cap.set(cv2.CAP_PROP_FPS, 30)
cap.set(cv2.CAP_PROP_FRAME_WIDTH, 1920)
cap.set(cv2.CAP_PROP_FRAME_HEIGHT, 1080)
```