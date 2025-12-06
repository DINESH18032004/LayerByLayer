# LayerByLayer

# Real-Time Oil Spill Detection Using SAR–AIS Data Fusion
## AI-Powered Maritime Environmental Monitoring

## Overview

This system provides real-time oil spill detection by combining Synthetic Aperture Radar (SAR) satellite imagery with Automatic Identification System (AIS) vessel tracking data. Deep learning models classify spills from radar images, anomaly detection evaluates vessel behavior, and a multi-channel alerting framework enables quick responses in maritime environments.

## Problem Statement

Oil spills often go unnoticed for long periods because traditional detection depends heavily on manual reports or infrequent satellite checks. SAR-only surveillance generates many false positives because natural phenomena can resemble oil slicks. Existing systems also cannot predict vessel behavior before a spill happens. Remote maritime zones often lack connectivity, preventing timely communication. Manual verification slows down response workflows, and conventional architectures struggle to scale across large ocean regions.
Objective: Build an AI-driven, automated, scalable system that detects spills accurately and delivers alerts instantly.

## How This System Addresses the Problem
### Late Detection & Slow Response

Traditional systems detect spills too late due to manual observation and long intervals between image captures.

Solution: 
Live SAR imagery and continuous AIS streams are processed automatically using serverless computing, allowing detections within seconds of data arrival.

### High False Positives from SAR Alone

Radar images frequently misinterpret calm-water zones, algae, or ship wakes as oil spills.

Solution: A CNN identifies candidate spill regions, and vessel behavior from AIS is analyzed to verify whether nearby ships showed suspicious movement patterns, reducing false alarms significantly.

### No Early Prediction of Spill Risk

Older systems only detect oil after it is visible on the water surface.

Solution: LSTM models analyze vessel motion sequences to predict unusual behaviors such as abrupt halts or route deviations, generating early warnings before spills occur.

### Connectivity Issues in Offshore Regions

Many spill-prone areas lack cellular or internet coverage, preventing alerts from reaching authorities.

Solution: Alerts can be transmitted via AIS broadcasts, VHF maritime radio, and satellite Short Burst Data, ensuring communication even in remote locations.

### Manual Verification Delays

Human review slows down detection pipelines and causes inconsistent responses.

Solution: Automated SAR classification, AIS scoring, and fusion-based confirmation enable the system to dispatch alerts without requiring human intervention.

### Lack of Scalability & Regional Adaptation

Conventional systems perform poorly when deployed across vast or diverse maritime regions.

Solution: A cloud-native microservice architecture scales automatically, while transfer learning and modular models adapt easily to new regions and environmental conditions.

## System Architecture
### Data Acquisition

SAR data from Sentinel-1 satellites provides radar imagery of ocean surfaces, and AIS data supplies vessel positions and movement patterns.

### Data Fusion

SAR detections are aligned with AIS activity in both space and time to determine whether an observed anomaly is consistent with vessel behavior.

### Detection Models

A CNN classifies SAR patches as spill or non-spill. Isolation Forest identifies outlier vessel behavior. LSTM models evaluate temporal vessel motion for predictive insights.

### Alert Engine

Alerts are automatically delivered through email, SMS, mobile push notifications, dashboards, VHF radio messages, AIS safety broadcasts, and satellite SBD communication.

### Deployment

The system is deployed using serverless functions (AWS Lambda or GCP Functions), containerized microservices, and cloud message queues for scalable, real-time processing.

## Algorithms Used
### AIS Anomaly Detection

Isolation Forest detects abnormal vessel trajectories, LSTM models analyze motion patterns over time, and rule-based filters validate vessel proximity and timing.

### SAR Image Classification

A CNN distinguishes spill-like textures from background ocean patterns, transfer learning improves performance across different regions, and synthetic augmentation compensates for limited spill datasets.

## Data Pipeline
### SAR Workflow

Incoming SAR images undergo noise reduction, geometric correction, patch extraction, and CNN inference to identify potential spills.

### AIS Workflow

AIS streams are continuously processed to generate anomaly scores using Isolation Forest and vessel-behavior predictions using LSTM.

### Fusion Layer

A spill is confirmed only when SAR classification and AIS anomalies occur at the same location and time, ensuring high-confidence detection.

### Alert Dispatch

Alerts include the spill coordinates, associated vessel information, detection confidence, and the SAR-derived visual evidence.

### Alerting System

Alerts are delivered through multiple channels to maintain reliability. When networks are available, email, SMS, mobile notifications, and dashboards are used. In remote areas, VHF radio, AIS broadcasts, and satellite SBD ensure uninterrupted communication.

### Innovation & Uniqueness

The system combines SAR and AIS data to significantly reduce false positives. Predictive vessel modeling identifies risk before spills occur. Synthetic datasets improve training despite limited real examples. A serverless cloud-native structure supports global scaling. The system can integrate drone-based verification and operate on edge devices such as onboard ship computers.

##  Tech Stack

### **Languages**

* Python
* JavaScript (Dashboard)

### **AI / ML**

* PyTorch
* Scikit-learn
* OpenCV
* GeoPandas

### **Data Providers**

* Sentinel-1 SAR
* MarineTraffic AIS
* Spire Maritime AIS

---

##  Future Enhancements 

###  AI-Based Spill Severity Estimation

Use U-Net or Mask R-CNN to assess spill area, spread rate, and thickness.

###  Spill Drift & Weather Forecasting

Integrate:

* Wind fields
* Tide models
* Ocean currents

###  Blockchain Event Logging

Ensures tamper-proof evidence for insurance and legal claims.

###  Federated Learning Support

Enables international agencies to train models without sharing raw data.

###  On-Vessel Edge AI

Runs lightweight CNN + AIS anomaly detection locally on ships.

---

## Figures 

<img width="279" height="803" alt="image" src="https://github.com/user-attachments/assets/9f878d84-9e0b-4ba2-afb8-8aa28a974bf6" />

* Sentinel-1 SAR example scene 
<img width="516" height="251" alt="image" src="https://github.com/user-attachments/assets/15eb7f64-8880-49a7-84ff-92bbf8c33b80" />

* Satellite SBD block diagram 
<img width="508" height="227" alt="image" src="https://github.com/user-attachments/assets/14ad7017-2a04-456d-985f-64038d46ed1e" />

---

##  Contributors

* **Sri Varshan P**
* **Shriram S**
* **Mr. Dinesh Babu G L** (Assistant Professor, Guide)
* **Kanishkar M**




