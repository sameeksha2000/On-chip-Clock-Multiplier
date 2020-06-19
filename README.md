# Introduction
## On-Chip Clock Multiplier(PLL)(Fclkin – 5MHz to 12Mhz, Fclkout – 40MHz to 100MHz at 1.8v@osu180nm)
> This project presents a model for clock generating circuitry using PLL techniques. The reference signal is a clock pulse and technology used for implementation is 180nm(@osu180nm).

### Phased Lock Loop
> This Phased lock loop comprises of a phase detector, Charge Pump, Low pass filter, and a voltage-controlled oscillator(VCO) which is current starved.The phase detector or comparator compares the input frequency with feedback frequency. The output of the phase detector is proportional to the phase difference between input and output frequency. The VCO is a sinusoidal generator whose frequency is determined by a voltage applied to it from an external source. In effect, any frequency modulator may serve as a VCO. PLL has quite many applications in this electronics domain which includes Frequency Synthesizer in mobile phones or Clock generation in microprocessors.

### Sourceware
> The design is implemented using one of the open sourceware -`LTSpice`.

### Installation
> Steps for installation of the simulator in LINUX:
1) As it isn't directly supported, we need to download WineHQ.
2) Copy paste the commands one after another in the terminal for downloading & installing:
```
sudo dpkg --add-architecture i386
wget -O - https://dl.winehq.org/wine-builds/winehq.key | sudo apt-key add -
sudo add-apt-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ focal main'
sudo apt update
sudo apt install --install-recommends winehq-stable
```
3) Download [LTSpice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).
4) Click on `Download for Windows`.
5) Install as directed on the screen by clicking on `->next`.
6) After installing click on open with `WineHQ windows program loader`.
![Screenshot from 2020-06-16 17-13-27](https://user-images.githubusercontent.com/34000135/84770617-81568200-aff5-11ea-87b7-fab9d7952eff.png)

> Steps for installation of the simulator in WINDOWS/MAC:
1) Download [LTSpice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html).
2) Install as directed on the screen by clicking on `->next`.

### Implementation
Steps to implement the project:
1) Click on the desktop icon, `LTSpice VII`.
2) Click on `New Schematic` and build your circuit diagram by placing components. 
3) Click on the `Simulate` button for waveforms generation.
4) For further help with LTSpice refer the manual [LTSpice guide](http://dept.me.umn.edu/labs/hmd/lab/docs/LTspice_Guide.pdf)

### Library
> To use the 180nm CMOS technology
1) Download this [CMOS@180nm_NMOS](https://github.com/sameeksha2000/On-chip-Clock-Multiplier/blob/Schematic/Nmos)
    & [CMOS@180nm_PMOS](https://github.com/sameeksha2000/On-chip-Clock-Multiplier/blob/Schematic/Pmos)
2) Copy the code excluding .end until the brackets for both nmos & pmos.
![Screenshot from 2020-06-19 00-50-59](https://user-images.githubusercontent.com/34000135/85063256-7f441d00-b1c7-11ea-90a2-50c1f0e943c7.png)

3) Click on .opt in LTSpice and paste the code there.
![Screenshot from 2020-06-16 16-36-15](https://user-images.githubusercontent.com/34000135/84770820-e5794600-aff5-11ea-9dd2-5175b68d8fe5.png)


### Accessing my files
1) Click on `Download zip file`.
2) Click on`.asc` file which will open the schematic.
3) Click on simulate to check the waveforms.
4) To view the `Spice Netlist`. Go to `Tools ->Export Netlist'.
![Screenshot from 2020-06-19 00-51-49](https://user-images.githubusercontent.com/34000135/85063318-984cce00-b1c7-11ea-9a5a-9042b3f1419b.png)

![Screenshot from 2020-06-19 00-52-05](https://user-images.githubusercontent.com/34000135/85063377-aef32500-b1c7-11ea-9e4d-9e0eabb4c93f.png)

NOTE: The netlist exported in this will be .cir file. So to make it universally accessible, we need to run it in `ngspice`.

### Simulations in NGSpice
> Windows
1) Download [ngspice](https://sourceforge.net/projects/ngspice/files/) and then [ngspice gui](http://ngspice.sourceforge.net/download.html).
2) Unzip the folder, then 'DuSpiceStart.exe' & 'DuSpicePlot.exe' will appear.
3) Click on 'DuSpiceStart.exe -> New file -> include .cir file'.
4) Click on 'Setup -> include ltspice '.
![WhatsApp Image 2020-06-19 at 17 58 12](https://user-images.githubusercontent.com/34000135/85132651-d6450300-b256-11ea-8ae9-481432289f2c.jpeg)

5) Click on `Start interact`, ltspice will open.
6) Trace the plot and the waveform will be generated.

>Linux
1) To install type `sudo apt-get install -y ngspice`.
2) After installation, to enter into the shell type `ngspice`.
3) To simulate type `source filename.cir`.
![Screenshot from 2020-06-19 18-06-30](https://user-images.githubusercontent.com/34000135/85134303-e6aaad00-b259-11ea-9b8d-a711d070cb3b.png)
    Here I've first changed the directory to the location where `.cir` file is present. command is
    cd 'location'.


### Schematic

- Phase detector
![PFD](https://user-images.githubusercontent.com/34000135/85063542-ebbf1c00-b1c7-11ea-96c4-bf2fa5431680.png)

- Charge Pump & Low Pass Filter
![ChargePump LPF](https://user-images.githubusercontent.com/34000135/85063505-e06bf080-b1c7-11ea-81b1-f32a3a00f615.png)

- Voltage Controlled Ring Oscillator
![VCO](https://user-images.githubusercontent.com/34000135/85063460-cc27f380-b1c7-11ea-91c1-be1fcb28066e.png)


### WAVEFORMS

![Vclk2   Vclk1](https://user-images.githubusercontent.com/34000135/84765417-d215ad00-afec-11ea-9eb8-97b940b97b7f.png)

> In this the output is of V(Clk_1) & V(Clk_2).

![WhatsApp Image 2020-06-18 at 23 25 04](https://user-images.githubusercontent.com/34000135/85132735-fd033980-b256-11ea-9e25-00785a335005.jpeg)

> This is V(up) & V(down)

![Vcont](https://user-images.githubusercontent.com/34000135/84765449-dcd04200-afec-11ea-8383-7b36e1fc71f2.png)
> This is V(cont) which comes out of charge pump & LPF.







Contact Information
--------

-  SAMEEKSHA KONAKALLA- B.Tech Electronics and Communication Engineering, SRM University AP <26sameekshak@gmail.com>

- KUNAL GHOSH, Director, VSD Corp. Pvt. Ltd. <kunalpghosh@gmail.com>

- PHILIPP GÜHRING, Software Architect at LibreSilicon Association <pg@futureware.at>

-  Dr. GAURAV TRIVEDI, Co-Principal Investigator, EICT Academy, IIT Guwahati <trivedi@iitg.ac.in>
