# ZX81plus38
Mij latest ZX81 clone without ULA built from discrete pin through hole components
It features a PCB with the exact same size as a normal ZX81, (142 x 100mm) and features drill holes and connectors at the same locations (with the 3.5mm power jack replaced
with a modern Type B power jack, so you can power this ZX81 clone with a simple USB power supply, and with the RF output modulator replaced with a composite video
output connector, that produces a video signal that modern composire monitors should be able to accept (yes with a real front porch signal).
There is no ULA needed for this clone, as all the ULA logic is replicated with modern DIP compatible logic IC's. The software (ZX-81 BASIC) fits into a cheap OTP
(one time programmable) 27C256 ROM, and the bit-for bit same code as a real ZX-81 code can be programmed into a 27C256 OTP ROM, and will work exactly the same as a real ZX-81. but with a few jumper changes you can alos use an original 8K ZX81 ROM. The use of a 4K ZX80 ROM is also supported.
Its also possible to fit several (different) code images into the 32K ROM, and it is possible to add switches to select one image to boot with.
Extra logic was added to simulate the same cassette loading screen patterns as a real ZX81 has.
The cassette loading input logic has been eenhanced to give perfect cassette loading behaviour, even whith cassette signals generated with a laptop, for easy cassette loading.
The ULA replacement logic is perfect enough to enable the use of games which use various enhanced highres graphics techniques to work flawlessly.
In fact the ZX81+38 clone is easy to build, and a joy to use.

Warning: The revision 1.4 version of my ZX-81+38 contains some errors, and will NOT work as is. The main reason being that the WAIT generator flip/flop idea doesn't work, and must be replaced with a working wait circuit. As revision 1.4 is not working, and has now been replaced by revision 1,5, I have deleted revision 1,4

ZX81+38rev1,5.zip contains all gerber and drill files for the working updated and layout checked files to produce a revision 1,5 version PCB.

The file ZX81+38rev1,5.pdf is the schematic of the corrected revision 1.5 (in black and white) The only difference with rev 1.6 is that a8 is used for the keyboard connection instead of A8'

We found one more error, that I have fixed in revision 1,6:
the keyboard matrix is connected to eight Address lines, A8 to A15, but the error is that for A8 a version is used that comes from the signal line passing through a 10K resistor (R1) so it is signal A8' , that is not correct, the keyboard needs unattenuated signals, so A8, not A8'. otherwise the resulting dataline does not go low enough to reliably register as "low". (actualy this was not essential, as long as the RP1 pullups are not too strong, so I changed them to 10K instad of 4K7. 

Because of covid (closing my Makerspace) I have not been able to build my own copy of the ZX81plus38, but I'm several people have built it and reported that revision 1.6 is working well. You can read much more about the development of my designs in my makerspace at www.revspace.nl look up my projects in the projects gallery. For example this project can be found here: https://revspace.nl/ZX81plus38_simple_to_build_ZX-81_clone for writing back you can mail me at mahjongg at xs4all.nl replace the at for the comercial at sign @, or you can use the forum of the raspberry PI organisation where I wrote about this clone in the "offtopic" section.

R21 (the series resistor for a keyboard LED ) should be 330 Ohm (if you add a keyboard LED) That is if you built the keyboard I designed for the ZX81plus35 that also works with this ZX81plus38, in the schamatic a value of 100Ohm is used, which is also okay, although much brighter.

And I will upload kiCad files after I know revision 1.6 is working well, which can happen only if revspace reopens, and I have built and tested my own copy, and I have recovered enough from my current bad condition of what I think of as my "long-covid", only I don't remeber ever having a case of covid, but I do suffer from the symptoms. I'm 65 now (2021/2022) so I don't see myself getting a job anymore, and consider myself retired.

I noticed that somehow I hadn't uploaded a correct BOM, so I added the Bill of material file in the form of and .ODS (open officie spreadsheet) file
The BOM contains exact component designators for all components used from either farnell or mouser, so you will know EXACTLY which components to buy.
