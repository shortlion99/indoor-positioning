# Indoor Positioning System using BLE RSSI

Using machine learning to predict indoor locations based on Bluetooth Low Energy (BLE) RSSI signal strengths.

## Overview

Indoor localization is a challenging problem due to the absence of GPS signals indoors. BLE beacons offer a low-cost alternative for estimating location via signal strength readings. This project explores machine learning-based regression models to map RSSI values to (x, y) coordinates in a predefined grid.

## Models

Two models were implemented and compared:

1. Gradient Boosting Regressor (GBR)

- Pros: Handles non-linearities well, good with small datasets.
- Accuracy: ~86.6% within 1-unit square.

2. K-Nearest Neighbors (KNN)

- Pros: Simple and effective for spatial data.
- Accuracy: ~91.6% within 1-unit square.
