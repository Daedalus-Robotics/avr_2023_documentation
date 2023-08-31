```mermaid
---
title: AVR Ros2 Diagnostics Graph
---
stateDiagram-v2
    direction LR
    
    classDef topic color:white;
    
    state Abstractions{
        CSI_Abstraction
        MAVROS
        PCC
        Gimbal_Controller
        Thermal_Camera
        ZED
        
    }
    
    state GUI{
        RQT
    }
    
    ZED --> DIAGNOSTICS : publishes
    CSI_Abstraction --> DIAGNOSTICS : publishes
    MAVROS --> DIAGNOSTICS : publishes
    PCC --> DIAGNOSTICS : publishes
    Gimbal_Controller --> DIAGNOSTICS : publishes
    Thermal_Camera --> DIAGNOSTICS : publishes
    DIAGNOSTICS:::topic --> Diagnostics_Aggregator : subscribes
    Diagnostics_Aggregator --> DIAGNOSTICS_AGGREGATOR : publishes
    Status_Node --> Status_Lights_Abstraction : controls-via-service
    Status_Node --> DIAGNOSTICS_AGGREGATOR : publishes
    DIAGNOSTICS_AGGREGATOR --> RQT : subscribes
    DIAGNOSTICS_AGGREGATOR --> RQT : 

```
