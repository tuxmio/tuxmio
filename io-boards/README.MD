┌──────┬────────────┬───────────┬─────────────────────────────────────────────┬───────────────────────────────────────────────────────────────────────────────┐
│ Code │ Complexity │ Priority  │ Description                                 │ Notes                                                                         │
├──────┼────────────┼───────────┼─────────────────────────────────────────────┼───────────────────────────────────────────────────────────────────────────────┤
│ DI   │ 0          │ 1         │ Direct digital input (NPN/PNP stabilized)   │ Simple design, direct to MCU or buffer input.                                 │
│ DI   │ 4          │ -         │ Differential digital input (super-fast OC)  │ High-speed differential inputs, open-collector tolerant.                      │
│ DI   │ 2          │ -         │ Optocoupled digital input (NPN/PNP)         │ Isolated voltage sensing, moderate complexity.                                │
│ DO   │ 0          │ 1         │ Direct digital output (NPN/PNP stabilized)  │ Transistor-based output, low-side/high-side variants possible.                │
│ DO   │ 2          │ -         │ Optocoupled digital output (short-prot.)    │ Protected, diagnostic LEDs, block on short.                                   │
│ DO   │ 4          │ -         │ Super-fast optocoupled digital output       │ High-speed driver, isolation + diagnostics.                                   │
│ DO   │ 4          │ -         │ Differential digital output (OC)            │ Fast differential output, open-collector style.                               │
│ DO   │ 1          │ 2         │ Relay output                                │ Mechanical relay, user-changeable type.                                       │
│ DO   │ 1          │ 2         │ SSR relay output                            │ Solid State Relay variant.                                                    │
│ AI   │ 0          │ 1         │ Direct analog input 0–5V                    │ Basic ADC interface.                                                          │
│ AI   │ 1          │ -         │ 0–10V analog input                          │ Most common industrial input range.                                           │
│ AI   │ 2          │ -         │ ±10V analog input                           │ Bipolar measurement range.                                                    │
│ AI   │ 4          │ 5         │ 0–5mA analog input                          │ Requires precise current sensing, maybe external supply.                      │
│ AI   │ 4          │ 5         │ 0–20mA analog input                         │ Current loop sensing, possibly needs shunt resistor.                          │
│ AI   │ 4          │ 5         │ Low-voltage 0–10mV analog input             │ For small-signal sensors, instrumentation amp required.                       │
│ AI   │ 3          │ 5         │ Thermocouple input                          │ Requires CJC, precision ADC, low noise.                                       │
│ AI   │ 3          │ 5         │ RTD input (PT100/PT1000)                    │ Requires excitation and bridge measurement.                                   │
│ AO   │ 0          │ 1         │ Direct analog output 0–5V                   │ Simple DAC output.                                                            │
│ AO   │ 2          │ 2         │ 0–10V analog output                         │ Standard industrial output range.                                             │
│ AO   │ 2          │ 5         │ ±10V analog output                          │ Bipolar DAC driver, requires dual supply.                                     │
│ AO   │ 4          │ 3         │ 0–20mA analog output                        │ Current loop output, supply-dependent.                                        │
└──────┴────────────┴───────────┴─────────────────────────────────────────────┴───────────────────────────────────────────────────────────────────────────────┘

Enhanced I/O Function Table with ABC Codes
#	Old Code	New Code	Description	Notes / Feature keywords
1	DI	DID	Direct Digital Input (NPN/PNP stabilized)	simplest form, direct connection
2	DI	DIF	Differential Digital Input (superfast OC)	high-speed, open-collector compatible
3	DI	DIO	Optocoupled Digital Input (NPN/PNP voltage)	isolated, standard industrial input
4	DO	DOD	Direct Digital Output (NPN/PNP stabilized)	simple transistor output
5	DO	DOO	Optocoupled Digital Output (short-prot, diag)	isolated, protected, LED indicators
6	DO	DOF	Fast Optocoupled Digital Output (superfast)	high-speed variant
7	DO	DOH	Differential (High-speed OC) Digital Output	OC differential drivers
8	DO	DOR	Relay Output (mechanical relays)	changeable relay sockets
9	DO	DOS	SSR Output (Solid-State Relay)	solid-state version
10	AI	AIV	Analog Voltage Input (0–5V, 0–10V, ±10V)	voltage-based measurement
11	AI	AIC	Analog Current Input (0–5mA, 0–20mA)	current loop or shunt measurement
12	AI	AIL	Low-Voltage / Millivolt Input	instrumentation, low-noise sensors
13	AI	AIT	Thermocouple Input	temperature, requires CJC
14	AI	AIR	Resistance / RTD Input (PT100/PT1000)	with excitation and linearization
15	AO	AOV	Analog Voltage Output (0–5V, 0–10V, ±10V)	DAC-based voltage output
16	AO	AOC	Analog Current Output (0–20mA)	current loop output
17	COM	CCI	Communication Interface Input (e.g., RS, CAN)	receives data
18	COM	CCO	Communication Interface Output	transmits data
19	COM	CCX	Communication Transceiver / Bidirectional	bidirectional (e.g., RS485, CAN, I²C)



1st letter: Domain
D → Digital
A → Analog
C → Communication

2nd letter: Direction
I → Input
O → Output
X → Bidirectional / mixed

3rd letter: Feature

D = Direct
O = Optocoupled
F = Fast / Differential
R = Relay
S = Solid State
V = Voltage
C = Current
L = Low voltage / millivolt
T = Thermocouple
R = RTD (resistance sensor)
H = High-speed / OC
X = Mixed / special

┌────────────┬───────────┬───────────────────────────────────────────────┐
│ Letter Pos │ Represents│ Example Letters / Meaning                     │
├────────────┼───────────┼───────────────────────────────────────────────┤
│ 1st        │ Domain    │ D = Digital, A = Analog, C = Communication    │
│ 2nd        │ Direction │ I = Input, O = Output, X = Bidirectional      │
│ 3rd        │ Feature   │ D = Direct, O = Optocoupled, F = Fast,        │
│            │           │ R = Relay, S = Solid-state, V = Voltage,      │
│            │           │ C = Current, L = Low-voltage, T = TC, R = RTD │
└────────────┴───────────┴───────────────────────────────────────────────┘

<ABC>-<LS>-<PT>-<RPO>-Vx.xx

where:
ABC = 3-letter functional code = [Domain][Direction][Feature]
    Domain: A = Analog, D = Digital (use “Digital”), C = Communication
    Direction: I = Input, O = Output, X = Bidirectional
    Feature: domain-specific (e.g. D=Direct, O=Optocoupled, F=Fast/Differential, R=Relay, S=SolidState, V=Voltage, C=Current, L=Low-voltage, T=Thermocouple, R=RTD, H=High-speed, X=Mixed)
LS = two digits: [LogicLevel][SocketType]
    LogicLevel (first digit): 3 = 3.3 V logic, 5 = 5 V logic, 9 = Mixed/Auto/Dual
    SocketType (second digit): 0 = Socket A, 1 = Socket B, 2 = Socket C, 3 = Socket D
PT = Peripheral Type (single letter)
    U = Voltage-type peripheral
    C = Current-type peripheral
RPO = Range code + Peripheral Option (two chars)
Range code (digit): Voltage codes (for U)
    0 = sink-mode NPN (logic sink)
    1 = 3.3/5 V logic-level field
    2 = 10 V
    3 = 12 V
    4 = 15 V
    5 = 24 V
    6 = 230 VAC
Range code (digit): Current codes (for C)
    0 = 0–5 mA
    1 = 0–20 mA
    2 = 4–20 mA
    3 = −20 mA … +20 mA
Peripheral Option (letter, immediately after range digit):
    N = Sink mode (NPN)
    P = Source mode (PNP)
    B = Bipolar
Vx.xx = Version (major.minor) e.g. V0.01
