# LicensePlateDetction


![alt text](https://github.com/[Pranav418]/[LicensePlateDetection]/blob/[main]/detections/detection1.png?raw=true)


inside the recognise_plate function
  (line 73 in utils.py)
  text = pytesseract.image_to_string(roi, config='-c tessedit_char_whitelist=0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ --psm 8 --oem 3')

  We use google tesseract to perform the text extraction. tessedit_char_whitelist argument are the characters we are looking for. --psm 8 flag implies that we want to treat the     whole image as a single word.

The draw_bbox function is where we actually draw the bounding boxes around the characters

Vehicle License Plate Detection using Google Tesseract and YOLOv4 
