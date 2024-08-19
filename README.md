# Sony SND THT Replacement 
A replacement for the Sony SND IC (part number 343-0045-A) as used on the Macintosh Plus, SE and others.
This was designed for the Macintosh Plus Clone project, but should be able to be used in other Macintoshes.




![Screenshot_20240816-162321~2](https://github.com/user-attachments/assets/c34cc3c8-0712-4313-ade1-feef66516c8a)




**So, What Is It?**

The Sony SND is a custom IC, developed by Sony for the Macintosh Plus. 
It has three main functions - volume control, audio amplification, as well as providing the POR (Power On Reset) signal for the system. 
The original IC represents one of three custom pieces of silicon found with the Macintosh Plus. 

This board replaces the original Sony SND with equivalent circuitry. 
The Power On Reset deisgn is taken from the book _The 68000 microprocessor : hardware and software principles and applications_
This is currently available on the internet archive: https://archive.org/details/68000microproces00jame

Whereas the design for the audio amplification and volume control was taken from the original Macintosh 128/512 schematics:
https://forums.macrumors.com/threads/macintosh-512k-schematic.2291827/

**Parts List**

The SND is comprised of relatively easy to find, off the shelf parts:

C1       100n 50V       100N_TH_CAP            CAP_5.08MM_PITCH 1

C2       100n 50V       100N_TH_CAP            CAP_5.08MM_PITCH 1

C3       100n 50V       100N_TH_CAP            CAP_5.08MM_PITCH 1

C4       100n 50V       100N_TH_CAP            CAP_5.08MM_PITCH 1

C5       1u 50V         1U_TH_ELEC_CAPVERTICAL CAP_ELECTROLYTIC 1

C6       100n 50V       100N_TH_CAP            CAP_5.08MM_PITCH 1

C7       470p 50V       470P_TH_CAP            CAP_5.08MM_PITCH 1

C8       1n 50V         1N_TH_CAP              CAP_5.08MM_PITCH 1

C9       100n 50V       100N_TH_CAP            CAP_5.08MM_PITCH 1

C10      100n 50V       100N_TH_CAP            CAP_5.08MM_PITCH 1

C11      220p 50V       220P_TH_CAP            CAP_5.08MM_PITCH 1

D1       5.1V Zener     ZENER-DIODEF126-10     F126Z10          1

IC1      TL072P         TL072P                 DIL08            1

IC2      4016N          4016N                  DIL14            1

IC3      74LS05N        74LS05N                DIL14            1

IC4      555            555P                   DIP08            1

CN1      Header         Turned Pin Header      DIP16 Header     16

Q1       2N3906         2N3906                 TO92             1

Q2       2N3904         2N3904                 TO92D            1

R1       1M             1M_TH_RESISTOR         RESISTORTHRUHOLE 1

R2       1M             1M_TH_RESISTOR         RESISTORTHRUHOLE 1

R3       6k8            6K8_TH_RESISTOR        RESISTORTHRUHOLE 1

R4       47k            47K_TH_RESISTOR        RESISTORTHRUHOLE 1

R5       1k             1K_TH_RESISTOR         RESISTORTHRUHOLE 1

R6       47k            47K_TH_RESISTOR        RESISTORTHRUHOLE 1

R7       68k            68K_TH_RESISTOR        RESISTORTHRUHOLE 1

R8       150k           150K_TH_RESISTOR       RESISTORTHRUHOLE 1

R9       470k           470K_TH_RESISTOR       RESISTORTHRUHOLE 1

R10      470k           470K_TH_RESISTOR       RESISTORTHRUHOLE 1

R11      200k           100K_TH_RESISTOR       RESISTORTHRUHOLE 1

R12      150R           150K_TH_RESISTOR       RESISTORTHRUHOLE 1

R13      10R            10R_TH_RESISTOR        RESISTORTHRUHOLE 1


All components are through hole, and are designed to be easily soldered. 
The PCB can be sourced from your favoured fab house, I prefer JLCPCB (sorry PCBWay) - and only cost $4 for five boards. 

**Assembly Notes and Errata**

This design is the initial VDEV1 version of the SND replacement, although an example has been produced on veroboard, 
it is currently not known if this will operate correctly.
However, all components listed are identical to the prototype version, so are known to work.



<img width="324" alt="Screenshot 2024-08-19 at 20 36 02" src="https://github.com/user-attachments/assets/627c5565-2866-4a05-8091-defc22d9686b">




The design (being through hole) is unlikely to fit into an existing Macintosh chassis, and was designed as a
"first stab" attempt at making a replacement SND. It is anticipated that a secondary improved SMD design will be more suited to this application.

The zener diode at D1 theoretically should be a 1N5231, but any similar 5.1v zener will suffice. 

Assembly should be fairly straight forward for those with some experience with electronic assembly.

Additionally, as the audio section is based off the original Macintosh 128K, -12V is required, which is not provided by the SND header. 
-12V can be tapped directly from the logic board - either from pin 2 (central pin) of the 7905 -5v regulator, pin 8 of the audio/power header
or from pin 5 of the MC3488 line driver. 
I heavily suggest checking with a multimeter before installation - this may damage the SND adapter, the Macintosh board, or both.

The board should be fitted so that the majority of the boards cover the 6522 and Z8530. It may be necessary to add a standard IC socket to raise the board.
