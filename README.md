# search-rescue-uav

An autonomous fixed-wing UAV platform for search and rescue operations, 
with a custom ground control station and computer vision target detection.

## Mission

Build an autonomous fixed-wing UAV capable of executing intelligent search 
patterns over large wilderness areas, with onboard computer vision to detect 
and flag targets, controlled via a custom ground control station — making 
large-area wilderness SAR faster, cheaper, and more effective than 
ground teams alone.

## Motivation

Search and rescue operations in wilderness terrain are slow and resource-intensive. 
Fixed-wing UAVs offer significantly greater range and endurance than quadcopters, 
enabling coverage of tens of square kilometers on a single battery. This project 
explores what a capable, affordable, and fully autonomous fixed-wing SAR platform 
looks like when built from the ground up.

## System Overview

- **Aircraft** — Custom fixed-wing airframe running ArduPlane
- **Autopilot** — Pixhawk flight controller with GPS, compass, and IMU
- **Ground Control Station** — Custom-built GCS with live map, telemetry, 
  and mission planning
- **Computer Vision** — Onboard target detection pipeline flagging 
  persons of interest in real time
- **Communication** — MAVLink over telemetry radio

## Status

Planning — simulator environment configured, hardware on order.

## Author

Gabriel Ortiz — CS @ Northeastern University  
Built in Monterrey, México. Summer 2026.
