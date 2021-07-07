# Vehicle License Plate Detection using Google Tesseract and YOLOv4 

Main working methodology

1. Input the image in RGB format as a numpy array
2. Run the object localization to detect position of number plate and draw bounding box around it
3. Crop Detected License plate region and pre-process the image, by gray scaling, enlarging, thresholding, dilation
4. Find contours and segment to obtain individual characters
5. Run Tesseract Script to detect the characters
6. Display License Plate (check if License plate is in a given database stored in the form of strings)

![Alt text](detections/detection1.png?raw=true "Title")

Yolov4 algorithm detects the position of the license plate with great speed and accuracy. The Tesseract OCR is slightly slower


inside the recognise_plate function
  (line 73 in utils.py)
  
  text = pytesseract.image_to_string(roi, config='-c tessedit_char_whitelist=0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ --psm 8 --oem 3')

  We use google tesseract to perform the text extraction. tessedit_char_whitelist argument are the characters we are looking for. --psm 8 flag implies that we want to treat the     whole image as a single word.

yolov4.py is where the license plate's position is detected


