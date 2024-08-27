# node-red_temperature_monitoring

This repository contains my first Node-RED project for logging the temperature of a boiler. The project involves monitoring two temperature points:

- **T1**: This is typically the higher temperature, measured next to the boiler's original temperature sensors (there are two for redundancy).
- **T2**: This is measured at the inlet tube and serves as a good indicator of water flow. The temperature increases if no hot water is consumed during a longer period of time, due to the backflow of hot water into the feeding tube.

## Project Overview

### Initial Implementation

The first function node, named **'Format Spreadsheet Line'**, was designed to write the date & time followed by the two temperatures. However, this script has some issues:
- It cannot handle the race condition between the two measurements.
- It fails to differentiate between T1 and T2 by topic.
- It does not write all values into one line after the date & time.

This flow has been running since 2019-02-26, the date of the last descaling. The goal is to determine the need for boiler descaling by monitoring the slope of the heating curve.

### Second Implementation

The second function node, named **'Second Try'**, was implemented on 2023-01-11 after watching a Node-RED video by Norm Freeman from Opto22 about writing values into a file. This node writes identifiable values into the file but introduces too much overhead. Nevertheless, this data can be used for later analysis.

---

Feel free to let me know if there are any specific areas you'd like to focus on or if you need further adjustments!
