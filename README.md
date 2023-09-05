# face_recognition_and_attendance_tracking
Python script for face recognition and attendance tracking using the face_recognition library, OpenCV, and Pandas. 
Here's a breakdown of what the code does:
1. Import necessary libraries: The script imports the required libraries, including face_recognition, numpy, cv2 (OpenCV), pandas, and datetime.
2. Load known face image and encoding: The script loads a known face image (in this case, "yashika.jpg") and encodes it using the face_recognition library. The encoding is stored in the variable `known_face_encoding`.
3. Initialize attendance dictionary: An attendance dictionary is initialized with the names of known faces as keys, and initially set to `False` for attendance.
4. Open a video capture: It opens the default camera (webcam) for capturing video frames.
5. Main loop: The script enters a main loop that captures video frames from the webcam and processes them for face recognition.
              a. Face detection: It detects faces in the captured frames using `fr.face_locations()`.
              b. Face encoding: The faces are encoded using `fr.face_encodings()`.
              c. Face matching: It compares the encodings of detected faces with the known face encoding to determine if there is a match.
              d. Attendance tracking: If a match is found, the script updates the attendance dictionary with the corresponding name set to `True`. It also draws a rectangle around the detected face and labels it 
                                      with the name.
              e. Display the frame: The processed frame with face detection and labels is displayed.
              f. Break the loop: The loop can be exited by pressing the 'q' key.
6. Attendance recording: After the main loop, the script records attendance by creating a list of attendance records for each person who was detected (marked as present) along with a timestamp. This data is stored in a Pandas DataFrame.
7. Export attendance data: The attendance data is exported to an Excel file named "attendance.xlsx" using Pandas.
8. Release resources: The webcam capture is released, and OpenCV windows are closed.

This script essentially performs real-time face recognition and keeps track of attendance for the known person(s) in front of the camera. The attendance records are then saved to an Excel file for further analysis or record-keeping. Make sure you have the required libraries installed and that the known face image is provided before running the script. Additionally, you can adjust the known_face_names and known_face_encodings to match the individuals you want to recognize.
