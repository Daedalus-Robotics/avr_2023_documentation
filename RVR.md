```mermaid
---
title: Daedalus AVR 2023 RVR Systems Graph
---
flowchart LR

    subgraph manual[Manual Control]
        direction RL
        subgraph laptop[Laptop]
            keyboard[Keyboard Input]
        end

        subgraph rvr[RVR]
            move[Move Drone]
        end
    
        keyboard --> move

    end

    subgraph cru[Civilian Recovery Unit]
        direction RL

        subgraph arvr[on RVR]
            rvrbit[RVR Microbit]
        end

        subgraph drive[with Driver]
            driverbit[Driver Microbit]
        end

        driverbit --- rvrbit --> servo[Box Servo]
        

    end

    subgraph reconpath[Autonomous Recon Path]
        direction TB

        subgraph blaptop[Laptop]
            rp[Recon Path Algorithm]
        end

        subgraph brvr[RVR]
            rp --> bmove[Move Rover]
            gyro[Gyroscopic Data] --> rp
        end 

    end

    


  


```
