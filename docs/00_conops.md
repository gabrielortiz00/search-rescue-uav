# Concept of Operations

## Autonomous Search UAS

## 1. Purpose

This document describes the concept of operations for an autonomous fixed-wing UAS designed to search a defined area, detect the presence of a person on the ground, and alert a ground operator. The system is a personal engineering project with applications in search and rescue and ISR.

## 2. Background

Locating a person in a large natural area is a difficult task. Ground searches are slow, resource-intensive, and expose search personnel to the same hazardous conditions they are searching in. Manned aircraft are expensive and require significant coordination. Small UAS offer a compelling alternative: low cost, rapid deployment, and the ability to cover large areas of terrain systematically and autonomously, without placing additional personnel in the field.

This project explores what it takes to build this capability from scratch, integrating an autonomous fixed-wing platform with a thermal imaging payload, a custom ground control station, and a detection pipeline capable of identifying a person from the air.

## 3. System Overview

The system consists of three primary components:

**UAV:** A fixed-wing airframe with autopilot integration, thermal camera payload, and telemetry and video downlink.

**Ground Control Station (GCS):** A custom software application for mission planning, live telemetry display, video feed monitoring, and detection alerting.

**Detection Pipeline:** Image processing that identifies human heat signatures in the thermal feed, distinguishes them from other heat sources, and alerts the operator in real time.

## 4. Operational Context

**Operator:** Remote pilot in command (RPIC), operating under FAA Part 107 or locally applicable regulations. No dedicated spotter or ground crew required.

**Environment:** Mixed terrain including open fields, light forest, and suburban periphery. Day operations initially, expanding to night operations as the project matures.

**Launch and Recovery:** The system must be launchable and recoverable by a single operator without ground support equipment or a prepared surface.

**Regulatory:** Part 107 compliant. Initial operations within VLOS; BVLOS a future extension pending applicable waiver.

## 5. Mission Narrative

The operator arrives at the search area and opens the GCS. A coverage grid is drawn over the target area and one of several automatically generated search patterns is selected. Altitude, lateral spacing, and airspeed are configured to optimize detection probability for the given terrain and lighting conditions.

After assembly and pre-flight checks, the UAV is launched and climbs to search altitude, then transitions to autonomous flight and executes the planned route without further operator input.

The GCS displays live telemetry and the thermal video feed continuously. The detection pipeline processes the feed in real time, flagging signatures consistent with a person on the ground. On a detection event, the GCS alerts the operator and logs the GPS coordinates of the contact.

The operator reviews the flagged detection and decides whether to investigate further by commanding the UAV to orbit the location, or to disregard and continue the search. At mission end the UAV returns to the home point and the operator recovers it.

## 6. Key Scenarios

**Scenario A — Open terrain, daytime**
Person located in an open field or meadow. High thermal contrast and clear sightlines. Baseline case for detection pipeline development and system validation.

**Scenario B — Mixed terrain, twilight**
Person located near a forest edge or partially obscured by vegetation. Reduced thermal contrast. Tests detection robustness at the margins of system capability.

**Scenario C — Simulated exercise**
A person is placed in the search area without the operator knowing the exact location. Tests end-to-end system performance under realistic conditions. Primary acceptance test for the system.

## 7. Constraints and Assumptions

- Single RPIC; no dedicated ground crew or spotter
- FAA Part 107 compliant; no flight over people
- System must be operable without a prepared launch surface
- System must be transportable by a single operator
- ArduPlane used as the autopilot platform
- Initial operations within VLOS
- BVLOS and night operations are future extensions
- No integration with external emergency or military systems in scope for initial build
