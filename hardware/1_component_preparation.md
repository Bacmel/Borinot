# Component Preparation Guide

Some components require modifications before assembling. This guide covers adjustments needed for the power module, brushless motors, and ESCs.

---

## Part 1: Power Module Modification

The Power Module distributes power to all components (computer, motors, arm, flight controller) and monitors battery status via Pixhawk.

### Materials

<img src="../media/1_power_module_exploded.avif" alt="Exploded view of power module components" width="350">

> **Top view: computer cable, power module, masterboard power cable with JST connectors, EC5 connector, XT30-F connector, diode for hot-swap cable, XT30-M connector for microdriver, power cables**

| Part Name             | Quantity | Description                          | Reference                                                                                   |
|-----------------------|----------|--------------------------------------|---------------------------------------------------------------------------------------------|
| PM03D Power Module    | 1        | Base unit                            | [Holybro](https://holybro.com/products/pm03d-power-module)                                  |
| EC5-M Connector       | 1        | Male battery connector               | [TME](https://www.tme.eu/es/en/details/ec5-m/dc-power-connectors/amass/)                    |
| XT30-F Connector      | 1        | Female power connector               | [RC Innovations](https://rc-innovations.es/shop/amass-conector-xt30-hembra-xt30u-h)         |
| XT30-M Connector      | 1        | Male power connector                 | [RC Innovations](https://rc-innovations.es/shop/amass-conector-xt30-macho-xt30u-m)          |
| Diode                 | 1        |                                      | `BQ30TB 45B714`                                                                             |
| Red Power Cable       | 2        | 15cm 16AWG (VCC)                     | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Rojo-1-metro-amass)    |
| Black Power Cable     | 2        | 15cm 16AWG (GND)                     | [RC Innovations](https://rc-innovations.es/shop/cable-de-silicona-26-awg-negro-1-metro)     |
| Computer Cable        | 1        | 24cm barrel plug (5.5×2.5mm)         | [Amazon](https://www.amazon.com/Generic-5-5mm-2-5mm-Right-Pigtail/dp/B07H38LNPD)            |
| Masterboard Cable     | 1        | 17cm line                            |                                                                                             |
| Connector JST         | 1        | Male                                 |                                                                                             |

### Steps
<img src="../media/1_power_module_step_1.avif" alt="Reposition current component" width="350"> <img src="../media/1_power_module_step_1b.avif" alt="Reposition current component" width="350">

> **Top view: EC5 connector and power module prior to battery cable connector replacement**

1. **Unsolder** the capacitor and battery cable from the board.
2. **Replace** the battery cable's connector from XT60 to EC5.
   > :warning: Do not cut the cable to remove the XT60.

   > :warning: Do not hesitate to force when insering the the EC5 terminal inside the case.
3. **Reposition** the capacitor and battery cable so they point **inward** on the board.

<img src="../media/1_power_module_step_2b.avif" alt="Hot swap components" height="350"> <img src="../media/1_power_module_step_2.avif" alt="Hot swap components" height="350">

> **Close view: Finalized hot-swap cable; diode visible at front-right**

4. **Bend** the diode's anode (right leg) to connect with the positive terminal of the XT30-M connector and **solder** it.
5. **Solder** the diode's cathode (left leg) to the positive power cable.
6. **Solder** the negative power cable to the negative terminal of the XT30-M connector.
7. **Add** heat shrink tubing over the connectors and **heat** to seal.  
   > :information_source: This cable will be referred to as the **hot-swap cable**.
8. **Solder** the hot-swap cable to the original battery cable location, keeping the same orientation.

<img src="../media/1_power_module_step_3.avif" alt="Microdriver components" width="350">

> **Close view: Pad for microdriver soldering with corresponding cables and connector**

9. **Solder** both power cables to the XT30 connector (red to positive, black to negative).
10. **Add** heat shrink tubing to seal the connections.  
    > :information_source: This cable will be referred to as the **microdriver cable**.
11. **Solder** the microdriver cable to the pad visible on the picture (red to B+ pad, black to GND pad).
    > :information_source: Put a heat shrink on the connector for manipulation safety.

<img src="../media/1_power_module_step_4.avif" alt="Masterboard components" width="350">

> **Top view: Components for masterboard cable (from right to left: masterboard power cable, JST male connector, JST female connector)**

12. **Cut** the masterboard power cable in half.
13. **Crimp** JST connector onto each cable.
14. **Use** the connector-bearing cable for the [flying arm assembly](6_flying_arm_assembly.md) and the other as the **masterboard cable**.
   > :warning: Be sure to put the connector the correct way to ensure that positive connect to positive. 
15. **Solder** the masterboard cable to the **5V com pin**, ensuring proper polarity (black cable to ground, red cable to 5V).

<img src="../media/1_power_module_step_5.avif" alt="Computer components" width="350">

> **Close view: VDD jumper pins (middle left) and computer cable at servo pin (lower right)**

16. **Set VDD to 12V** using the jumper configuration.
17. **Cut** the computer cable to a **24cm length**.
18. **Solder** the computer cable to the **VDD servo pin**, maintaining correct polarity.

<img src="../media/1_power_module_modified.avif" alt="Modified power module" width="350">

> **Top view: Final modified power module**

---

## Part 2: Brushless Motor and ESC Modification

In this part you’ll modify both the brushless motors and the ESCs. Follow the steps closely to ensure proper electrical connections and maintain correct polarity.

### Materials

<img src="../media/1_brushless_motor_exploded.avif" alt="Exploded view of brushless motor components" width="350">

> **Top view: Components for motor and ESC modification (from top to bottom, left to right: servo connector, ESC, motor, servo pins, power cables, banana plug, XT30-M connector, signal cables)**

| Part Name             | Quantity | Description                          | Reference                                                                                                    |
|-----------------------|:--------:|--------------------------------------|--------------------------------------------------------------------------------------------------------------|
| TMotor F90-1300KV     | 6        | Brushless motor                      | [TMotor](https://store.tmotor.com/goods.php?id=1064)                                                         |
| Banana Plug (male)    | 18       | 3.5 mm, male                         | [RC Innovations](https://rc-innovations.es/shop/con00000438-conector-banana-3-5mm-tipo-tmotor-pareja-18644)  |
| TMotor F35A 6s        | 6        | ESC                                  | [TMotor](https://store.tmotor.com/goods.php?id=1176)                                                         |
| Red Power Cable       | 6        | 30cm Silicone 16 AWG cable in Red     | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Rojo-1-metro-amass)                     |
| Black Power Cable     | 6        | 30cm Silicone 16 AWG cable in Black   | [RC Innovations](https://rc-innovations.es/shop/Cable-silicona-16AWG-Negro-1-metro-amass)                    |
| White Servo Cable     | 6        | 30cm Silicone 26 AWG cable in White   | [RC Innovations](https://rc-innovations.es/shop/Cable-de-silicona-26AWG-blanco-1-metro)                      |
| Black Servo Cable     | 6        | 30cm Silicone 26 AWG cable in Black   | [RC Innovations](https://rc-innovations.es/shop/cable-de-silicona-26-awg-negro-1-metro)                      |
| Banana Plug (female)  | 18       | 3.5 mm, female                       | [RC Innovations](https://rc-innovations.es/shop/con00000438-conector-banana-3-5mm-tipo-tmotor-pareja-18644)  |
| XT30 Connector (male) | 6        | XT30 male connector                  | [RC Innovations](https://rc-innovations.es/shop/amass-conector-xt30-macho-xt30u-m)                           |
| Servo Connector       | 6        | Female                               | [RC Innovations](https://rc-innovations.es/shop/Conector-servo-Futaba-hembra)                                |

### Steps

#### Brushless Motor Modification

<img src="../media/1_motor_step_1.avif" alt="Brushless motor modification" width="350">

> **Top view: Motor and banana plugs (from left to right)**

1. **Trim** the phase cables by about **5cm**.  
   > :warning: Retain the trimmed segments for the ESC modification.
2. **Solder** the male banana plugs to the trimmed phase cables.  
   > :information_source: Use the connector’s side hole to help evenly melt the solder paste.
3. **Add** heat shrink tubing around the connectors to insulate the soldered joints.
4. **Repeat** these steps for all 6 brushless motors.

<img src="../media/1_motor_modified.avif" alt="Modified brushless motor" width="350">

> **Close view: Finalized motor**

#### ESC Modification

<img src="../media/1_esc_step_1.avif" alt="ESC modification" width="350">

> **Close view: ESC faces – Left/Middle ones show pads labeled `–`, `S`, and `T` for signal cables at the bottom left. Right one shows power cable pads at the top; displays phase cable pads at the bottom**

5. **Solder** 5cm of the leftover phase cables from the motors to the ESC’s phase pads.
6. **Attach** the female banana plugs to these phase cables and **add** heat shrink tubing over the connections before heating to seal.
7. **Solder** 30cm power cables to the ESC’s power pads.  
   > :information_source: Connect the red cable to the positive (`+`) pad and the black cable to the negative (`–`) pad.
8. **Slide** heat shrink tubing onto both power cables (do not heat yet).
9. **Solder** the XT30 male connectors to the ends of the power cables.  
   > :warning: Double-check polarity before sealing.
10. **Heat** the tubing to secure the connections.
11. **Solder** 30cm servo cables to the ESC’s servo pads.  
    > :information_source: Attach the white cable to the signal (S) pad and the black cable to the ground (–) pad.
12. **Crimp** the wires and attach the servo connectors.  
    > :warning: Double-check the orientation.
13. **Repeat** the entire ESC modification process for all 6 ESCs.

<img src="../media/1_esc_modified.avif" alt="Modified ESC" width="350">

> **Top view: Finalized modified ESC**

---

[Next → Airframe Assembly](2_airframe_assembly.md)
