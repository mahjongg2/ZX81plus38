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

The file ZX81+38rev1,5.pdf is the schematic of the corrected revision 1.5 (in black and white)

And I will upload kiCad files after I know revision 1.5 is working well.

We found one more error, that I will fix in revision 1,6:
the keyboard matrix is connected to eigh Address lines, A8 to A15, but the error is that for A8 the version is used that comes from the signal line passing through a 10K resistor (R1) so it is signal A8' , that is not correct, the keyboard needs unattenuated signals, so A8, not A8'. otherwise the resulting dataline does not go low enough to register as "low". 

