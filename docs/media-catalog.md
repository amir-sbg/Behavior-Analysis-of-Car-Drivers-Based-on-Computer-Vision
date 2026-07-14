# Media Catalog

This file lists the visual assets and demonstration media associated with the project page.

## Images Stored in This Repository

| File | Description | Usage |
| --- | --- | --- |
| [`assets/media/driver-behavior-intro.jpg`](../assets/media/driver-behavior-intro.jpg) | Prototype setup inside the car. The image shows real-time visual acquisition from inside the vehicle, real-time acquisition from outside the vehicle, and local processing of received visual data. | Main README project overview image. |
| [`assets/media/system-architecture.jpg`](../assets/media/system-architecture.jpg) | System architecture diagram showing outside-scene perception, in-cabin driver monitoring, decision fusion, and final output generation. | README architecture section and technical documentation. |

## Video Demonstrations

The videos are stored in this repository as MP4 files and mirrored on Google Drive.

| Demo | Local MP4 | Google Drive Mirror | Expert Description |
| --- | --- | --- | --- |
| Head Direction Detection | [`assets/videos/head-direction-detection.mp4`](../assets/videos/head-direction-detection.mp4) | [Open video](https://drive.google.com/file/d/1A2q3yyOWNahFMdCXNqwSgLiplSm0I8R8/view?usp=sharing) | Demonstrates the in-cabin monitoring stream. The driver face is localized and the system estimates the driver's head direction for attention-aware decision making. |
| Object Detection and Tracking | [`assets/videos/object-detection-tracking.mp4`](../assets/videos/object-detection-tracking.mp4) | [Open video](https://drive.google.com/file/d/10NZdcjuLJwZpQkWyuejilv89bkpzwO8w/view?usp=sharing) | Demonstrates the exterior perception stream. YOLOv8 is used for object detection, while optical flow contributes temporal motion information across video frames. |
| Wake Up Alert | [`assets/videos/wake-up-alert.mp4`](../assets/videos/wake-up-alert.mp4) | [Open video](https://drive.google.com/file/d/1OBGQBOWgTtPI4M-Lg9MHks1ceZ5gpF04/view?usp=sharing) | Demonstrates an attention or drowsiness warning. The system identifies a driver state that requires intervention and produces an alert. |
| Traffic Light Alert | [`assets/videos/traffic-light-alert.mp4`](../assets/videos/traffic-light-alert.mp4) | [Open video](https://drive.google.com/file/d/1SKdeQcPozlHjiXv1Xai9ZFWGEwpoZ0t2/view?usp=sharing) | Demonstrates detection of traffic-light context in the road scene and translation of that perception result into a driver-facing notification. |
| Pedestrian Alert | [`assets/videos/pedestrian-alert.mp4`](../assets/videos/pedestrian-alert.mp4) | [Open video](https://drive.google.com/file/d/175rLPKxnW_U6EwKj4D845NgkOWCcjafd/view?usp=sharing) | Demonstrates pedestrian detection for safety-critical road-scene awareness. |
| Look Left Alert | [`assets/videos/look-left-alert.mp4`](../assets/videos/look-left-alert.mp4) | [Open video](https://drive.google.com/file/d/1Xo7zvCDjAGA3eRQL3tgdRpmuObn_qE4a/view?usp=sharing) | Demonstrates side-hazard reasoning, where the system prompts the driver to pay attention to the left side of the vehicle. |

## Source Page

The media catalog is based on the public project page:

[https://amir-sbg.github.io/driver-behavior/](https://amir-sbg.github.io/driver-behavior/)
