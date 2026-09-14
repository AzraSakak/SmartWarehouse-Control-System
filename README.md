# SmartWarehouse Control System

A PLC-based automated storage and retrieval system developed in CODESYS as an industrial automation project.

The project simulates the control of a smart warehouse using PLC logic, warehouse management algorithms, an HMI, and a simulated Cartesian stacker robot.

## Features

- 4 × 4 warehouse rack structure
- 3 pallet positions per rack location
- Total capacity of 48 pallet positions
- Product ID-based storage management
- Dedicated rack assignment for each Product ID
- Automatic search for available pallet positions
- 5-position Waiting Area for products whose assigned rack is full
- Automatic relocation from the Waiting Area when a pallet position becomes available
- STORE and RETRIEVE operations
- Single-pallet retrieval
- Simulated Cartesian stacker robot with X, Y and Z positioning
- HOME and RESET functions
- System START and STOP controls
- Warehouse and Waiting Area capacity monitoring
- HMI-based system control and real-time monitoring
- Basic fault and operating-state monitoring

## System Architecture

The control system is divided into several functional modules:

- **Warehouse Manager**  
  Handles Product ID-based rack assignment, storage, retrieval, warehouse capacity and Waiting Area management.

- **Stacker Robot**  
  Simulates Cartesian X, Y and Z movement between warehouse pallet positions.

- **Pick/Drop Station**  
  Controls the sequence between the conveyor, product detection and pneumatic cylinder operations.

- **Motor and Conveyor Control**  
  Provides reusable motor control and conveyor operation logic.

- **Pneumatic Cylinder Control**  
  Includes extend/retract control, sensor feedback, interlocking and timeout-based fault detection.

- **HMI**  
  Provides operator controls and real-time visualization of the warehouse, Waiting Area and stacker robot status.

## Warehouse Logic

Each warehouse rack location can contain up to three pallets of the same Product ID.

Different Product IDs are not mixed within the same rack location.

When a new product arrives:

1. The system searches for an existing rack assigned to the same Product ID.
2. If an available pallet position exists, the product is stored in that position.
3. If no rack has been assigned to the Product ID, an empty rack location is assigned.
4. If the assigned rack is full, the product is transferred to the Waiting Area.
5. When a pallet position becomes available again, an eligible product in the Waiting Area is automatically relocated to its assigned rack.

## HMI

The CODESYS Visualization interface provides:

- START / STOP control
- STORE operation with Product ID input
- RETRIEVE operation with Product ID input
- 48 pallet position monitoring
- 5-position Waiting Area monitoring
- Warehouse availability status
- Waiting Area availability status
- Stacker X / Y / Z position monitoring
- Busy, Homed and Fault status indicators
- HOME and RESET controls

## Technologies

- CODESYS V3.5
- IEC 61131-3
- Structured Text (ST)
- Ladder Diagram (LD)
- CODESYS Visualization
- PLC Function Blocks
- State Machine / Sequential Control Logic

## Project File

The complete CODESYS project is available as:

`SmartWarehouse_ASRS.project`

## Project Status

The control logic and HMI were developed and functionally tested using the CODESYS runtime environment.

The stacker robot and warehouse processes are simulated in software. The SmartWarehouse system has not been implemented as a physical warehouse installation.

## Author

Azra Sakak  
