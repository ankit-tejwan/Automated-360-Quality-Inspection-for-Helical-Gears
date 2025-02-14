# Introduction
This project enables automated quality inspection of helical gears manufactured by Sona BLW Precision Forgings Ltd (Sona Comstar) for Tesla.
It integrates a rolling machine, Baumer industrial cameras, and a YOLO-based object detection system to ensure defect-free production.

# System Workflow

# Step 1: Gear Rotation & Image Capture Setup
The manufactured helical gear is placed in the rolling machine.
The machine uses a drive mechanism to rotate the gear 360° based on a PLC signal.

# Step 2: Image Acquisition
Two Baumer industrial cameras capture images during rotation.
A total of 30 images are acquired within 1 minute for complete surface inspection.

# Step 3: Image Preprocessing and perspective transformation
The images are sent to a FastAPI server (running on Uvicorn).
Using OpenCV, a perspective transformation is applied to convert tilted images into a 2D planar view for accurate object detection.

![Figure_1](https://github.com/user-attachments/assets/769c1f71-f14c-46ff-a44b-2b4b7c3ce74b)

# Step 4: Defect Detection Using YOLO
The transformed images are sent to the YOLO object detection model.
The model analyzes the images and detects defects .

# Step 5: Data Storage
The inspection results are saved in the Sona Comstar database server for tracking and analysis.

# Step 6: Real-Time Monitoring
Simultaneously, results are displayed on a real-time dashboard over the local LAN IP.
Operators can monitor inspection status and detected defects instantly.

# Technologies Used
*Hardware:* Rolling Machine, PLC, Baumer Industrial Cameras

*Software:* FastAPI, Uvicorn, OpenCV, YOLO Object Detection

*Database:* Sona Comstar Database Server

*Dashboard:* Real-time visualization of Production  Dashboard  over Local LAN
