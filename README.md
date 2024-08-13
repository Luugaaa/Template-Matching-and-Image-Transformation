# Template Matching and Image Transformations

## Overview

This project explores two fundamental concepts in image processing: template matching and homographic transformations. We aimed to detect and replace elements in images through practical applications—locating "Waldo" in a complex scene and replacing an advertisement on a bus with another image.

## 1. Template Matching

### Objective

The goal was to identify Waldo in a crowded image using a template matching algorithm. This involved comparing a small template (Waldo's image) with different sections of a larger image (a crowded amusement park) to find the best match.

### Methodology

- **Sum of Squared Differences (SSD):** The similarity between the template and a section of the image was evaluated by calculating the SSD between corresponding pixels. A lower SSD indicates a higher similarity.
- **Optimization:** To reduce computation time, a threshold was introduced. If the initial pixel comparison between the template and a section of the image did not meet the similarity threshold, further SSD calculation was skipped for that section.
- **Result:** The algorithm successfully located Waldo in both the unnoised and noised versions of the image, demonstrating robustness even when the image is altered.

## 2. Image Transformation Using Homography

### Objective

The task was to replace a Sprite advertisement on the side of a bus with a poster of "The Simpsons," considering the perspective distortion due to the angle of the bus.

### Methodology

- **Corner Detection:** We first identified the four corners of the bus's advertisement space to define the region where the new image would be placed.
- **Homographic Transformation:** 
  - **Method 1:** A matrix was computed using the least squares method to map the Simpsons poster onto the bus advertisement.
  - **Method 2:** The reverse approach was also explored, where the bus advertisement space was mapped back to a flat plane to align with the poster. This method, while more computationally intense, proved faster due to processing fewer pixels.
- **Result:** Both methods produced the desired image transformation, with the second method being more efficient despite its complexity.

## Conclusion

This project highlighted key aspects of image processing:
- **Template Matching:** Proved effective for object detection even with noise, showcasing the robustness of the SSD method.
- **Homography:** Demonstrated how different approaches to image transformation can yield similar results but with varying efficiency. This emphasizes the importance of algorithmic efficiency in practical applications.

Both sections illustrated that multiple methods can achieve the same goal, but the choice of method depends on the specific requirements of the task, such as computational efficiency and accuracy.
