# System Overview

## Motivation

A driver-assistance system should understand both the environment around the vehicle and the state of the driver. A road hazard is more urgent when the driver is distracted, looking away, or showing signs of drowsiness. This project therefore treats driver behavior analysis as a multi-source computer vision problem rather than a single object-detection task.

The prototype combines road-scene perception, driver monitoring, temporal tracking, and alert generation into one integrated pipeline.

## Input Streams

### Outside-Car Camera

The outside-car stream captures real-time visual data from the driving environment. This stream is used to identify objects and events that may require a driver response, including:

- Vehicles.
- Pedestrians.
- Traffic lights.
- Road-side hazards.
- Motion patterns of surrounding objects.

### Inside-Car Camera

The inside-car stream captures the driver's face and upper-body region. This stream is used to estimate attention-related signals, including:

- Face presence.
- Approximate head direction.
- Looking forward, left, right, or away.
- Potential inattention or drowsiness.

## Perception Pipeline

### 1. Road-Scene Object Detection

The exterior stream uses YOLOv8 to detect objects in real time. YOLO-style one-stage detectors are suitable for ADAS prototypes because they provide a practical balance between speed and detection accuracy. In this project, object detection supplies semantic information about the driving scene: what objects are present and where they are located in the image.

### 2. Motion Tracking

Optical flow is used to estimate how visual patterns move between consecutive frames. This adds temporal reasoning on top of object detection. Instead of treating each frame independently, the system can reason about motion direction, object movement, and changes in nearby traffic.

### 3. Driver Face Detection

The in-cabin stream uses an SSD-based face detector to localize the driver's face. SSD-style detectors are efficient single-shot models that can provide fast face-region proposals for downstream attention analysis.

### 4. Head-Direction Estimation

After detecting the driver's face, the system estimates head direction from the face region. The goal is not only to know whether a face is present, but also whether the driver appears to be oriented toward the road or away from relevant hazards.

### 5. Decision Fusion

The decision layer compares both streams:

- What is happening outside the vehicle?
- What is the driver paying attention to?
- Does the current scene require an immediate warning?

This fusion step is what turns perception into driver assistance. For example, a pedestrian near the road can trigger a stronger warning when the driver is not looking forward.

### 6. Voice-Based Alerts

The final output is an alert interface designed to communicate warnings in real time. Example alerts include:

- Wake up.
- Traffic light ahead.
- Pedestrian nearby.
- Look left.

## Architecture Diagram

![System architecture](../assets/media/system-architecture.jpg)

## Design Notes

- The project is structured around modular computer vision components, so each perception task can be improved independently.
- The system uses complementary viewpoints: outside-scene context and inside-driver context.
- Temporal tracking is included because driving is dynamic; motion cues are often as important as single-frame detections.
- The decision layer is intentionally interpretable in this prototype, making it easier to inspect why a warning was produced.

## Limitations

This repository currently documents the project and demonstrations only. It does not yet include:

- Source code.
- Model weights.
- Dataset preparation scripts.
- Training or evaluation notebooks.
- Quantitative benchmark results.

Those materials can be added in a future release if the implementation is prepared for public distribution.

