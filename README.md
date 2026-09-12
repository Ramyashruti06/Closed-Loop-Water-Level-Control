# Closed-Loop-Water-Level-Control
MATLAB simulation for closed loop using Bang-Bang control

# OBJECTIVE
To simulate a relay controlled water-level control system for a tank in a closed loop system using Bang-Bang control and evaluate how different hysteresis bands affect relay switching frequency.

# METHODOLOGY
Tank water level is simulated over time with fixed drain rate and fill rate. Based on hysteresis, the relay module turning the pump ON / OFF is based on previous time step’s water level.

# PARAMETERS
1. Target level = 15 cm => The water level which needs to be constant.
2.	Hysteresis => ± 1 cm => The range for the level to drift and the relay to react.
3.	Relay switch => Enables the pump for ON and OFF modes.
4.	Level_cal => It creates a list of water level from 0 to 20 cm with the range of intervals.
5.	Resistance_cal => It represents a quadratic curve to determine sensor’s resistance with water level.
6.	dt = 2 => Time step size.
7.	T = 500 => Total time window.
8.	Drain_rate = 0.01 => Loss of water per time step.
9.	Fill_rate = 0.05 => Amount of water added per time step when the pump is running.
10.	level_sim, relay_state => These 2 variables store water levels at each time step
11.	rng(42) => random integer

# CODE
The source code is available at [https://github.com/Ramyashruti06/Closed-Loop-Water-Level-Control/blob/main/Bang-Bang%20_control_code].

# GRAPHS
Calibration curve - 
<img width="1119" height="674" alt="calibration_curve" src="https://github.com/user-attachments/assets/053da7da-f37a-4eb3-a64d-a2db6a38e1e6" />

Water-level hysteresis [0.5] - 
<img width="1119" height="674" alt="waterlevel_control_hyst0 5" src="https://github.com/user-attachments/assets/16a30fef-8867-4053-a1c5-4f08d7f93b28" />

Water-level hysteresis [1] - 
<img width="1119" height="674" alt="waterlevel_control_hyst1 0" src="https://github.com/user-attachments/assets/226fc3ba-6958-49b9-8776-93c3e85ae1f8" />

Water-level hysteresis [2] - 
<img width="1119" height="674" alt="waterlevel_control_hyst2 0" src="https://github.com/user-attachments/assets/f74ddbdf-126d-4a4c-98e1-a250635a85ae" />

Water-level hysteresis [4] - 
<img width="1119" height="674" alt="waterlevel_control_hyst4 0" src="https://github.com/user-attachments/assets/8ab3825c-137b-4d18-af65-e7cf2b9da4f7" />

Water-level hysteresis [6] - 
<img width="1119" height="674" alt="waterlevel_control_hyst6 0" src="https://github.com/user-attachments/assets/63235e4a-4c3a-40ac-b88d-794c894adeb5" />

# RESULTS
Hysteresis values for each relay switch count -

| Hysteresis value | Relay switch count |
|:---|---:|
| 0.5 | 8 times over 500 minutes |
| 1 | 4 times over 500 minutes |
| 2 | 2 times over 500 minutes |
| 4 | 2 times over 500 minutes |
| 6 | 1 time over 500 minutes |

# OBSERVATIONS
- The simulation show Bang-Bang control in a closed loop with a target level of 15 cm and a defined time window of 500 min.
- The pump ON switches when the water level drops below the lower threshold limit (Target level - Hysteresis) and switches OFF when the water level rises above the upper threshold limit (Target level + Hysteresis).
-	When the hysteresis values are 2 cm and 4 cm, the relay switch counts are 2. This might be due to fixed time interval (500 min), fixed fill rate and drain rate.
-	Testing multiple hysteresis bands shows an inverse relationship between hysteresis band and relay switch count. A narrow band caused more frequent switching whereas a wider band requires reduced switching.

# LIMITATIONS
- Although a real-time closed loop simulation is done, certain aspects rely on assumptions rather than real-time data.
- Calibration curve of water-level sensor is assumed since actual resistance-to-level readings are not yet measured.
- Drain rate and fill rate are pre-defined and do not represent real-time factors like evaporation.
- The simulation window was set to 500 minutes, which was insufficient to differentiate relay-switching for 2 cm and 4 cm hysteresis bands.

# FUTURE SCOPE
In addition to Bang-Bang control, a system to detect and rectify leaked currents in the tank can be implemented.

# PROJECT STATUS 
MATLAB Simulated project

# AUTHOR
KOTIKALAPUDI RAMYA SHRUTI
