# ZX81plus38
Mij latest ZX81 clone without ULA built from discrete pin through hole components
It features a PCB with the exact same size as a normal ZX81, (142 x 100mm) and features drill holes and connectors at the same locations (with the 3.5mm power jack replaced with a modern Type B USB power jack, so you can power this ZX81 clone with a simple USB power supply), and with the RF output modulator replaced with a composite video output connector, that produces a video signal that modern composite monitors should be able to accept (yes with a real front porch signal, so it works on modern TV's as well).
There is no ULA needed for this clone, as all the ULA logic is replicated with modern DIP compatible logic IC's. The software (ZX-81 BASIC) fits into a cheap OTP (one time programmable) 27C256 ROM, and the bit-for bit same code as a real ZX-81 code can be programmed into a 27C256 OTP ROM, and will work exactly the same as a real ZX-81. but with a few jumper changes you can also use an original 8K ZX81 ROM. The use of a 4K ZX80 ROM is also supported.
Its also possible to fit several (different) code images into the 32K ROM, and it is possible to add switches to select one image to boot with. Note that you should fill up the ROM with as many copies of the 8K BASIC ROM as will fit, meaning for a 27C256 (a 32 K byte ROM) you should fill it with four copies, and a W27C512 (64K Byte) with eight copies.
Extra logic was added to simulate the same cassette loading screen patterns as a real ZX81 has.
The cassette loading input logic has been eenhanced to give perfect cassette loading behaviour, even whith cassette signals generated with a laptop, for easy cassette loading.
The ULA replacement logic is perfect enough to enable the use of games which use various enhanced highres graphics techniques to work flawlessly.
In fact the ZX81+38 clone is easy to build, and a joy to use.

Warning: The revision 1.4 version of my ZX-81+38 contains some errors, and will NOT work as is. The main reason being that the WAIT generator flip/flop idea doesn't work, and must be replaced with a working wait circuit. As revision 1.4 is not working, and has now been replaced by revision 1,5, I have deleted revision 1,4

ZX81+38rev1,5.zip contains all gerber and drill files for the working updated and layout checked files to produce a revision 1,5 version PCB.

The file ZX81+38rev1,5.pdf is the schematic of the corrected revision 1.5 (in black and white) The only difference with rev 1.6 is that a8 is used for the keyboard connection instead of A8'

We found one more error, that I have fixed in revision 1,6:
the keyboard matrix is connected to eight Address lines, A8 to A15, but the error is that for A8 a version is used that comes from the signal line passing through a 10K resistor (R1) so it is signal A8' , that is not correct, the keyboard needs unattenuated signals, so A8, not A8'. otherwise the resulting dataline does not go low enough to reliably register as "low". (actualy this was not essential, as long as the RP1 pullups are not too strong, so I changed them to 10K instad of 4K7. 

Revision 1.7 fixes some small errors, and revision 1.8 has the fault fixed that lead to a mix of logic families, now only HC logic is used (in theory you can also use all LS logic, or all HCT logic, all LS logic is confirmed to work.

Because of covid (closing my Makerspace) I have not been able to build my own copy of the ZX81plus38, but I'm several people have built it and reported that revision 1.6 is working well. You can read much more about the development of my designs in my makerspace at www.revspace.nl look up my projects in the projects gallery. For example this project can be found here: https://revspace.nl/ZX81plus38_simple_to_build_ZX-81_clone for writing back you can mail me at mahjongg at xs4all.nl replace the at for the commercial at sign @, or you can use the forum of the raspberry PI organisation where I wrote about this clone in the "offtopic" section.

And I will upload kiCad files after I know revision 1.6 is working well, which can happen only if revspace reopens, and I have built and tested my own copy, and I have recovered enough from my current bad condition of what I think of as my "long-covid", only I don't remeber ever having a case of covid, but I do suffer from the same symptoms. I'm 66 now (2021/2022) so I don't see myself getting a job anymore, and consider myself retired.

I noticed that somehow I hadn't uploaded a BOM, so I added the Bill of material file in the form of and .ODS (open officie spreadsheet) file
The BOM contains exact component designators for all components used from either farnell or mouser, so you will know EXACTLY which components to buy. Use version 1.8 so that you don't use a mix of logic families.

Note that R21 (the series resistor for a power LED) is NOT in this BOM, as I added it after I created the BOM, but should be 330 Ohm (if you add a Power LED) That is if you built the keyboard I designed for the ZX81plus35 that also works with this ZX81plus38, in the schematic a value of 100Ohm is used, which is also okay, although much brighter.

on june 15, 2022 I uploaded a BOM for revision 1.7 of the ZX81+38 creating some corrections R20 should be 680R, R21 should be 330 R R29 should be 1M RP22 can be 10Kx8 but 22Kx8 works better with some keyboards, C7 should be 47nF, most importantly U21 should be a 74HC04 or 74HCU04 NOT A 74HC14! There is a strong possibility the crystal oscillator won't work when using a schmitt trigger inverter (74HC14) use a HC04 or better a HCU04.

On June 23, 2022 I finished the schematic for the latest revision 1.7 version of the ZX81+38 with several small corrections. and also updated the layout. The main correction is the rotation of the keyboard-data connector J3, so the ZX81+38 is now completely compatible with a ZX-81 keyboard foil, (I will create a specific keyboard PCB for the ZX81+35, or even a real ZX81 later on) other changes are that U21 is now a 74HC04 with R29 as an 1M resistor. 

JP1 is now default jumpered for a 16K ROM space, (instead of an 8K ROM space) so its compatible with the future PSG board, awhich needs the firmware for the SD interface in a second 8K ROM section, if you don't want this (you want to use four 8K selectable ROM's) then switch over JP1. 

I made the crystal footpad now compatible for a SMD crystal too, and printed several texts on the sikscreen bootom and top to help with selecting options, and improve compatibility with the BOM.

I also updated a component placement drawing for revision 1,7 and uploaded it here.

Lastly for completeness, I also uploaded the ROM dump of the real ZX-81, which you are legally allowed to burn into a ROM and use with the ZX81+38. 

On 5 juli 2022 I discovered that KiCad had changed back to the logic family of some libraries for wich I had changed the original logic family from LS logic to HC logic. I intended that all logic would be HC logic, just like in my ZX84+35 initial clone. But this bug in KiCad may cause problems because HC logic and LS logic are incompatible. So the first thing I did was updating the BOM, also to see if there actually were HC replacements for the LS logic I had used by mistake. Luckily all the HC logic I needed was available in DIP. Next up will be revision 1.8 of the schematic, which will also get a clock inverter using a spare half of a flipflop. This might be necessary to solve a timing error that can occur with EPROM's that are too slow to put pixel data into the shift register, which results in all black character squares (due to the databus pullups that pull the databus high when nothing is driving it). Then I will correct the component placement diagram which also shows some wrong logic families. My last remark is that although theoretically the ZX81+38 should not work with mixed logic, it seems that in practice it still seems to work as I have reports that it does! I finished building up my own copy with mixed logic so soon I can check this for myself. Also note that I no longer recommend using sockets with machined pins, use dual wipe sockets instead. This is reflected in the BOM. Lastly perhaps this clone will not work with original N-MOS Z80 chips, its recommended to use modern (C-MOS) versions, such as the Z84C0008PEG.


PREVIOUS VERSION REVISION 1.8

on 26 July 2022, I updated the BOM (Bill of materials) for ZX81+38 revision 1.8, adding more reichelt order codes (I have ordered my own missing HC logic chips from there, as farnell is no longer an option for me). They even had all the correct connectors!
Added a new component placement drawing that corrects the wrongly mixed logic family's and adds some extra info, use this drawing for revision 1.8
Addded rev 1.8 Schematic (.PDF in black and white) for other (.PNG older or color schematics) see my Revspace pages at www.revspace.nl/projects.

Uploaded PCB production files gerber and drill files, (I checked them with a gerber viewer, they should be okay) this version has all the latest improvements, inclusing clock inversion and the copper fill isolation around JP1.

To avoid confusion when downloading unsuitable older files I have removed all older (pre rev1.8) files, older schematics etc can be found on my revspace pages. if you need older gerber files contact me at mahjongg@xs4all.nl or visit the offtopic section of the raspberry PI foundation where I have pages about my projects (I'm a moderator there). 

On august 4, 2022, after many request I decided to zip up my KiCad project directory for the ZX81+38, and upload it to GitHub, so you can duplicate my effort, and create your own version of the ZX81+38. Note that at this moment I still have not got my own version working, I'm still missing a 74HC74 IC,
but many people have reported that they got my ZX-81 clone working, so I decided to keep my promise to completely open source my ZX-81 clone.
Please if you do, don't remove my name from the PCB, and schematics!
If you have any questions or remarks, you can reach me at mahjongg@xs4all.nl

by the way, if you need a manual for your ZX81+38 you can find it here: http://www.retro8bitcomputers.co.uk/Content/downloads/manuals/zx81-basic-manual.pdf

Also, if you are using a real ZX-81 keyboard foil then you need the connectors, (as you cannot solder pins to the foil) the actual connectors you need are Molex parts 22-02-3053 and 22-02-3083.
Note when soldering that you solder them in with the correct orientation, as the two foil ends are metalized on diferent sides, and so the 5-pin 22-02-3053 should be mounted 180 degrees rotated compared to the orientation of the 8-pins 22-02-3083. If the orientation is wrong the connectors will not make contact with the metalized side of the foil. You can find these connectors from different distributors, or from https://www.sellmyretro.com/offer/details/set-of-molex-keyboard-membrane-connectors-for-sinclair-zx81-10859 

ONE MORE SMALL REVISION WAS NEEDED REVISION 1.9

When testing the joystick interface we found out that it wasn't working, R23 should be 1 K not 10K, and I forgot to add five pulldown to GND resistors on the bases of the five 2N3904 transistor, the latter means a large layout change, I opted for a 6-pin resistor (star) network with 5 10K resistors, and I placed it between the SRAM chip and the 5 2N3904 Transistors, note that pin 1 (the common pin) is located on top). I remade all the files anew for revision 1.9 and replaced the existing files with revision 1.9 files here. The .ZIP file with the KiCad files now only contains the three necessary files: that is:
ZX81plus38.kicad_pcb
ZX81plus38.kicad_pro
and
ZX81plus38.kicad_sch
hopefully that was the last update


KEYBOARD PCB

For a keyboard with real buttons.
on September 8, 2022. I finished my keyboard PCB, revision 1.1. I uploaded the schematic, the PCB production files, a Bill of material specifically for the keyboard, and a keyboard overlay (.PDF) which you can print out, laminate with transparent plastic, punch holes for the 40 keyboard plungers, and glued on top of the buttons.
and a Bill of material for the keyboard with 40 keys a power LED, and solder pads for three flatcables, that are prepared so that they have wire ends with 2.54 pitch (every other wire with an 1.27mm pitch is not used) three flexcables are used with 5-wires 3-wires (for the LED) and 8-wires).
revision 1.2 was made because there were some errors in the lettering below the keys, now the text "T Y U I O P" is corrected and the "10" was changed to "0", also the lettering was made a bit bolder. This change only pertains to the silk screen, nothing else has changed.
