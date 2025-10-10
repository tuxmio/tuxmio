TUXMIO Mainboard Classification
┌──────────────┬──────────────────────────────┬────────┬──────────────────────────────────────────────────────────────────────────────┐
│ Directory    │ Full Name                    │ Level  │ Description                                                                  │
├──────────────┼──────────────────────────────┼────────┼──────────────────────────────────────────────────────────────────────────────┤
│ L0-MB-PML    │ Power Management Layer       │ L0     │ Handles power entry, conversion, and protection (fuse, surge, polarity).     │
│              │                              │        │ Supplies regulated voltages to upper layers.                                 │
├──────────────┼──────────────────────────────┼────────┼──────────────────────────────────────────────────────────────────────────────┤
│ L1-MB-CIM    │ Controller Interface Module  │ L1     │ Hosts the main controller (MCU, SBC, or SoM). Manages logic, communication   │
│              │                              │        │ and links between the power and I/O layers.                                  │
├──────────────┼──────────────────────────────┼────────┼──────────────────────────────────────────────────────────────────────────────┤
│ L2-MB-IOP    │ Input/Output Peripherals     │ L2     │ Provides interface for I/O boards, sensors, and actuators. Includes sockets  │
│              │                              │        │ for I/O boards. each socket only supports specific I/O board types           │
└──────────────┴──────────────────────────────┴────────┴──────────────────────────────────────────────────────────────────────────────┘
 
   ┌┐   ┌┐   ┌┐   ┌┐   ┌┐   ┌┐   ┌┐   
   ||   ||   ||   ||   ||   ||   ||
   ||   ||   ||   ||   ||   ||   ||  ← I/O Boards
   ||   ||   ||   ||   ||   ||   ||
   └┘   └┘   └┘   └┘   └┘   └┘   └┘   
   ┌──────────────────────────────┐
   │  L2 – MB-IOP  (Peripherals)  │  ← I/O Expansion Layer
   └─────────────┬────────────────┘
                 │
   ┌─────────────┴────────────────┐
   │  L1 – MB-CIM  (Controller)   │  ← Processing & Communication Layer
   └─────────────┬────────────────┘
                 │
   ┌─────────────┴────────────────┐
   │  L0 – MB-PML  (Power)        │  ← Power & Protection Base Layer
   └──────────────────────────────┘
