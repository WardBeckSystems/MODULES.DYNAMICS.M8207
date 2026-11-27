# M8207 · Dynamics

Ward-Beck Systems M8207, 1995|28. Wiki page: [M8207 on WBSps.ca](https://wardbecksystems.github.io/WBSps.ca/PAGES/M8207.html)

| Folder | What is in it | Files |
|---|---|---|
| [SCHEMATICS/](SCHEMATICS/) | electrical drawings: schematics, functional diagrams, component layouts, wiring | 1 |
| [MECHANICAL/](MECHANICAL/) | front panels, cover plates, metalwork, assemblies; the front panel as vectors | 1 |
| [PINOUTS/](PINOUTS/) | the RTO-144 connector: connection sheets, connector layouts, rear views | 3 |
| [MANUALS/](MANUALS/) | manuals, manual pages, price lists, brochures, documents | 4 |
| [PHOTOS/](PHOTOS/) | photographs of the module | 2 |
| [SOFTWARE/](SOFTWARE/) | program listings, firmware, the plugin | 1 |
| [KICAD/](KICAD/) | KiCad schematics traced from the drawings, the symbol, PCB projects | 2 |
| [OCR/](OCR/) | the note of every file: date, origin, title block, OCR text | 4 |

<!-- module data: tools/module_specs.py, tools/forum_quotes.py -->

## Circuit description

From [1995 - M8207 - 8207-02-001 - COMPONENT LAYOUT.wp](MANUALS/1995%20-%20M8207%20-%208207-02-001%20-%20COMPONENT%20LAYOUT.wp) page 1 (read by OCR; check against the pages). As data: [`CircuitDescription.json`](CircuitDescription.json).

<details><summary>Read it</summary>

4 SA14-146 Audio Terminal Assembly 4-1

5 Connector Layout 5-1

6 Parts List 6-1 to 6-5

7 Drawings:

Schematic B 8207-02-001 Component Layout B 8207-06-001 Gain: Unity.

Frequency Response: ±0.25 dB from 20 Hz to 20 kHz.

Noise: At 0 dBu sensitivity, greater than 75 dB below 0 dBu. (20 Hz to 20 kHz bandwidth).

Harmonic Distortion: Less than 0.25% at compressor threshold. Measured at +4 dBu sensitivity.

Source Impedance: 600 ohms maximum, balanced.

Input Impedance: Greater than 30K ohms, balanced.

Common Mode Rejection: Greater than 75 dB below normal signal level, 20 Hz to 15 kHz.

Input Level: +4 dBu nominal, +27 dBu maximum.

Output Impedance: Output 1: Less than 1 ohm, balanced. Output 2: 60 ohms, balanced.

Load Impedance: 1.5K ohms or greater, balanced.

Output Level: +4 dBu nominal.

Compression Ratio: 1.75:1 Nominal (in dB).

Limiting Ratio: 5:1 (in dB).

Attack Time:

Compressor: 500µs nominal, exclusive of VCA. User adjustable. Limiter: 10µs nominal, exclusive of VCA. User adjustable.

Release Time:

Compressor: 2s nominal. User adjustable.

Limiter: 10ms nominal. User adjustable.

Metering: Test Point, provided to monitor control voltage.

Power Requirements: ±22 volts DC, 70 mA.

Ambient Temperature: 0 to 50 degrees Celsius.

Dimensions: 1.00&quot; wide x 2.75&quot; high x 10.60&quot; deep.

(25.4 mm x 70.0 mm x 270.0 mm).

Weight: 0.5 lbs (227 grams).

**GENERAL**

The M8207 Compressor/Limiter is a powerful dynamics module, designed to integrate with the WBS M8200 series Distribution Amplifiers.

The modular approach allows &quot;plug and play&quot; design of audio distribution systems, all within two frame sizes: a single rack unit, housing four WBS M8200 series amplifiers and a two rack unit frame which accommodates twelve amplifiers.

The M8207 includes a state of the art input stage, providing 75 dB of common mode rejection over the audible spectrum. A front panel sensitivity control allows small variations in input sensitivity to be accommodated, and the overall threshold of both the limiter and compressor. Additional Family Members:

M8200 Remote Sensitivity Microphone Preamplifier M8201 Announce Channel Control Module M8202 Remote Sensitivity Amplifier M8203 Oscillator Module M8204 Dual Channel Audio Distribution Amplifier M8205 Audio Distribution Amplifier.

M8206 Matrixing Audio Distribution Amplifier M8208 Remote Level Amplifier Input

The input signal is applied to pins 9 and K, with the input shield connection at pin L.

Resistor R1 and R2 set the amplifier input impedance at 30,000 ohms. Resistors R3 and R4 along with CR1 through CR4 and capacitors C2 and C3 protect the amplifier from DC voltages, and limit the common mode signal which maybe connected to the amplifier's input. Capacitors C1 and C4 are selected on test at the factory and added as necessary for optimum common mode rejection. Variable resistor R6 and variable capacitor C5 are adjusted for maximum common mode rejection over the audio band.

The overall sensitivity of the M8207 is controlled by R13, which is screwdriver adjustable from the front of the card.

The output of the preamplifier is capacitively coupled to U2 and U7.

Variable Gain Cell

Integrated Circuit U2 is a high quality, current input, current output voltage controlled amplifier (VCA).

Operational amplifier U3 is configured as a current to voltage convertor. The combination of U2 and U3 (along with R14) realizes a unity gain voltage in/voltage out variable gain cell. Overall gain cell adjustment of level is accomplished by changing the voltage on pin 3 of U2. The output of the gain cell is capacitively coupled to the output amplifier and the feedback control circuit.

Output Amplifier

An actively balanced output amplifier is composed of two operational amplifiers and associated components. The gain of U4 maybe trimmed over a 3 dB range to &quot;make up&quot; for the apparent loudness loss perceived by the compression process.

The anti-phase signal of the balanced output is generated by U5, along with R31, R36 and C25.

Two balanced outputs are available. Output 1 is a low (less than 0.5 ohm) source for driving external splitter networks. Output 2 is a nominal 60 ohm output for driving a single high impedance balanced load. The minimum total load that can be driven from the M8207 is 600 ohms.

Feed Forward Control Loop

The feed forward control loop is connected to the input preamplifier output through C29. A full wave biased rectifier, consisting of U7A, U7B and associated components is coupled to a fast attack/fast decay smoothing. This filter has a nominal attack time of 10 µs, and typical decay time of 10 ms. Non-inverting U7C buffers the smoothing filter output to the logarithmic amplifier stage through R103.

Feedback Control Loop

A slower acting feedback control loop generates a control voltage through a full wave precision rectifier consisting of U6A, U6B and associated components. The attack and decay time of the feedback loop is controlled by R42, R43 and C33. Diode CR8 blocks any current leakage back into the output stage of U6B.

Resistor R42 sets the attack time at approximately 500 µs, while R43 controls the release time of approximately 2 seconds.

Non-inverting buffer U6C couples the control voltage to U6D, a variable threshold diode. This signal is impressed to the logarithmic amplifier by R63.

Logarithmic Amplifier

FET input amplifier U8 and associated components are configured as a logarithmic amplifier. U8B is a constant current driver for Q1 and Q2 via R75. A 500 µA bias current is set by R68. Logging transistor Q1, R64 and R65 and U8A area simple log circuit providing approximately 1V/decade of transfer voltage. Transistor Q2 compensates for U8A's input bias offsets.

Control Signal

The output of U8A is inverted by U7D. This signal is coupled to front panel test points through protection resistor R78, and to the variable gain cell through R25 and R26.

The control signal at U2 is prevented from introducing too much gain by CR5. Power Supply Decoupling

The ±22 volt DC supply bus voltages appearing at the amplifier connector pins (15&amp;S)and (13&amp;P) are isolated from the amplifier circuitry by fusing resistors R85 and R88. The incoming ±22 volt supply voltages are filtered by C41 and C42, after which they connect directly to the M8207 output stage.

Transistors Q4 and Q5 form positive and negative supply decouplers for the preamplifier and control stages. These beta multipliers filter and drop the input voltage to ±18 volts.

Further regulation to ±12 volts is performed by U9 and U10. This voltage provides a stable reference for the logarithmic amplifier and VCA power. C1 Capacitor SOT C2 &quot; 220 uF/10 V ITT 220M10 C3 &quot; 220 uF/10 V &quot; &quot;

**C4 &quot; SOT**

C5 &quot; 2-18 pF Philips 809-05003

C6 &quot; 15 pF &quot; 638-10159 C7 &quot; 4.7 uF/35 V ITT 4.7M35 C8 &quot; 15 pF Philips 638-10159 C9 &quot; 47 pF &quot; 638-34479 C10 &quot; 4.7 uF/35 V ITT 4.7M35

C11 &quot; 10 pF Philips 638-10109 C12 &quot; 10 uF/25 V ITT 10M25 C13 &quot; 10 uF/25 V &quot; &quot; C14 &quot; 10 uF/25 V &quot; &quot; C15 &quot; 22 pF Philips 638-10229

C16 &quot; 22 pF &quot; &quot; C17 &quot; 0.1 uF/100 V Sprague K104K20X7RFVBWN C18 &quot; 0.1 uF/100 V &quot; &quot; C19 &quot; 220 uF/10 V ITT 220M10 C20 &quot; 22 pF Philips 638-10229

C21 &quot; 0.1 uF/100 V Sprague K104K20X7RFVBWN C22 &quot; 0.1 uF/100 V &quot; &quot; C23 &quot; 22 pF Philips 638-10229 C24 &quot; 22 pF &quot; &quot; C25 &quot; 22 pF &quot; &quot;

C26 &quot; 0.1 uF/100 V Sprague K104K20X7RFVBWN C27 &quot; 0.1 uF/100 V &quot; &quot; C28 &quot; 68 uF/10 V ITT 68M10 C29 &quot; 10 uF/25 V ITT 10M25 C30 &quot; delete

C31 &quot; 22 pF Philips 638-10229 C32 &quot; 22 pF &quot; &quot; C33 &quot; 2.2 uF/35 V ITT 2.2M35 C34 &quot; 22 uF/25 V Siemens 85200

C35 &quot; 22 uF/25 V &quot; &quot; C36 &quot; 33 pF Philips 638-10339 C37 &quot; delete C38 &quot; 0.1 Sprague K104K20X7RFVBWN C39 &quot; 330 pF Philips 638-03331

C40 Capacitor 22 pF Philips 638-10229 C41 &quot; 22 uF/35 V &quot; 22M35 C42 &quot; 22 uF/35 V &quot; &quot; C43 &quot; 10 uF/25 V ITT 10M25 C44 &quot; 10 uF/25 V &quot; &quot;

C45 to C50 &quot; 0.1 Sprague K104K20X7RFVBWN C51, C52 &quot; 22p Philips 638-10229

CR1-CR7 Diode Motorola 1N4148

**CR11, CR12 &quot; &quot; 1N5711**

DS1 LED, Red Dialight 555-2001 DS2 LED, Green &quot; 555-2301

Q1 Transistor, NPN National 2N3904

Q3 delete Q4 Transistor &quot; 2N6731

**Q5 &quot; &quot; 2N6730**

Q6, Q7 delete

R1 Resistor 1/4W 1% 16K2 Philips MRS25F

**R5 &quot; &quot; 8K25 &quot; &quot;**

R6 Potentiometer 5K Piher PT10V-5K R7 Resistor 1/4W 1% 75 Philips MRS25F

**R12 &quot; 1/4W 5% 3K &quot; CR25**

R13 Potentiometer 5K Piher PT10H-5K R14 Resistor 1/4W 5% 13K Philips CR25

**R15 &quot; 1/4W 1% 100K &quot; MRS25F**

R16 Potentiometer 20K Piher PT10V-20K

**R17 &quot; 50K &quot; PT10V-50K**

R18 Resistor 1/4W 5% 240K Philips CR25

**R20 &quot; &quot; 3K6 &quot; &quot;**

R21 Resistor 1/4W 5% 180 Philips CR25

**R25 &quot; 1/4W 1% 1K &quot; MRS25F**

R26 Resistor 1/4W 1% 75 Philips MRS25F

**R28 &quot; &quot; 33K &quot; &quot;**

R29 Potentiometer 5K Piher PT10V-5K R30 * Resistor 1/4W 5% 16K Philips CR25

R31 Resistor 1/4W 1% 4K75 Philips MRS25F R32 &quot; 1/4W 5% 0 ohms &quot; CR25

**R33 &quot; 1W 5% 30 &quot; PR37J**

R34 &quot; 1/4W 5% 0 ohms &quot; CR25

**R47 &quot; &quot; 10K &quot; &quot;**

R48 Potentiometer 2K Piher PT10V-2K R49 to R53 Resistor 1/4W 5% 10K Philips CR25

**R55 &quot; &quot; 47K5 &quot; &quot;**

R56 Potentiometer 2K Piher PT10V-2K R57 Resistor 1/4W 5% 20K Philips CR25

**R59 &quot; 1/4W 1% 4K75 &quot; MRS25F**

R60 Potentiometer 2K Piher PT10V-2K

**R64 &quot; &quot; 15K &quot; &quot;**

R65 Resistor 1/4W 1% 1K Philips MRS25F

**R67 28K7 &quot; &quot;**

R68 Potentiometer 5K Piher PT10V-5K R69 delete

R70 Resistor 1/4W 5% 0 Philips CR25

**R73 &quot; &quot; 100K &quot; &quot;**

R74 delete

R75 Resistor 1/4W 1% 2K Philips MRS25F

**R77 &quot; 1/4W 1% 47K5 &quot; MRS25F**

R78 Resistor 1/4W 5% 1K &quot; CR25 R79 to R84 delete

R85 Resistor 1/2W 5% 2R2 Philips SFR25 HJ

**R97 &quot; 1/4W 1% 243 &quot; MRS25F**

R98 to R102 delete R103 Resistor 1/4W 1% 6K81 &quot; MRS25F

U1 Integrated Circuit National LM833N

</details>

<!-- /module data -->

## Photos

_Photographs of the module itself: front, back, inside, racked._

<table>
<tr><td align="center" valign="top" width="33%"><a href="https://drive.google.com/file/d/0B0yR0b5T78SKMi1RWTdMbVBVZVk/view?resourcekey=0-wLOW-kmMpAZBEYEwhe-gcw" title="Open on Google Drive"><img src="https://drive.google.com/thumbnail?sz=w480&id=0B0yR0b5T78SKMi1RWTdMbVBVZVk&resourcekey=0-wLOW-kmMpAZBEYEwhe-gcw" width="240" alt="1995 - M8207 - audio compressor - limiter 003.jpg"></a><br><sub>1995|28 · audio compressor - limiter 003</sub></td></tr>
</table>

## Manuals and documents

_Manuals and manual pages, price lists, RTO-144 connection sheets, brochures, ads and other document scans._

<table>
<tr><td align="center" valign="top" width="33%"><a href="https://drive.google.com/file/d/0B0yR0b5T78SKY3Q2WWgtRXlNcVU/view?resourcekey=0-BDu44rNvnEgENRsmiapIgA" title="Open on Google Drive"><img src="https://drive.google.com/thumbnail?sz=w480&id=0B0yR0b5T78SKY3Q2WWgtRXlNcVU&resourcekey=0-BDu44rNvnEgENRsmiapIgA" width="240" alt="1995 - M8207 - audio compressor - limiter 001.jpg"></a><br><sub>1995|28 · audio compressor - limiter 001</sub></td><td align="center" valign="top" width="33%"><a href="https://drive.google.com/file/d/0B0yR0b5T78SKZUt0Wi1wU0tzNU0/view?resourcekey=0-GBTD1Q1RVWY8vaQNU2J5cw" title="Open on Google Drive"><img src="https://drive.google.com/thumbnail?sz=w480&id=0B0yR0b5T78SKZUt0Wi1wU0tzNU0&resourcekey=0-GBTD1Q1RVWY8vaQNU2J5cw" width="240" alt="1995 - M8207 - audio compressor - limiter 002.jpg"></a><br><sub>1995|28 · audio compressor - limiter 002</sub></td></tr>
</table>

## KiCad

_KiCad: a schematic (`.kicad_sch`) traced from each electrical drawing, the module symbol (`.kicad_sym`) and its PCB projects. Traced schematics are the line work only: redraw with symbols over them._

- [M8207.kicad_sym](KICAD/M8207.kicad_sym)
- [index.html](KICAD/index.html)

## Software

- [index.html](SOFTWARE/index.html)

---
Archive: Anthony Peter Kuzub · [WBSps.ca](https://WBSps.ca) · [WBSps.Kuzub.com](https://WBSps.Kuzub.com)
