**Exploratory Testing on Mobile Web Demo App**  
 

**Tester:** Viktor Kokeza  
 **Date:** August 7, 2025 / August 14, 2025 

**Description:** This QA report documents exploratory testing conducted for the Mobile Web Demo App with a primary focus on negative test case scenarios. The testing covered three main functional areas: 

1. **ID Capture & Validation**  
2. **Face Capture & Liveness Detection**  
3. **Face Recognition & Matching**

The testing process was performed using an Android device, and results were reviewed in the Demo Dashboard. This report includes a list of all executed test cases, the documented results of negative scenarios, identified bugs  and inconsistencies, and suggestions for potential improvements.

**Device Used:** Samsung Galaxy S22 Ultra (Android 15), Chrome Browser (138.0.7204.180)   
 

**Test Environment:** (The link has been omitted due to NDA restrictions.)

**Demo Dashboard:** (The link has been omitted due to NDA restrictions.)

### 

###  **1\. List of All Tests Performed**

#### **A. ID Capture & Validation**

* Uploading a valid ID (e.g. passport, driver’s license, ID).  
* Upload a non-identification document (e.g., gift card, business card, or loyalty card).  
* Uploading a blurred photo of ID.  
* Uploading cropped photo or part of ID.  
* Uploading an ID with glare.  
* Upload a completely blank image.  
* Test cancellation during the image upload process by refreshing the page.  
* Uploading an expired ID.  
* Uploading someone else's document.  
* Test taking a picture of the document sideways.  
* Uploading a document with shaking hands.  
* Take a photo of the front of the document twice instead of capturing both front and back.  
* Take a picture of a document from far away.

#### **B. Face Capture & Liveness Detection**

* Face scan in good lighting.  
* Face scan with poor lighting.  
* Face scan with face partially out of frame.  
* Using a printed photo of a face.  
* Using a video of a face  
* Test under extreme brightness  
* Perform sudden head movements   
* Test with eyes closed  
* Making no movements when prompted for liveness.  
* Test cancelling the upload of a selfie photo (refresh page)

#### 

#### 

#### **C. Face Recognition & Matching**

* Matching the same face as ID.  
* Test face scan while the user is wearing a mask.  
* Test face scan while the user is wearing glasses.  
* Test face scan while the user is wearing a hat.  
* Matching a different person’s face.  
* Test system response with similar-looking faces( using AI to change the face).  
* Test cancelling matching process(refresh page).

### 

### 

### 

### 

### **2\. Documented Negative Test Case Scenarios and Results**

#### **Test Case\_A01:** Upload a non-identification document (e.g., gift card, business card, or loyalty card).

**Test Case Session ID**: 689518d0670e0308db2ec6b9, 68951ba900fc517994dc3d7e

**Description**: This negative test case evaluates the system’s ability to identify and reject non-identification documents, such as gift cards, business cards, or loyalty cards, when submitted in place of a valid form of identification. The objective is to verify that the system correctly detects invalid documents and prevents them from progressing in the verification workflow. Additionally, this test ensures that the application remains stable, with no unexpected errors, crashes, or abnormal behaviors occurring as a result of such invalid inputs.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has a non-official government document, such as a gift card, business card, or loyalty card, to use for the ID capture step.  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license,ID"**.  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Position the document and wait until the shutter (circle) button appears, then capture an image of a gift card instead of a valid ID. (You can also use business cards or loyalty cards.)  
7. Click **"Continue"**. The system should detect the invalid document and present an option to "try again."  
8. Click **"Try again"**.  
9. Repeat steps 6, 7 and 8 two more times, attempting to submit the gift card image. The system should continue to reject the invalid document.   
10. After two attempts there should be a title displayed:”ID scan failed”, then click the “**Continue”** button.  
11. After the failed attempts, the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
12. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
13. Take a selfie. The process should then proceed to the "matching" stage.  
14. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
User is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test: PASSED**

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### **Test Case\_A02:** Uploading a blurred photo of ID

**Test Case Session ID: 68974bc67c4c578f169dce04**  
**Description:** This negative test case validates the system's ability to reject images of official identification that fail to meet minimum quality standards for clarity and focus. The user is instructed to intentionally take and upload a blurred image of a valid government-issued ID to verify that the application correctly detects the poor quality and rejects the upload. Additionally, this test ensures that the application remains stable, with no unexpected errors, crashes, or abnormal behaviors occurring as a result of such invalid inputs.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to have an official document, such as an ID, driver's license, passport to use for the ID capture step.  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"ID, Driver's license"**  
4. On the "Place your ID" page, click the **"Continue"** button.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Wait until the shutter (circle) button appears and **intentionally take a blurred image of the front of a valid ID document.**  
7. Click **"Continue"**. The system should detect if the image is blurred and present an option to "try again."  
8. The user clicks **"Try again"**.  
9. Repeat steps 6, 7 and 8 two more times, attempting to submit the blurred image. The system should continue to reject the blurred image of ID.  
10. After the failed attempts, the system may proceed to capture the back of the ID. On the "**Ready to scan**" page, click **"Continue"**.  
11. Wait until the shutter (circle) button appears and **intentionally take a blurred image of the back of a valid ID document.**  
12. Click **"Continue"**. The system should detect if the image is blurred and present an option to "try again."  
13. The user clicks **"Try again"**.  
14. Repeat steps 11, 12 and 13 two more times, attempting to submit the blurred image. The system should continue to reject the blurred image of ID.  
15.  After two more attempts there should be a title displayed:”ID scan failed”, then click “**Continue”** button  
16. After the failed attempts, the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
17. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
18. Take a selfie. The process should then proceed to the "matching" stage.  
19. After the matching process fails, click **"Continue"** to complete the test case

**Expected Result:**  
Matching  fails and user is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test:** Pass

**Note:**  
One bug was identified during testing, if the user rotates their phone from vertical (portrait) to horizontal (landscape) orientation while the camera is loading image, the application incorrectly prompts for camera access again. After granting the access, this action unexpectedly redirects the user to the first page of the process, interrupting the workflow and potentially causing user confusion.

 

#### **Test Case\_A03:** Uploading photo of cropped ID

**Test Case Session ID**:68976f50ef2f996231fd5f7b

**Description:** This negative test case evaluates the system's ability to handle the upload of a cropped or incomplete image of an ID document. The user is instructed to intentionally take and upload a photo where a portion of the ID (e.g., a corner, the top, or the bottom) is cut off or missing from the frame. This test aims to verify that the application correctly detects the incomplete document, rejects the image, and prompts the user to retake the photo, ensuring the entire ID is visible and in focus. Additionally, this test ensures that the application remains stable, with no unexpected errors, crashes, or abnormal behaviors occurring as a result of such invalid inputs.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to have an official document, such as an ID, driver's license, passport to use for the ID capture step.  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"ID, Driver's license"** button  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. **Wait until the shutter (circle) button is displayed,  intentionally cover the front half of the ID with paper** and capture the image.  
7. Click **"Continue"**. The system should detect the invalid document and present an option to "try again."  
8. Click **"Try again"**.  
9. Repeat steps 6, 7 and 8 two more times, attempting to submit the image. The system should continue to reject the image. After two more attempts there should be a title displayed:”ID scan failed”, then click "Continue" button  
10. **Wait until the shutter (circle) button is displayed, intentionally cover the back half of the ID with paper** and capture the image.  
11. Click **"Continue"**. The system should detect the invalid document and present an option to "try again."  
12. Click **"Try again"**.  
13. Repeat steps 10, 11 and 12 two more times, attempting to submit the image. The system should continue to reject the image.  
14. After the 2 failed attempts, the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
15. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
16. Take a selfie. The process should then proceed to the "matching" stage.  
17. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
Match fails and user is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test: PASSED**

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_A04: Uploading photo of an ID with glare.

**Test Case Session ID**:689779b6593aafebaa155bc2

**Description:** This negative test case evaluates the system's ability to detect and reject images of identification documents where critical information (e.g., name, photo, document number) is obscured by glare or excessive light. The user is instructed to intentionally create and submit a photo with a bright reflection on the ID's surface to verify that the application's validation process correctly identifies the quality issue and prevents the user from proceeding. Additionally, this test ensures that the application remains stable, with no unexpected errors, crashes, or abnormal behaviors occurring as a result of such invalid inputs.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to have an official document, such as an ID, driver's license, passport to use for the ID capture step.  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have a flashlight or good sunlight

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"ID, Driver's license"** button  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. **Wait until the shutter (circle) button is displayed, intentionally cover the front half of the ID with light** and capture the image.  
7. Click **"Continue"**. The system should detect the invalid document and present an option to "try again."  
8. Click **"Try again"**.  
9. Repeat steps 6, 7 and 8 two more times, attempting to submit the image. The system should continue to reject the image. After two more attempts there should be a title displayed:”ID scan failed”, then click "Continue" button  
10. **Wait until the shutter (circle) button is displayed, intentionally cover the back half of the ID with light** and capture the image.  
11. Click **"Continue"**. The system should detect the invalid document and present an option to "try again."  
12. Click **"Try again"**.  
13. Repeat steps 10, 11 and 12 two more times, attempting to submit the image. The system should continue to reject the image.  
14. After the 2 failed attempts, the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
15. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
16. Take a selfie. The process should then proceed to the "matching" stage.  
17. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
Match fails and user is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test: PASSED**

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

####  Test Case\_A05: Upload completely blank image

**Test Case Session ID**: 6895243a51b2ca45305ea0ff

**Description:** This negative test case evaluates the system's ability to handle the upload of a completely blank or unreadable image. The user is instructed to intentionally take and upload a blank image to verify that the application's validation process correctly identifies that no document is present and rejects the submission. The test aims to confirm that the system prevents the user from proceeding with a useless image and prompts them to provide a valid photo of their ID. Additionally, this test ensures that the application remains stable, with no unexpected errors, crashes, or abnormal behaviors occurring as a result of such invalid inputs.

**Preconditions:**

* The user has a smartphone (Android or iOS) with an active internet connection  
* The user needs to grant the browser permission to access the device's camera.

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Passport"** button  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Intentionally capture a picture of the wall .  
7. Click **"Continue"**. The system should detect the invalid document and present an option to "try again."  
8. Click **"Try again"**.  
9. Repeat steps 6, 7 and 8 two more times, attempting to submit the image. The system should continue to reject the image. After two more attempts there should be a title displayed:”ID scan failed”, then click "Continue" button  
10. After the failed attempts, the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
11. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
12. Take a selfie. The process should then proceed to the "matching" stage.  
13. After the matching process fails , click **"Continue"** to complete the test case.

**Expected Result:**  
User is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test: PASSED**

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### 

#### Test Case\_A06: Test cancellation during the image upload process by refreshing the page

#### 

**Test Case Session ID**:68977dc400fc517994e0b269

**Description:** This negative test case evaluates the system's ability to handle an interruption during the ID document upload process. The user begins the upload of a valid ID image and, while the upload is still in progress, performs a disruptive action like refreshing the browser page. The test aims to determine if the application correctly handles this interruption by either restarting the process from the beginning, saving the progress, or displaying an appropriate error message without crashing.

**Preconditions:**

* The user has a smartphone (Android or iOS) with an active internet connection  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have an official document, such as an ID, driver's license, passport to use for the ID capture step.  
* The user need to have a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. While the picture is being uploaded, refresh the page  
8. A prompt requesting camera permission is displayed. Click **"Allow"** to proceed and complete the test case.

**Expected Result:**  
The user is navigated back to Click the "Ready to scan" button or is navigated to the first page of Test Environment

**Actual Result:**

User is navigated back to the first page of  Test environment

**Status of Test:** FAILED

**Note:**  
There is bug, application crashes while testing and user is navigated back to the first page of  Test environment

#### Test Case\_A07: Uploading an expired document

#### 

**Test Case Session ID**: 6897bc8d894cc6fb6937844e

**Description:** This negative test case evaluates the system's ability to recognize and reject an official identification document that has expired. The user is instructed to upload an image of a valid government-issued ID (e.g., driver's license, passport) that has passed its expiration date. This test aims to verify that the application's document validation process correctly flags the document as invalid and prevents the user from proceeding with the verification process.

**Preconditions:**

* The user has a smartphone (Android or iOS) with an active internet connection  
* The user needs to grant the browser permission to access the device's camera.  
* The user has an official expired document, such as an ID, driver's license, passport to use for the ID capture step.

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Passport"**  
4. On the "Align your passport " page, click **"Continue"**.  
5. Scan passport  
6. After scanning the passport , the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
7. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
8. Take a selfie. The process should then proceed to the "matching" stage.  
9. After the matching process, click **"Continue"** to complete the test case.

**Expected Result:**

Matching fails and the user is navigated to the “Verification complete” page

**Actual Result:**  
Matching passes and user is navigated to the “Verification complete” page

**Status of Test: FAILED**

**Note:**  
No application crashes or functional bugs were encountered during testing. However, one unhandled validation error was observed: the system did not detect that an uploaded document had expired. An example of this issue is provided in the attachment below.

**Attachment:** 

![][image1]

#### Test Case\_A08:Uploading someone else's document

**Test Case Session ID:6898a8b700fc517994e14b55**

**Description:**This negative test case evaluates the system's ability to handle the upload of a valid official ID document belonging to a person other than the user performing the verification. The user is instructed to use a legitimate ID document that is not their own during the ID capture step. This test aims to verify that the application's facial recognition and matching technology correctly identifies the mismatch between the ID photo and the live selfie, and subsequently rejects the verification attempt. Additionally, this test ensures that the application remains stable, with no unexpected errors, crashes, or abnormal behaviors occurring as a result of such invalid inputs.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document from person who is not user(ID, passport, ect)  
* The user needs to grant the browser permission to access the device's camera.

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Passport"**.  
4. On the "Place your Passport" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan Passport that does not belong to the user.  
7. After that, the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
8. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
9. Take a selfie. The process should then proceed to the "matching" stage.  
10. After the failed  matching process, click **"Continue"** to complete the test case.

**Expected Result:**  
 Matching fails and the user is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

Status of Test: PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing, 

#### Test Case\_A09: Test taking a picture of the document sideways

**Test Case Session ID: 689b3c353d4c39c387728572**  
**Description:** This negative test case evaluates the system's ability to detect and reject images of identification documents that are not in the standard, correct orientation. The user is instructed to intentionally take and upload an image of a valid ID that is rotated 90 degrees or otherwise improperly oriented to verify that the application correctly identifies the issue and prompts the user to retake the photo in the correct orientation.Additionally, this test ensures that the application remains stable, with no unexpected errors, crashes, or abnormal behaviors occurring as a result of such invalid inputs.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to have an official document, such as an ID, driver's license, passport to use for the ID capture step.  
* The user needs to grant the browser permission to access the device's camera.  
* A good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"ID, Driver's license"**  
4. On the "Place your ID" page, click the **"Continue"** button.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Wait until the shutter (circle) button appears and **Intentionally take an image of the front of a valid ID document sideways(**rotated 90 degrees**).**  
7. Click **"Continue"**. The system should detect if the image is displayed sideways and present an option to "try again."  
8. The user clicks **"Try again"**.  
9. Repeat steps 6, 7 and 8 two more times, attempting to submit the blurred image. The system should continue to reject the blurred image of ID.  
10. After the failed attempts, the system may proceed to capture the back of the ID. On the "**Ready to scan**" page, click **"Continue"**.  
11. Wait until the shutter (circle) button appears and **Intentionally take an image of the back of a valid ID document sideways(**rotated 90 degrees **).**  
12. Click **"Continue"**. The system should detect if the image is blurred and present an option to "try again."  
13. The user clicks **"Try again"**.  
14. Repeat steps 11, 12 and 13 two more times, attempting to submit the blurred image. The system should continue to reject the image of ID.  
15.  After two more attempts there should be a title displayed:”ID scan failed”, then click “**Continue”** button  
16. After the failed attempts, the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
17. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
18. Take a selfie. The process should then proceed to the "matching" stage.  
19. After the matching process fails, click **"Continue"** to complete the test case

**Expected Result:**  
The system should detect that the ID image is improperly oriented and reject the upload. A clear error message should be displayed, and the user  is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected result:

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_A10: Uploading a document with shaking hands

**Test Case Session ID: 689b4b3794faf85b0f475072**

**Description:** This negative test case evaluates the system's ability to handle the capture of an ID document when the user's hands are shaking, resulting in a slightly blurry or unsteady image. The user is instructed to intentionally shake their hands while taking a photo of a valid, official ID document. This test aims to verify that the application's image validation correctly detects the motion blur or unsteadiness, rejects the image, and prompts the user to take a clearer, more stable photo.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to have an official document, such as an ID, driver's license, passport to use for the ID capture step.  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"ID, Driver's license"**  
4. On the "Place your ID" page, click the **"Continue"** button.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. **Intentionally take an image of the front of a valid ID document while hands are shaking.**  
7. Click **"Continue"**. The system should detect if the image is displayed sideways and present an option to "try again."  
8. The user clicks **"Try again"**.  
9. Repeat steps 6, 7 and 8 two more times, attempting to submit the blurred image. The system should continue to reject the blurred image of ID.  
10. The system may proceed to capture the back of the ID. On the "**Ready to scan**" page, click **"Continue"**.  
11. Wait until the shutter (circle) button appears and **intentionally take an image of the back of a valid ID document while hands are shaking.**  
12. Click **"Continue"**. The system should detect if the image is displayed sideways and present an option to "try again."  
13. The user clicks **"Try again"**.  
14. Repeat steps 11, 12 and 13 two more times, attempting to submit the blurred image. The system should continue to reject the blurred image of ID.  
15. The system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
16. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
17. Take a selfie. The process should then proceed to the "matching" stage.  
18. After the matching process fails, click **"Continue"** to complete the test case

**Expected Result:**  
The system should detect that the ID image is blurry and reject the upload. A clear error message should be displayed, and the user  is navigated to the “Verification complete” page

**Actual Result:**  
Same as expected result

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_A11: Take photo of front documentation twice instead one picture of front and back of document

**Test Case Session ID: 689b4d2fc4eeedc31038ab54**

**Description:** This negative test case evaluates the system's ability to handle a user submitting two identical photos of the front of a document, instead of one photo of the front and one of the back. This test aims to verify that the application correctly detects this improper submission, rejects the images, and prompts the user to submit new photos for each side of the document.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to have an official document, such as an ID, driver's license, passport to use for the ID capture step.  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"ID, Driver's license"**  
4. On the "Place your ID" page, click the **"Continue"** button.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. **Take an image of the front of a valid ID document**   
7. The system may proceed to capture the back of the ID. On the "**Ready to scan**" page, click **"Continue"**.  
8. **Take an image of the front of a valid ID document** again  
9. Click **"Continue"**. The system should detect that the user submitted an image of the front **document** and present an option to "try again."  
10. The user clicks **"Try again"**. button  
11. Repeat steps 8, 9 and 10 two more times, The system should continue to reject the front image of ID.  
12. After the failed attempts, the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
13. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
14. Take a selfie. The process should then proceed to the "matching" stage.  
15. After the matching process is done (due to the blurred image upload), click **"Continue"** to complete the test case

**Expected Result:**  
The system should detect that the user submitted two identical images and reject the upload. A clear error message should be displayed, and the user  is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected result

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_A12: Take a picture of ID document from far away

**Test Case Session ID: 689b4d2fc4eeedc31038ab54**

**Description:**This negative test case evaluates the system's ability to handle the capture of an ID document from a significant distance, resulting in a small, low-resolution image where details are hard to read. The user is instructed to intentionally take a picture of a valid, official ID document from a far distance. This test aims to verify that the application's image validation correctly detects the low resolution and lack of detail, rejects the image, and prompts the user to take a closer photo

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to have an official document, such as an ID, driver's license, passport to use for the ID capture step.  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"ID, Driver's license"**  
4. On the "Place your ID" page, click the **"Continue"** button.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. wait until the shutter (circle) button appears and **Intentionally take an image of the front of a valid ID document. from far away**  
7. Click **"Continue"**. The system should detect if the image is blurred and present an option to "try again."  
8. The user clicks **"Try again"**.  
9. Repeat steps 6, 7 and 8 two more times, attempting to submit the blurred image. The system should continue to reject the blurred image of ID.  
10. After the failed attempts, the system may proceed to capture the back of the ID. On the "**Ready to scan**" page, click **"Continue"**.  
11. Wait until the shutter (circle) button appears and **intentionally take an image of the back of a valid ID document.**  
12. Click **"Continue"**. The system should detect if the image is blurred and present an option to "try again."  
13. The user clicks **"Try again"**.  
14. Repeat steps 11, 12 and 13 two more times, attempting to submit the blurred image. The system should continue to reject the image of ID. After two more attempts there should be a title displayed:”ID scan failed”, then click “**Continue”** button  
15. After the failed attempts, the system may proceed to capture the back of the ID. On the "**Ready to scan**" page, click **"Continue"**.  
16. After the failed attempts, the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
17. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
18. Take a selfie. The process should then proceed to the "matching" stage.  
19. After the matching process fails, click **"Continue"** to complete the test case

**Expected Result:**  
The matching process has failed and the user  is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected result

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### 

#### Test Case\_B13: Face scan with poor lighting.

**Test Case Session ID: 689cae99a9c06c19a42ca7f0**

**Description:**This negative test case evaluates the system's ability to handle face capture under poor lighting conditions. The user is instructed to position their face in an area with low or uneven lighting, which may cast shadows or make facial features difficult to discern. The test aims to verify that the application correctly detects the poor lighting and prompts the user to move to a better-lit area for a proper capture.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to be in a dark room or dark environment

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.   
10. Take a selfie in a dark room.  
11.  The process should fail and the user will be asked two more times,then press the “**Continue”** button.  
12. Repeat step 10 and 11 two times  
13. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
 Matching  fails and user is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_B14: Face scan with face partially out of frame

**Test Case Session ID: 68985e1e8223a1185cbc3cd3**

**Description:** This negative test case evaluates the system's ability to handle face capture when the user's face is not completely within the designated frame. The user is instructed to intentionally position their face so that a portion of it (e.g., the chin, ear, or forehead) is outside the boundaries of the on-screen guide. The test aims to verify that the application correctly detects the incomplete face and prompts the user to reposition it for a proper capture.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.   
10. Take a selfie with your face partially out of frame.  
11.  The process should fail because the face is not aligned with the dotted outlines and the user will be asked two more times,then press the “**Continue”** button.  
12. Repeat step 10 and 11 two times  
13. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
Matching has failed and  user is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_B15: Using a printed photo of a face

**Test Case Session ID: 689866648274769bfbe97983**

**Description:** This negative test case evaluates the system's ability to detect and reject a printed photograph of a user's face during the liveness detection. This test aims to verify that the application's liveness detection technology correctly identifies the fraudulent attempt and prevents the user from proceeding with the verification.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user has a printed photo of their own face

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Take a selfie with your printed photo of a face.  
10. The process should fail because the face is not aligned with the dotted outlines and the user will be asked two more times,then press the “**Continue”** button.  
11. Repeat step 9 and 10 two times  
12. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
User has failed matching process and User is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_B16: Testing the selfie capturing process by using a video of a user's face 

**Test Case Session ID: 68986aa3894cc6fb6937db35**

**Description:** This negative test case evaluates the system's ability to detect and reject a digital video of a user's face during the liveness detection or selfie capture process. This test aims to verify that the application's liveness detection technology correctly identifies the fraudulent attempt and prevents the user from proceeding with the verification.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have video of their face that lasts 30 seconds  
* The user needs to have second monitor (phone, laptop, tablet, etc.) to display video

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Take a selfie with a video of a user's face.  
10.  The process should fail because the face is not aligned with the dotted outlines and the user will be asked two more times,then press the “**Continue”** button.  
11. Repeat step 9 and 10 two times  
12. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
Matching process has failed and user is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_B17: Testing the selfie capturing process in extreme brightness

**Test Case Session ID:68986d1e670e0308db3643ad**

**Description:** This negative test case evaluates the system's ability to handle face capture under conditions of extreme brightness. The user is instructed to position their face directly facing a strong light source (e.g., direct sunlight or a bright lamp) to intentionally overexpose the image. The test aims to verify that the application correctly detects the overexposed conditions, prevents the user from capturing a selfie, and prompts them to move to a location with more suitable lighting for a proper capture.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have a strong light (sunlight or a bright lamp)

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.   
10. Take a selfie with a strong light source  
11.  The process should  fail and the user will be asked two more times,then press the “**Continue”** button.  
12. Repeat step 10 and 11 two more times  
13. After the matching process, click **"Continue"** to complete the test case.

**Expected Result:**  
Matching process has failed and user is navigated to the “Verification complete” page

**Actual Result:**  
The system successfully captured the user’s face even in extreme lighting conditions, passed the matching process, and navigated the user to the "Verification Complete" page.

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_B18: Test face scan while user perform sudden head movements

#### 

**Test Case Session ID: 689a545151b2ca453065c819**

**Description:** 

This negative test case evaluates the system's ability to handle face capture when the user makes sudden, unexpected head movements. The user is instructed to perform a quick head movement, such as a sharp turn or a rapid tilt, while the camera is in the process of capturing a face scan. This test aims to verify that the application correctly detects the motion, prevents a successful capture, and prompts the user to remain still for a proper scan.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user has a good light source.

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.   
10. Take a selfie while performing sudden head movements  
11.  The process should fail because the face is not aligned with the dotted outlines and the user will be asked two more times,then press the “**Continue”** button.  
12. Repeat step 10 and 11 two times  
13. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
Matching  failed because the user's photo of the face was too blurry  and the user was navigated to the “Verification complete” page.

**Actual Result:**  
Same as Expected Result

**Status of Test:** PASSED

 

**Note:**  
There were no bugs, application crashes or unhandled errors while testing.

#### Test Case\_B19: Test face scan with eyes closed

**Test Case Session ID: 6898a4b000fc517994e147f7**

**Description:** 

This negative test case evaluates the system’s ability to handle face capture when the user keeps their eyes closed during the scanning process. The user is instructed to close their eyes entirely while the camera attempts to capture the face scan. The purpose of this test is to verify that the application correctly detects closed eyes, prevents a successful capture, and prompts the user to open their eyes to ensure a proper and accurate scan.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user has a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.   
10. Take a selfie with eyes closed  
11.  The process should fail and the user will be asked two more times,then press the “**Continue”** button.  
12. Repeat step 10 and 11 two times  
13. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
The user has failed the matching process because eyes were closed  and  is navigated to the “Verification complete” page.

**Actual Result:**  
Same as Expected Result

 **Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### 

#### Test Case\_B20: Test face scan by making no movements when prompted for liveness. 

#### 

**Test Case Session ID: 6898b59c51b2ca453063fcf2**

**Description:** This negative test case evaluates the system's ability to detect a lack of movement during the liveness detection phase. The user is instructed to remain completely still and not perform any of the requested actions (e.g., blinking, turning the head) when prompted by the application. This test aims to verify that the system correctly identifies the absence of a live person's actions and rejects the attempt, preventing the user from proceeding with the verification process.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have a good light source.

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.   
10. Take a selfie with no movements when prompted for liveness.  
11.  The process should fail because the face is not aligned with the dotted outlines and the user will be asked two more times,then press the “**Continue”** button.  
12. Repeat step 10 and 11 two more times  
13. After the matching process, click **"Continue"** to complete the test case.

**Expected Result:**  
The user has failed the matching process and  is navigated to the “Verification complete” page.

**Actual Result:**  
Same as Result

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### 

#### Test Case\_B21: Cancelling upload of selfie photo (refresh page)

**Test Case Session ID: 689a6ab0262e5eae490b427b**

**Description**:This negative test case verifies the app's behavior when the user cancels the selfie photo upload by refreshing the page during the face capture step. The objective is to ensure that refreshing the page cancels the upload process appropriately and the app handles this interruption gracefully, without causing errors or unexpected behavior.

**Preconditions**:

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user has granted the browser permission to access the device's camera  
* The user has a good light source.

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
10. The user takes a picture  
11. While the system is loading the photo, user refreshes the page 

**Expected Result:**

The selfie capture/upload process is cancelled due to page refresh and the user is navigated to the first page of the Test Environment. 

**Actual Result:**  
Same as Expected Result

**Status of Test:** PASSED

**Notes:**  
There were no bugs, application crashes or unhandled errors while testing

#### 

#### Test Case\_C22: Test face scan while user is wearing mask 

**Test Case Session ID: 6898775a262e5eae490886fd**

**Description:** This negative test case evaluates the system’s ability to detect and handle situations where a user attempts to perform a face scan while wearing a mask that partially or fully covers the face. The objective is to verify that the facial recognition and liveness detection mechanisms fail to authenticate a masked face, as masks obscure critical facial features required for accurate identification. The system should recognize the mask as an obstruction, reject the scan, and display an appropriate error message instructing the user to remove the mask and use a fully visible, live face for successful scanning. 

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to have an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have face mask  
* The user needs to have a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Take a selfie with a mask on  
10.  The process should fail because the face is not aligned with the dotted outlines and the user will be asked two more times,then press the “**Continue”** button.  
11. Repeat step 9 and 10 two times  
12. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
User has failed matching process because they were wearing mask and user is navigated to the “Verification complete”page 

**Actual Result:**  
Same as Expected Result

**Status of Test:** PASSED

**Note:**There were no bugs, application crashes or unhandled errors while testing

#### 

#### Test Case\_C23: Test face scan while user is wearing glasses

**Test Case Session ID:68987b99a61a28e986c32d00**

**Description:** This negative test case evaluates the system's ability to handle face capture and recognition when the user is wearing glasses. The user is instructed to perform the face scan while wearing prescription glasses or sunglasses. This test aims to verify whether the application correctly detects the presence of glasses and either rejects the capture, prompts the user to remove them, or successfully performs the recognition and liveness detection.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have prescription  glasses or sunglasses  
* The user needs to have a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing any hats and positioning your face in the camera frame.   
10. Take a selfie with glasses on  
11.  The process should fail and the user will be asked two more times,then press the “**Continue”** button.  
12. Repeat step 10 and 11 two times  
13. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
User has failed matching process because they were wearing glasses and  is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result

**Status of Test:** PASSED

**Note:**

There were no bugs, application crashes or unhandled errors while testing

#### 

#### Test Case\_C24: Test face scan while the  user is wearing hat

**Test Case Session ID: 68987cbe7c4c578f169f06e4**

**Description:** 

This negative test case evaluates the system's ability to handle face capture when the user is wearing a hat or other head covering. The user is instructed to wear a hat that partially obscures their forehead and hair. This test aims to verify that the application correctly detects the obstruction and prompts the user to remove the hat for a proper facial capture, preventing them from proceeding with the verification process.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have hat(e.g. American cap)  
* The user needs to have a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing glasses and positioning your face in the camera frame.   
10. Take a selfie with a hat on  
11.  The process should fail because the face is not aligned with the dotted outlines and the user will be asked two more times,then press the “**Continue”** button.  
12. Repeat step 10 and 11 two times  
13. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
User has failed matching process because he is wearing hat and  is navigated to the  “Verification complete”page

**Actual Result:**  
Same as Expected Result

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_C25: Matching with a different person's face

**Test Case Session ID: 6898acba985dc1789c8d4647**

**Description:** 

This negative test case evaluates the system's ability to accurately detect a mismatch when the face captured during the live selfie process is different from the face on the provided ID document. The test aims to confirm that the face recognition and matching algorithms correctly identify that the two individuals are not the same and prevent the user from proceeding with a successful verification.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have another person for face scanning  
* The user needs to have a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.   
10. Take a selfie with some else face  
11.  The matching process should fail and the user will be asked two more times,then press the “**Continue”** button.  
12. Repeat step 10 and 11 two times  
13. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
User has failed match process and  is navigated to the “Verification complete” page

**Actual Result:**  
Same as Expected Result 

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### 

#### Test Case\_C26: Test system response with similar-looking faces or generate by AI

**Test Case Session ID: 6898ae578274769bfbe9a99e**

**Description:** 

This negative test case evaluates the system's ability to differentiate between a live user's face and a similar-looking face, including those generated by AI. The user is instructed to present an AI-generated image of a face that closely resembles their own or a picture of an identical twin to the camera during the liveness and face-matching stages. This test aims to verify that the application's facial recognition algorithm is robust enough to detect subtle differences and prevent a successful match, thereby avoiding potential spoofing attempts.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user has an official government document, such as ID, passport or driver's license  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs generate another similar face by using AI (e.g. ChatGPT )  
* The user needs to have a monitor or phone to display the photo.

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"Driver's license, ID"**  
4. On the "Place your ID" page, click **"Continue"**.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. Scan the front of the ID document, afterwards click **"Continue"** button  
7. Scan the back of the ID document then click the “**Continue”** button.  
8. On the "Let's take a selfie" page, click **"Continue"**.  
9. Take a selfie of generated AI photo  
10.  The process should fail because the face is not aligned with the dotted outlines and the user will be asked two more times,then press the “**Continue”** button.  
11. Repeat step 9 and 10 two times  
12. After the matching process fails, click **"Continue"** to complete the test case.

**Expected Result:**  
User has failed matching and is navigated to the “Verification complete” page 

**Actual Result:**  
Same as Expected Result

 **Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

#### Test Case\_C27: Test cancelling matching process(refresh page)

**Test Case Session ID: 689b59b2380225a5f49fd88e**

**Description:** This negative test case evaluates the system's ability to handle the cancellation of the matching process. The user begins the matching process, and while it is actively in progress, they perform a disruptive action such as refreshing the browser page. The test aims to verify that the application handles this interruption gracefully, either by canceling the current process and returning the user to a previous step, or by properly restarting the matching process without crashing or entering an unstable state.

**Preconditions:**

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to have an official document, such as an ID, driver's license, passport to use for the ID capture step.  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs a good light source

**Steps:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, choose **"ID, Driver's license"**  
4. On the "Place your ID" page, click the **"Continue"** button.  
5. Click the **"Ready to scan"** button to activate the camera.  
6. **Take an image of the front of a valid ID document**   
7. The system may proceed to capture the back of the ID. On the "**Ready to scan**" page, click **"Continue"**.  
8. **Take an image of the back of a valid ID document**   
9.  the system may proceed to the selfie capture step. On the "Let's take a selfie" page, click **"Continue"**.  
10. Follow the on-screen instructions, removing any hats or glasses and positioning your face in the camera frame.  
11. Take a selfie. The process should then proceed to the "matching" stage.  
12. While the matching process is going refresh the page

**Expected Result:**  
The system should detect that the user refreshed the page (which cancels the matching process ) and is navigated to “Take a selfie” page or  user is navigated to first page of Test Environment

**Actual Result:**  
The matching process is cancelled due to page refresh, user is navigated to first page of Test Environment

**Status of Test:** PASSED

**Note:**  
There were no bugs, application crashes or unhandled errors while testing

### **3\. Bugs and Inconsistencies Found**

#### **Bug report**

**Title**: The application incorrectly requests camera access and restarts the workflow when a user changes phone orientation during camera loading.

**BR\_ID**: 001  
**Test Case Session ID: 68974bc67c4c578f169dce04**

**Description:** During testing, it was found that if the user rotates their phone from  vertical (portrait) to horizontal (landscape)  orientation while camera is loading, the app erroneously prompts the user to grant camera access again. This action unexpectedly redirects the user back to the first page of the process, disrupting the flow and causing confusion. 

**Test Environment**: https://onboardingdemo.com/qatest2025.vk899/flow  

**Device Used:** Samsung Galaxy S22 Ultra (Android 15), Chrome Browser(138.0.7204.180) 

**Preconditions**: 

* The user needs to have a smartphone (Android or iOS) with an active internet connection.  
* The user needs to grant the browser permission to access the device's camera.  
* The user needs to have auto-rotation on

**Steps to reproduce:**

1. Navigate to the Test environment (via provided link or QR code)  
2. Click the **"GET STARTED"** button.  
3. On the "Select document" page, click on **"ID, Driver's license"** button  
4. On the **"Place your ID**" page, click the **"Continue"** button.  
5. While Camera is loading, rotate Phone from Vertical to Horizontal position  
6. The app erroneously prompts the user to grant camera access again, and the user clicks the “Allow permission" button twice.

**Expected result:**

User is back to the "Place your ID" page

**Actual result:**   
This action unexpectedly redirects the user back to the first page of the process, disrupting the flow and causing confusion. 

**Severity**: Medium  
**Priority**: Medium

**Attachment**:(The link has been omitted due to NDA restrictions.)

###    **4\. Suggestions for Potential Improvements** 

1. **UI suggestion:** On the first page of the Test Environment, the logo should be visually centered to ensure balanced layout and a more professional appearance.  
2. **Progress Indicators:** Display clear step-by-step progress bars so users know where they are in the verification process.  
3. **Fix the Screen Rotation Bug**: A bug was identified in Test Case\_A02 where rotating the phone from portrait to landscape while the camera is loading redirects the user to the very first page of the Test Environment. This is a major usability issue that can lead to user confusion and drop-off. This bug should be a priority to fix.  
4. **Enhancing the interruption recovery process:** Test Case\_A06 revealed that refreshing the page during the upload process resets the user to the start of the test flow. While this behavior prevents system crashes, it negatively impacts the user experience. A more user-friendly approach would be to:  
   Preserve progress and allow the user to resume from the last completed step, or  
   display a clear confirmation prompt asking if they wish to refresh the page, warning them that progress will be lost.  
5. **Implement Proper Document Expiration Validation:** Test Case\_A07 reveals a significant security flaw: the system successfully processes an expired document and allows the user to complete the verification. The application's document validation must be updated to read the expiration date on the ID and automatically reject any document that has passed its expiry date.

[image1]: <data:image/png;base64,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>