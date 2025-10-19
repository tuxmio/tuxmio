Socket–Board compatibility is non-commutative.

> a board designed for Socket A may fit Socket B, but not necessarily vice-versa.

Final (refined) socket acronyms
#	Acronym	   Cards        Full Name	            Description
0	GPP	       DI/DO/AO     General Purpose Pin	    Multi-use socket — supports digital input/output and analog output. Default I/O connection.
1	AIP	       AI           Analog Input Pin	    Dedicated analog input socket for sensors (voltage, current, RTD, etc.).
2	URP	       Serial COM   UART Pin	            Serial communication socket — TX/RX pair for asynchronous data.
3	ICP	       I²C          I²C Pin	                Two-wire serial communication socket — SCL/SDA lines for intelligent peripherals.

Compatibility Matrix
┌───────────────┬─────┬─────┬─────┬─────┐
│ Board \ Socket│ GPP │ AIP │ URP │ ICP │
├───────────────┼─────┼─────┼─────┼─────┤
│ GPP           │  ✓  │  ✓  │  ✓  │  ✓  │
│ AIP           │     │  ✓  │     │  ✓  │
│ URP           │     │     │  ✓  │     │
│ ICP           │     │     │     │  ✓  │
└───────────────┴─────┴─────┴─────┴─────┘

🧩 Physical Connection System

All TUXMIO sockets and boards use 2.54 mm pitch pin header–type connectors for electrical and mechanical connection.
Sockets are equipped with female pin headers, while the I/O boards use corresponding male pin headers.
To ensure correct insertion and prevent incompatible combinations, certain holes in the socket connectors are mechanically blocked using plastic plugs, and matching pins are omitted on the corresponding boards.
This selective pin arrangement allows each board to fit only into its appropriate socket type, maintaining both electrical safety and system integrity.
Additionally, all connectors are polarized — boards cannot be inserted rotated 180°, preventing reverse connection or damage to components.For detailed socket–board relationships, For detailed socket–board relationships, please see the compatibility matrix.


Legend (for the table)
Sockets: o = empty hole, x = plugged hole
I/O Boards: - = pin present, x = pin absent

┌────────────┬───────────────────────┬───────────────────────────┬───────────────────────────┐
│            │                       │         Sockets           │        I/O Boards         │
│ Pin Number │ Function              ├──────┬──────┬──────┬──────┼──────┬──────┬──────┬──────┤
│            │                       │ GPP  │ AIP  │ URP  │ ICP  │ GPP  │ AIP  │ URP  │ ICP  │
├────────────┼───────────────────────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┼──────┤
│ 1          │ IO pin to uC          │ o    │ o    │ o    │ o    │  -   │  -   │  -   │  -   │IO
│ 2          │ A_REF pin from uC     │ x    │ o    │ x    │ o    │  x   │  -   │  x   │  -   │A_Ref
│ 3          │ GND or GND1(seperated)│ o    │ o    │ o    │ o    │  -   │  -   │  -   │  -   │GND1
│ 4          │ N/A                   │ o    │ x    │ o    │ o    │  x   │  x   │  -   │  -   │N/A
│ 5          │ Diagnostics for future│ o    │ o    │ o    │ o    │  -   │  -   │  -   │  -   │Diag
│ 6          │ -10V bipolar          │ o    │ o    │ o    │ o    │  -   │  -   │  -   │  -   │-10V_b
│ 7          │   OV bipolar          │ o    │ o    │ o    │ o    │  -   │  -   │  -   │  -   │0V_b
│ 8          │ +10V bipolar          │ o    │ o    │ o    │ o    │  -   │  -   │  -   │  -   │+10V_b
│ 9          │ Not assigned yet      │ o    │ o    │ o    │ o    │  -   │  -   │  -   │  -   │N/A_Pin_9
│ 10         │ N/A                   │ x    │ x    │ o    │ x    │  x   │  x   │  -   │  x   │N/A
│ 11         │ +24VDC                │ o    │ o    │ o    │ o    │  -   │  -   │  -   │  -   │+24VDC
│ 12         │ GND from 24V          │ o    │ o    │ o    │ o    │  -   │  -   │  -   │  -   │GND_24V
└────────────┴───────────────────────┴──────┴──────┴──────┴──────┴──────┴──────┴──────┴──────┘
