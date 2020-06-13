# Introduction
## On-Chip Clock Multiplier(PLL)(Fclkin – 5MHz to 12Mhz, Fclkout – 40MHz to 100MHz at 1.8v@osu180nm)
> This project presents a model for clock generating circuitry using PLL techniques. The reference signal is a square wave and technology used is 180nm(@osu180nm). 

### Phased Lock Loop
> This project is focussed on developing a Phased lock loop comprising of a phase detector, Charge Pump, Low pass filter, and a voltage-controlled oscillator(VCO) which is current starved using 180nm CMOS technology. PLL has quite many applications in this electronics domain which includes Frequency Synthesizer in mobile phones or Clock generation in microprocessors.

### Sourceware
> The design is implemented using one of the open sourceware -`LTSpice`.

### Installation
> Steps for installation of the simulator in LINUX:
1) As it isn't directly supported. Download [WineHQ](https://wiki.winehq.org/Download).
2) Download [LTSpice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).
3) Click on `Download for Windows`.
4) After downloading click on open with `WineHQ windows program loader`.

> Steps for installation of the simulator in WINDOWS/MAC:
1) Download [LTSpice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).
2) Install as directed on the screen by clicking on `->next`.

### Implementation
Steps to implement the project:
1) Click on the desktop icon, `LTSpice VII`.
2) Click on `New Schematic` and build your circuit diagram by placing components. 

![Screenshot (353)_LI](https://user-images.githubusercontent.com/34000135/84546653-6b0fa400-ad1f-11ea-9b50-b768c685475f.jpg)

3) Click on the `Simulate` button for waveforms generation.

### Accessing my files
1) Click on `Download zip file`.
2) Click on`.asc` file which will open the schematic.
3) Click on simulate to check the waveforms.
4) To view the `Spice Netlist`. Go to `Edit ->SPICE Analysis'.
![Screenshot (367)_LI](https://user-images.githubusercontent.com/34000135/84550881-7962bd80-ad29-11ea-9ae3-ad43360cf1a6.jpg)


### Schematic

- Phase detector
![Screenshot (356)](https://user-images.githubusercontent.com/34000135/84546882-f25d1780-ad1f-11ea-8837-42dc5e8f5054.png)

- Charge Pump and Low Pass Filter(LPF)
![Screenshot (357)](https://user-images.githubusercontent.com/34000135/84547037-4c5ddd00-ad20-11ea-8d8f-e259929f418e.png)

- Voltage Controlled Ring Oscillator
![Screenshot (358)](https://user-images.githubusercontent.com/34000135/84547131-80390280-ad20-11ea-960e-a7f829f6c426.png)

### WAVEFORMS
![Screenshot (364)](https://user-images.githubusercontent.com/34000135/84550333-f1c87f00-ad27-11ea-9fbe-f0c6f2bf2991.png)
> In this the first waveform is V[Up], Second is V[Down] which are the outputs of the phase detector. The third waveform is of Vdd(1.8v) and V(Clk_input1) & V(Clk_input2).

![Screenshot (365)](https://user-images.githubusercontent.com/34000135/84550608-b7abad00-ad28-11ea-95b7-bc7cb00a2a5c.png)
> This is V(cont) which is output of VCO.





Contact Information
--------

-  SAMEEKSHA KONAKALLA- B.Tech Electronics and Communication Engineering, SRM University AP <26sameekshak@gmail.com>

- KUNAL GHOSH, Director, VSD Corp. Pvt. Ltd. <kunalpghosh@gmail.com>

- PHILIPP GÜHRING, Software Architect at LibreSilicon Association <pg@futureware.at>

-  Dr. GAURAV TRIVEDI, Co-Principal Investigator, EICT Academy, IIT Guwahati <trivedi@iitg.ac.in>
