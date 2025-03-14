# Power Distribution Setup

## Overview
The power distribution system for the home server is designed to ensure **stable, efficient, and reliable** power delivery to all components. Since Raspberry Pis and other devices require different voltages, a custom solution has been implemented to step down voltage appropriately while maintaining stability.

## Power Source
- **450W ATX Power Supply (SMPS)** – Provides multiple voltage outputs:
  - **12V Rail** (Primary Power Source)
  - **5V Rail** (Found to be unstable for direct Raspberry Pi power)
  - **3.3V Rail** (Not used in this setup)

## Power Conversion
Due to instability in the 5V rail of the ATX power supply, the **12V output is stepped down** to 5V using a **DC-DC Buck Converter** for a more stable power source.
![Unstable supply](images/Fluctuating5V-Supply.mp4)

### Voltage Regulation
- **Step-Down Converter (12V to 5V, 5A rated)** 
  - Provides stable 5V for Raspberry Pi boards.
  - Ensures consistent power delivery, preventing undervoltage issues.
  
## Power Distribution
The system distributes power efficiently to different components:

| Component               | Voltage Required | Power Source                     |
|-------------------------|-----------------|----------------------------------|
| **Raspberry Pi 3B**    | 5V              | Step-down converter (12V → 5V)  |
| **Raspberry Pi 5**     | 5V              | Step-down converter (12V → 5V)  |
| **Cooling Fans (x4)**  | 12V             | Direct from ATX PSU (12V rail)  |
| **1TB HDD (NAS)**      | 12V & 5V        | Direct from ATX PSU             |
| **MikroTik Switch**    | 12V             | Direct from ATX PSU             |

![Circuit Diagram](images/PowerDistributionCircuit.pdf)

## Fuse Unit
Fuse units are also installed to keep a check on the current drawn by each of the components.

| Component               | Max Current |
|-------------------------|-----------------|
| **Raspberry Pi 3B**    | 3A              |
| **Raspberry Pi 5**     | 5A              |
| **MikroTik Switch**    | 1A             |

## Cooling & Heat Management
The power system includes **four cooling fans** to maintain stable temperatures:
- **2 Intake Fans** (Pull cool air inside)
- **2 Exhaust Fans** (Remove hot air)
- Fans are powered directly from the **12V rail** of the ATX PSU.

## Future Improvements
- **Test alternative step-down converters** for better efficiency.
- **Monitor power consumption** using smart power meters.
- **Consider a UPS (Uninterruptible Power Supply)** for backup power.

This setup ensures a stable power supply, reducing the risk of voltage drops and overheating while keeping all components running efficiently.
