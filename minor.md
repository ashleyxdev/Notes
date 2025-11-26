# UNIT–1: INTRODUCTION TO INDUSTRIAL AUTOMATION – ONE PAGE REVISION NOTES

## 1. PLC (Programmable Logic Controller)

Definition:
Industrial digital controller used for automation of machines & processes.

### PLC Architecture

* Power Supply
* CPU – executes logic, scan cycle
* Memory – RAM, ROM/Flash
* I/O Modules – DI/DO, AI/AO
* Communication Ports – Modbus, Profibus, Ethernet/IP
* Programming Device

### PLC Scan Cycle

1. Input Scan
2. Program Execution
3. Output Scan
4. Diagnostics/Communication

## 2. Types of PLC

### By Size / I/O Capacity

* Nano PLC: < 32 I/O
* Micro PLC: 32–128 I/O
* Medium PLC: 128–512 I/O
* Large PLC: > 512 I/O

### By Construction

* Fixed/Compact PLC – built-in I/O, no expansion
* Modular PLC – expandable, multi-slot rack

### By Application

* Relay PLC
* Motion Control PLC
* Safety PLC
* Process PLC

## 3. PLC Programming Languages (IEC 61131-3)

* Ladder Logic (LD)
* Functional Block Diagram (FBD)
* Structured Text (ST)
* Instruction List (IL – obsolete)
* Sequential Function Chart (SFC)

## 4. Applications of PLC

* Assembly lines
* Process industries (chemical, food, water)
* Robotics & motion control
* Packaging, conveyors
* Building automation
* Traffic control

## 5. HMI (Human Machine Interface)

Definition: Device that allows operator interaction with PLC-controlled processes.

### Need for HMI

* To visualize processes
* Modify setpoints
* View alarms, trends
* Manual/auto control

### Advantages

* User-friendly interface
* Real-time monitoring
* Reduces operator error
* Faster troubleshooting

## 6. PLC Interfacing

PLC interfaces with:

* HMI – operator screen
* Drives (VFDs) – motor speed control
* Sensors – proximity, limit switch, RTD, pressure
* Actuators – valves, relays, solenoids
* Robots – pick/place, welding
* Scanners/Barcode devices
* Printers – batch/label printing

### Communication Protocols

* Modbus (serial/Ethernet)
* Profibus
* Profinet
* Ethernet/IP
* DeviceNet

## 7. Most Important MCQ Points

* PLC = Programmable Logic Controller
* CPU executes ladder/FBD programs
* HMI = operator interface
* Fixed PLC = built-in I/O
* Modular PLC = expandable
* DI/DO = ON/OFF signals
* AI/AO = analog continuous signals
* VFD controls motor speed
* Modbus = common PLC communication protocol

---

# UNIT–2: SCADA (Supervisory Control & Data Acquisition) — ONE PAGE REVISION NOTES

## 1. What is SCADA?

SCADA = Supervisory Control + Data Acquisition
System used for monitoring, controlling, collecting, and analyzing industrial process data across wide or distributed locations.

Used in: Power systems, Water treatment, Oil & gas, Manufacturing, HVAC, Pipelines.

## 2. SCADA System Components

1. MTU (Master Terminal Unit)

   * Central SCADA server
   * Supervisory control, data logging, processing, trending

2. RTU (Remote Terminal Unit)

   * Located in remote fields
   * Collects data from sensors
   * Sends to MTU via communication link
   * Can do basic control
   * Low power, outdoor use

3. PLC

   * Local control; often used instead of RTU for fast logic

4. HMI

   * Operator interface
   * Displays process graphics, trends, alarms

5. Communication Network

   * Ethernet, Optical fiber, Radio, GSM, Satellite
   * Protocols: Modbus, DNP3, IEC 60870-5-104

6. Field Devices

   * Sensors, actuators, meters, transmitters

## 3. SCADA Architectures (Types)

1. Standalone SCADA – Single PC, small systems
2. Client–Server SCADA – Multiple operator stations, central server
3. Distributed SCADA – LAN-based, multiple nodes
4. Networked/Web-based SCADA – Cloud/IoT, remote & mobile access

## 4. Applications of SCADA

* Power transmission & distribution
* Water supply & sewage treatment
* Oil & gas pipelines
* Manufacturing plants
* Transportation systems
* Building management (HVAC)

## 5. Benefits of SCADA

* Remote monitoring & control
* Real-time data visualization
* Reduced operator workload
* Improved safety via alarms
* Data logging & reports
* Enhanced decision-making

## 6. Trending & Historical Data

### Trending

* Graphical display of real-time process values
* Used for monitoring & quick decisions

### Historical Data

* Long-term data stored in:

  * SQL databases
  * SCADA Historians (OSI-PI, Wonderware)
* Used for reports, analytics, performance optimization

## 7. Alarm Management

Alarms indicate abnormal conditions.

Types: High, Low, Critical, Warning, System alarms
Properties: Priortization, timestamping, acknowledgement

Used for safety, diagnosis, preventive actions.

## 8. PLC vs RTU vs SCADA (Key Differences)

| Parameter   | PLC                | RTU                    | SCADA               |
| ----------- | ------------------ | ---------------------- | ------------------- |
| Main use    | Fast local control | Remote data collection | Supervisory control |
| Area        | Small              | Wide-area/remote       | Multiple sites      |
| Power       | High               | Low                    | Depends             |
| Environment | Indoors            | Harsh outdoor          | Server-based        |

## 9. Development of SCADA Application

1. Create process screens (mimics)
2. Add tags/variables
3. Configure communication (PLC/RTU)
4. Set alarms
5. Set real-time & historical trends
6. Enable data logging
7. Test and deploy

## MOST IMPORTANT MCQ POINTS

* SCADA = monitoring + data acquisition
* RTU = remote outdoor unit, low power
* PLC can replace RTU for local fast control
* MTU is the brain of SCADA
* Trends show real-time data; Historians store long-term data
* Modbus / DNP3 / IEC 60870-5-104 = common SCADA protocols
* Client–server architecture is widely used
* SCADA ≠ DCS ≠ PLC (different levels)

---

# UNIT–5: DISTRIBUTED CONTROL SYSTEM (DCS)

### One-Page Revision Notes

## 1. What is DCS?

A Distributed Control System (DCS) is an industrial automation system where control is distributed across multiple controllers located throughout the plant, connected via a high-speed communication network.

Used for: Continuous processes → Oil & gas, Chemical, Power plants, Pharma, Water treatment.

## 2. Functions of DCS

* Process Control (PID, cascade, ratio control)
* Data Acquisition (sensor readings, analog inputs)
* Monitoring & Visualization (HMI screens)
* Alarms & Events
* Recipe & Batch Control
* Historical Data Logging
* Plantwide Coordination
* Real-time Communication

## 3. DCS Architecture (Layers)

### 1. Field Level

* Sensors (RTD, pressure, flow)
* Actuators (valves, pumps, motors)

### 2. Control Level

* DCS Controllers / Processors
* Execute PID loops & logic
* Redundant controllers supported

### 3. Supervisory Level

* Operator Stations / HMI
* Alarm logs, trends, graphical interface

### 4. Information Level

* Servers (Historian, Database)
* MES / ERP integration
* Reports & analytics

Key Components:

* I/O Modules (DI/DO/AI/AO)
* Engineering Stations
* Redundant networks (Ethernet, Fieldbus, Profibus)

## 4. Features of DCS

* Distributed control (not centralized)
* High reliability & redundancy
* Real-time operation
* Scalable & modular
* Centralized monitoring
* Advanced control support
* Secure communication
* Better process quality

## 5. Specifications of DCS

* I/O capacity
* Controller scan time
* Communication protocol (Profibus, Modbus, Fieldbus, HART)
* Redundancy features (dual CPU, dual network)
* Environmental rating
* Supported programming languages (FBD, ST, function blocks)

## 6. Advantages
 High reliability Fault tolerance (redundant components) Easy expansion and maintenance Excellent for large process industries Consistent product quality Lower downtime

## 7. Limitations

✘ High cost
✘ Complex installation
✘ Vendor dependent (proprietary systems)
✘ Requires skilled manpower
✘ Not ideal for small machines

## 8. Applications

* Petrochemical & chemical plants
* Power generation plants
* Oil refineries
* Food & beverage processing
* Pharmaceuticals
* Pulp & paper mills
* Cement plants
* Water treatment plants

## 9. Comparison Table (Very Important!)

### DCS vs PLC

| Aspect      | DCS                        | PLC                 |
| ----------- | -------------------------- | ------------------- |
| Use         | Process control            | Machine control     |
| Area        | Plant-wide                 | Local               |
| Control     | Continuous                 | Discrete/logic      |
| Response    | Slower                     | Very fast           |
| Reliability | High                       | Medium              |
| Cost        | High                       | Low                 |
| Application | Refineries, power stations | Packaging, robotics |

### DCS vs SCADA

| Aspect   | DCS                | SCADA                       |
| -------- | ------------------ | --------------------------- |
| Control  | Real-time          | Supervisory                 |
| Area     | Single plant       | Large geographic area       |
| Response | Fast               | Slow                        |
| Used for | Continuous process | Monitoring & remote control |
| Example  | Chemical plant     | Power grids, pipelines      |

---

# UNIT–2: BASIC PLC PROGRAMMING — ONE PAGE REVISION NOTES

## 1. PLC Programming Languages (IEC 61131-3)

### Graphical Languages

1. Ladder Diagram (LD)

   * Most widely used
   * Contacts, coils, timers, counters
   * Similar to relay logic

2. Functional Block Diagram (FBD)

   * Blocks interconnected by lines
   * Used for PID, math, timers, counters

3. Sequential Function Chart (SFC)

   * Step → Transition based
   * Used in sequential/batch processes

### Textual Languages

4. Instruction List (IL) *(obsolete)*
   Example:

   ```
   LD A
   AND B
   OUT C
   ```

5. Structured Text (ST)
   High-level language (Pascal-like)
   Example:

   ```
   IF A AND B THEN C := TRUE; END_IF;
   ```

## 2. Ladder Logic Basics (LD)

Elements:

* NO Contact → true when input ON
* NC Contact → true when input OFF
* Coil (Output)
* Series = AND
* Parallel = OR

### Boolean Logic in Ladder

* AND Gate: Series contacts
* OR Gate: Parallel contacts
* NOT Gate: NC contact
* NAND/NOR/XOR: Combinations

## 3. Timers

### Types of Timers

1. TON (On-Delay Timer)

   * Output ON after preset delay when input = ON

2. TOFF (Off-Delay Timer)

   * Output OFF after delay when input turns OFF

3. TP (Pulse Timer)

   * Generates fixed ON pulse

### Timer Parameters

* PT = Preset time
* ET = Elapsed time
* DN = Done bit (timer complete)

## 4. Counters

### Types

1. CTU – Count Up
2. CTD – Count Down
3. CTUD – Up/Down Counter

### Counter Parameters

* PV = Preset value
* CV = Current value
* DN = Done bit
* RES = Reset

### Counter Applications

* Bottle counting
* Object counting
* Batch process
* Conveyor product counting

## 5. Functional Block Diagram (FBD)

Common blocks:

* AND, OR, NOT
* ADD, SUB
* TON, TOFF, TP
* CTU, CTD
* PID blocks
* Comparators (>, <, =)

## 6. Structured Text (ST)

Used for:

* Math calculations
* Complex conditions
* Loops
* Data processing

Example:

```
IF Temp > 80 THEN
    Fan := TRUE;
END_IF;
```

## 7. Sequential Function Chart (SFC)

Used for sequential or batch operations:
Example sequence:
Start → Fill → Heat → Mix → Drain → Stop

Components:

* Steps
* Transitions
* Actions

## 8. Applications of Timers & Counters

Timer Applications:

* Delayed motor start
* Heater warm-up time
* Alarm delay
* Cooling cycle timing

Counter Applications:

* Bottle filling count
* Packaging line count
* Lift floors count
* Batch quantity control

## 9. Most Important MCQ Points

* LD is the most common PLC language
* Series → AND, Parallel → OR
* TON = ON delay, TOFF = OFF delay
* CTU increments, CTD decrements
* IL is a low-level, deprecated language
* ST is high-level like Pascal
* SFC = step-transition charts

---

# UNIT–3: ADVANCED PLC PROGRAMMING & INTERFACING

## 1. Arithmetic & Logical Instructions

### Arithmetic

* ADD – Addition
* SUB – Subtraction
* MUL – Multiplication
* DIV – Division
* MOD – Remainder
* INC / DEC – Increment/Decrement

### Logical

* AND, OR, NOT, XOR, NAND, NOR
  Used for conditional control and decision-making.

## 2. Comparison Instructions

Used to compare values:

| Operator | Meaning          |
| -------- | ---------------- |
| ==       | Equal            |
| !=       | Not Equal        |
| >        | Greater          |
| <        | Less             |
| >=       | Greater or Equal |
| <=       | Less or Equal    |

Examples of usage:

* Level > Setpoint → Pump ON
* Temperature < 30°C → Heater ON

## 3. Data Handling Instructions

* MOV → Move data
* COP → Copy block
* SWAP → Swap bytes/words
* CONVERT → INT ⇄ REAL
* MASK → Bit masking
* SHL / SHR → Shift Left / Right

### Common Data Types

* BOOL
* INT
* DINT
* REAL
* Timer/Counter structures

## 4. Analog I/O (Very Important)

### Analog Input Examples

* Temperature (4–20 mA, 0–10 V)
* Pressure transmitters
* Flow transmitters
* Level sensors

### Analog Output Examples

* Valve position
* Motor speed (via VFD)
* Heater power

### Signal Ranges

* 0–10 V
* ±10 V
* 4–20 mA (most widely used)
* 0–20 mA

### ADC/DAC Resolution

* 8-bit → 256 steps
* 12-bit → 4096 steps
* 16-bit → 65,536 steps

## 5. Scaling (Engineering Units Conversion)

Used to convert raw analog data → actual value.

Example:
Raw 3277–16384 (4–20 mA) → 0–100°C

## 6. Special Functions

### PID Control Block

Used in continuous processes.

Components:

* P → immediate correction
* I → accumulated correction
* D → predictive correction

Applications:
Temperature, pressure, level, flow control.

### Math Blocks

* SIN, COS, TAN
* SQRT
* LOG

## 7. PLC Communication

### Communication Protocols

* Modbus RTU/TCP
* Profibus
* Profinet
* Ethernet/IP
* DeviceNet
* CANopen
* RS-232 / RS-485

### Communication Enables

* PLC ↔ HMI
* PLC ↔ VFD
* PLC ↔ SCADA
* PLC ↔ Robots
* PLC ↔ PLC

## 8. PLC–HMI Interfacing

### Steps:

1. Create tags in PLC
2. Assign addresses
3. Configure protocol (Modbus/Profinet/Ethernet/IP)
4. Create HMI screens
5. Link screen objects → PLC tags
6. Download program

### HMI Objects:

Buttons, indicators, text display, bar graph, numeric entry, alarms, trends.

## 9. PLC–VFD Interfacing

### Methods:

1. Digital I/O – Start/Stop, Fault
2. Analog I/O – Speed control (0–10V / 4–20mA)
3. Communication – Advanced control (Modbus, Profibus, Ethernet/IP)

## 10. PLC Program Control Instructions

* JMP – Jump
* LBL – Label
* CALL / SUB – Call subroutine
* RET – Return

Used for large, modular, structured programs.

# Most Important MCQ Points

* ADD/SUB/MUL/DIV used for math operations
* Comparison block used for decision-making
* 4–20 mA is the most common analog signal
* 12-bit resolution → 4096 steps
* PID = Proportional + Integral + Derivative
* Modbus RTU/TCP widely used for PLC networking
* Analog inputs need scaling
* PLC ↔ HMI uses tags + communication protocol
* PLC ↔ VFD via I/O or communication

---