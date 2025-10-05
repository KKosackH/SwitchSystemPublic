# SwitchSystem  

The **SwitchSystem** PCB was developed as an *add-on discharging solution* for existing **AC home chargers**.  

Although the concept worked, the product was ultimately deemed too **expensive** for production. As a result, the design has been made publicly available.  

All major components were tested and verified functional, including the **HomePlug Green PHY (PLC communication)** with negligible switching losses. However, the PCB was not fully finalized — see the [TO-DO](#to-do) list below for pending improvements.  

---

## Features  
- **Discharging add-on** for existing AC chargers  
- **PLC communication** via HomePlug Green PHY  
- **Integration with Raspberry Pi** through a 2×20 GPIO connector  
- **BatteryBridge compatibility** via JST connector  
- **External I/O**: LCD screen and buttons via JST  
- **Vehicle interface**: IEC 62196 Type 2 AC plug with temperature sensor and lock  
- **Inverter interface**: CANBus development board mounted on Raspberry Pi  

---

## Design Notes  
- The board was later split into multiple PCBs to:  
  - Avoid routing **AC mains** directly onto the main board  
  - Reduce **EMI issues**  
- The newer versions (under NDA) added advanced features such as:  
  - **LTE Cat 4 module**  
  - **CANBus support**  
  - **AMD Xilinx Zynq 7000 SoC**  

> ⚠️ If using the **BatteryBridge v2**, remove the `[3.4] DC-DC converter` and patch the **12 V output** of the BatteryBridge to the 12 V net on the SwitchSystem PCB.  

A full circuit description is available in the [Documentation folder](./Documentation).  

---

## Schematic & PCB  

The schematic is organized using hierarchical sheets, with the root page showing all user-interactable components.  

- **First page schematic**  
  ![Schematic Overview](https://github.com/KKosackH/SwitchSystem/blob/main/Documentation/Sch_PCB/KicadSchOverview.png)  

- **PCB Front**  
  ![PCB Front](https://github.com/KKosackH/SwitchSystem/blob/main/Documentation/Sch_PCB/PCBOverview.png)  

- **PCB Back**  
  ![PCB Back](https://github.com/KKosackH/SwitchSystem/blob/main/Documentation/Sch_PCB/backSidePCB.png)  

---

## TO-DO  
Remaining improvements for the PCB design:  

1. Add node names to all nets  
2. Ensure all schematic symbols have correct naming  
3. Add transfer vias  
4. Match SPI line lengths  
5. Change BatteryBridge connector to flat-flex  
6. Add new ADC and connect to motor measurement  
7. Add color coding for cables on PCB  
8. Add low-pass filter to CPRead ADC  
9. Add protected earth connector  
10. Add default charge state for power-loss events  
11. Adjust PCB size for mechanically stable Raspberry Pi mounting  

---
