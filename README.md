# Indoor Positioning System using BLE RSSI

Using machine learning to predict indoor locations based on Bluetooth Low Energy (BLE) RSSI signal strengths.

## Overview

Indoor localization is a challenging problem due to the absence of GPS signals indoors. Bluetooth Low Energy (BLE) beacon offer a low-cost and power-efficient alternative for estimating location via signal strength readings, specifically Received Signal Strength Indicator (RSSI) values. This project leverages machine learning models to map noisy RSSI signals to precise (x, y) coordinates in a known indoor space.

## Background and motivation

BLE beacons continuously emit signals, and devices can detect the signal strength (RSSI) from nearby beacons. However, RSSI values can fluctuate significantly due to environmental factors such as:
- Walls and partitions
- Furniture and obstructions
- Human movement and interference

Traditional approaches to indoor positioning rely on geometric methods like trilateration. These struggle with signal noise and multipath effects. Instead, machine learning models can learn the mapping directly from data, capturing non-linear and environment-specific signal behavior.

### Why ML? 

1. Environment Adaptability: Models are trained on localized data, making them highly tailored to each space.

2. Noise Handling: ML can learn patterns despite fluctuating RSSI values.

3. Improves with Data: The more labeled examples available, the more accurate the model becomes.

4. Continual Refinement: Models can be retrained to adjust to layout or beacon configuration changes.

## Scalability limitiations

Despite its promise, this approach has some practical limitations:

1. Environment-specific models: Each deployment requires training a new model tailored to that physical environment. A model trained for Office A may not work accurately in Office B due to different layouts, materials, or interference.

2. Calibration effort: The system requires collecting labeled RSSI-location data during an initial setup phase that can be time-consuming and labor-intensive.

3. Recalibration needs: Any significant changes to the interior layout (e.g., walls, furniture, repositioned beacons) can disrupt signal dynamics, necessitating model retraining.

## Models implemented

1. Gradient Boosting Regressor (GBR)

- Pros: Captures non-linear relationships, performs well on small-to-medium datasets.
- Accuracy: ~86.6% within 1-unit square.

2. K-Nearest Neighbors (KNN)

- Pros: Simple and effective for spatial data.
- Accuracy: ~91.6% within 1-unit square.
