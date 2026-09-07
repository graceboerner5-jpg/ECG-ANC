---
title: Validation & Testing
layout: home
nav_order: 5
---

# Validation & Testing

## Overview

## (i) Hardware & Circuit Configuration

A bioamplifier circuit and Arduino Uno were borrowed from the Georgia Tech Library for obtaining the experimental ECG and sEMG signals. The board provided 5V power and analog-to-digital conversion at 1200 Hz. Electrode connections were made using alligator clips with Bio(0)- and Bio(0)+ carrying the ECG signal and Bio(1)- and Bio(1)+ carrying the sEMG reference signal. The two channels simultaneously recorded both signals allowing for adaptive noise cancellation. 

[images of schematic and circuit]
Schematic provided by Georgia Tech BMED 3110.

**AD623 Instrumentation Amplifier - Stage (1)**
The AD623 amplifies the difference between the two input electrodes and uses common-mode reject to cancel any signals common to both such as a powerline interference. This common-mode rejection is the same principle as what is used in bipolar pacemaker leads.

**Gain Stage - Stage (0)**
The gain stage is set by the 100kOhm potentiometer which amplifies approximately 3 times since ECG signals at the surface are typically relatively low voltage.

**High Pass Filter - Stages (3) and (4)**
The high pass filter removes any low voltage disturbances such as breathing or electrode movement. This is crucial since any drift could reduce the accuracy of the adaptive noise cancellation filter.

**Low Pass Filter - Stage (5)**
This stage allows the two channels to split. LP-ECG limits the ECG signal to the standard cardiac band while LP-EMG keeps the higher frequencies to determine the muscle artifact.

**Virtual Ground - Stages (8) and (9)**
These stages use a voltage divider to set a baseline for the signal. This moves the zero of the signal up to 2.5V to avoid any lost signal from the Arduino being unable to read below zero.

**Output Buffer - Stage (7)**
This final stage buffers the signal for the last time and outputs it to the Arduino analog input pin.

## (ii) Electrode Placement

## (iii) Signal Acquisition & Code Changes

## (iv) Validation Results

## (v) Reflection
