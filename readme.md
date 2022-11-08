# awesome-reset-toner

tools and docs to reset a laser toner cartridge chip



<blockquote>

https://www.techwalla.com/articles/how-to-reset-a-laser-toner-chip

How to Reset a Laser Toner Chip

Laser printers use special toner cartridges that have smart chips installed on them.

When the printer runs out of toner, the smart chip recognizes the low ink status and sends a warning to the printer.
The printer then sends a message to the connected computer, and that's how you know when to change the cartridge.

However, instead of changing the cartridge, many people prefer to refill the existing cartridge.

**After refilling, you must reset the toner chip** so it recognizes the refilled ink level
using a specific tool that can be bought from a printer accessories store.

</blockquote>



## generic

https://github.com/search?q=reset+toner

https://github.com/lugu/toner_chip_reset



## Samsung



### Samsung CLP-510

https://github.com/nharrer/speer

Speer is a python script that can backup, restore and reset the content of the EEPROM of toner cartridges for the Samsung CLP-510 series printers.



## Brother



### Brother HL-L3230CDW

toner cartridges: TN227, TN223

https://reverseengineering.stackexchange.com/questions/20780/identifying-a-toner-chip-and-its-communication-protocol-to-re-program-it


https://github.com/lugu/toner_chip_reset

Advices to reset your toner chip with an Arduino

https://www.google.com/search?q=link%3Ahttps%3A%2F%2Fgithub.com%2Flugu%2Ftoner_chip_reset



### Ricoh



### Ricoh SP 112

https://geizhals.de/?fs=ricoh+sp+112

toner: Ricoh 407166

https://github.com/lugu/toner_chip_reset

chip: FM24C02B https://github.com/lugu/toner_chip_reset/blob/master/datasheet/FM24C02B-04B-08B-16B.pdf

#### Links

Blog: http://www.hobbytronics.co.uk/arduino-external-eeprom http://www.hobbytronics.co.uk/eeprom-page-write http://lusorobotica.com/index.php/topic,461.msg2738.html

Arduino: https://www.arduino.cc/en/Reference/Wire

Tonner investigations: http://www.mikrocontroller.net/topic/369267 https://esdblog.org/ricoh-sp-c250dn-laser-printer-toner-hack/ http://rumburg.org/printerhack/

Toner chip reset for sale: http://www.aliexpress.com/item/chip-FOR-RICOH-imagio-SP-112-SF-chip-MAILING-MACHINE-printer-POSTAGE-printer-for-Ricoh-100/32261857176.html http://www.ebay.com/itm/Toner-cartridge-refill-kit-for-Ricoh-Aficio-SP112-SP112SU-SP112SF-407166-non-OEM-/161312940764

Ricoh: https://www.techdata.com/business/Ricoh/files/july2014/CurrentMSRP.pdf http://support.ricoh.com/bb_v1oi/pub_e/oi/0001044/0001044844/VM1018655/M1018655.pdf

Datasheets: http://www.gaw.ru/pdf/Rohm/memory/br24l01.pdf http://www.rinkem.com/web/userfiles/productfile/upload/201009/FM24C02B-04B-08B-16B.pdf

Logical Analyser & I2C: http://support.saleae.com/hc/en-us/articles/202740085-Using-Protocol-Analyzers http://support.saleae.com/hc/en-us/articles/200730905-Learn-I2C-Inter-Integrated-Circuit



### Ricoh SP 204

https://github.com/seurat-atreides/RICOH_SP-204_Toner-Chip-Reset

Arduino sketch to reset your RICOH SP-204 toner chip



## chip: 24C16L

german

https://www.mikrocontroller.net/topic/482699

> Ich finde auch leider zu dem 24C14(L) so gar kein Datasheet

Huh?

24C16 ist ein 08/15-Standard-EEPROM.

ps: Zum Beispiel hier:

https://www.st.com/resource/en/datasheet/m24c16-f.pdf

---

> Ich würde gerne von einer vollen Druckerkartusche einen Dump ziehen, und
> nach erfolgreichem Wiederbefüllen dann immer wieder neu schreiben.

Mit ein bisschen Pech speichert der Drucker die Seriennummern.
Und natuerlich nicht auf dem EEPROM der Druckerkartusche.

Bei HP-Tintenspuckern reicht das "Gedaechtnis" aber nur fuer 2.
Mit 3 Patronen klappt es dann...

---

Ich konnte es letzendlich doch noch zum laufen bekommen.

8 devices found in 293 milliseconds.

Nochmal alle Kabel ausgetauscht, Testklammern gekauft statt meiner 
Schiebevorrichtung und es lief direkt auf Anhieb!



## todo

https://forum.arduino.cc/t/resetting-printer-cartridge-chip-using-arduino-uno/927489


https://github.com/mlueft/tores_console

In combination with the tores arduino scetch it can be used to down and upload dump file from i2c connected EEproms. Actually this was the reason for this app to reset my toner chip.

Tores stands for Toner reset :-)



https://electronics.stackexchange.com/questions/569631/help-identify-8-pin-soic-chip-with-markings-1734-6m-2w4

Research indicates that a lot of these "toner chips" are nothing more than I2C EEPROMs.

It is clearly an I2C device, so you can find it's address using a microcontroller to scan the I2C bus.

A lot of these EEPROMs work the same way.

This github repo has code and information on how these EEPROMs are generally used in printers:

https://github.com/lugu/toner_chip_reset

If you have a working printer, you can also sniff the I2C bus to see what data is transferred between the chip and printer. The above github link has information on how to do that.



https://blog.slicer.ca/2018/12/resetting-page-count-on-samsung.html

After some research, it turns out drum unit uses the same technique as toner cartridges to enforce end-of-life.  It uses a small 4Kbit i2c EEPROM to store the page count.  

There are some great resources for resetting almost the same EEPROM on toner cartridges on Samsung printers.  I used and adapted these to reset the drum counter.

https://github.com/nharrer/speer
https://www.netzgewitter.com/projects/speer-samsung-printer-eeprom-resetter/
https://www.netzgewitter.com/2014/12/reset-samsung-clp510-toner-cartridge-with-raspberry-pi/
https://github.com/lugu/toner_chip_reset

Note: from what I have been reading, some versions of the firmware require modifications to other offsets too.  It's probably easiest to take a snapshot of the eeprom, save it somewhere safe, and then reload the eeprom 5 years later when the page counter is too high.



chip resetter

https://www.techwalla.com/articles/how-to-reset-a-laser-toner-chip

How to Reset a Laser Toner Chip

Laser printers use special toner cartridges that have smart chips installed on them.
When the printer runs out of toner, the smart chip recognizes the low ink status and sends a warning to the printer.
The printer then sends a message to the connected computer, and that's how you know when to change the cartridge.
However, instead of changing the cartridge, many people prefer to refill the existing cartridge.
After refilling, you must reset the toner chip so it recognizes the refilled ink level
using a specific tool that can be bought from a printer accessories store.

Step 1
Buy a chip resetter specific to your laser printer cartridge.
A resetter is a tiny plastic tool, which when brought into contact with the printer's chip, resets its memory.

Step 2
Place the cartridge in an upward position on a flat surface.
The release points on the cartridge should be pointing in the upward direction.
Hold the resetter upright, making sure its LED lights are also pointing upward.

Step 3
Push down all the pins on the resetter. Depending on the model, there may be a button instead of pins.

Step 4
Keep pushing the pins/button until the LED light on the cartridge turns green,
or it indicates with a beep that the cartridge has been reset.
The entire procedure shouldn't take more than five seconds.

Step 5
Open the printer tray and place the cartridge back into the printer.
The cartridge is now ready for use.



https://reverseengineering.stackexchange.com/questions/20780/identifying-a-toner-chip-and-its-communication-protocol-to-re-program-it

Identifying a toner chip and its communication protocol to re-program it

I need help identifying a chip and how to reset it from a new Brother's toner cartridge TN227 and TN223. This comes from the new Brother HL-L3230CDW laser printer.

There is currently no information on how to reverse engineer these chips to reset them, so I decided to investigate further, however I'm currently stuck.

...

I then connected a logic analyzer to the printer with the chip attached to see if I could figure out what protocol it was using. Assuming white is GND, Here's a sample of the Sigrok Pulseview received:

...

I'm not sure the best approach to analyze the binary data, since I can't identify the communication protocol, and I'm concerned that it might be encrypted. After searching patents to see if I could find more info on the chip, this was all I could find: http://www.freepatentsonline.com/y2013/0070279.html This suggests that the chip may be using crypto to hide info on the chip. If so, would it possible to crack it?

I tried analyzing the data as if it were I2C, but this doesn't seem right, Also I'm pretty sure it's not SPI. I do know there's a clock involved, so I know it has to be synchronous, but any help would be appreciated!



Tim Do Brava:

If you have a Brother printer you can use these instructions I found on Amazon on how to reset your cartridge chip, it worked for me.

"I was able to reset my toner cartridges for this model by using the process that I found by doing some googling for a "better way to reset brother" toner cartridges.

Summarized, open the inside cover where the toner cartridges are located. Next, press the back and X buttons simultaneously. Then, press the back button again. This should bring up the toner reset menu.

I had to try a number of times...I think I wasn't pressing exactly at the same time on those two buttons OR they intentionally build it so you have to do it multiple times to make it work. In any case, it is now reset. Happy Camper."



https://blog.123ink.ca/2016/08/what-is-a-printercartridge-chip/

Cartridge Refills and Replacements
Toner chips have caused some controversy
because they make it difficult to refill a printer cartridge.
After you refill a cartridge, you have to reset or replace the chip
in order for your printer to allow you to print.
Our compatible inks and toners have been installed with a new chip in our factory
so you don’t have to worry about resetting the chip.



https://www.instructables.com/How-to-Refill-Your-Printer-Toner-Cartridge-the-Eas/

Refill Your Laser Printer Toner Cartridge the Easy Way



reset the resetter ... (its getting stupid)

https://www.reddit.com/r/arduino/comments/fxrkqm/reverse_engineering_a_printercartridgeresetmodule/

Reverse engineering a printer-Cartridge-reset-module?



https://www.freelancer.com/projects/c-programming-verilog-vhdl/printer-toner-cartridge-reverse/

We design and develop after market printer/toner cartridges. We are looking for a new Engineer to help us with our products. We take a OEM printer and Cartridge and reverse engineer the firmware. Sometime we have to actual Decap the current IC that is used in the cartridge and use a SEM or FIB to be able to do what we need to. Extract code from the current secure controller, Create a flow chart, Emulate exactly what the current chip is doing. (100%) This is a very technical job, we only want people that really understand what we are asking for. We have lost many opportunities lately because we lost our last engineer. We need someone who is going to be 100% dedicated to what we are doing.

Main equipment that will be needed to complete this project.

Decapping Device

FIB

SEM

Probing Station



https://www.groovypost.com/howto/save-laser-toner-hack/

cheap trick

block infrared sensor



https://forum.arduino.cc/t/resetting-printer-cartridge-chip-using-arduino-uno/927489


https://stefansbb.blogspot.com/2016/04/hacking-ricoh-sp-c250dn-toner-cartridges.html



https://www.netzgewitter.com/2014/12/reset-samsung-clp510-toner-cartridge-with-raspberry-pi/


https://bitbucket.org/Electricks/arduiono_sketches/src/d4a242e5b1cdebb4c38a5d93fbd5d17411abe3c4/EEPROM/EEPROM.ino?at=master



https://www.eevblog.com/forum/chat/end-the-monopoly-we-need-open-source-inkjet-printers/

long discussion, focus on INKJET printers (waste of time, mostly)

End the Monopoly - we need Open Source Inkjet Printers

this video got me thinking

Ink Cartridges Are A Scam
https://www.youtube.com/watch?v=AHX6tHdQGiQ

transcript:
[ink-cartridges-are-a-scam.md](ink-cartridges-are-a-scam.md)

one way to end the inkjet printer monopoly is open source competition.
this has many interesting possibilities.
if 3D printing has open source why not 2D printing?
to end the ink cartridge scams.



https://www.quora.com/Is-there-any-Laser-Printer-available-whose-cartridge-does-not-come-with-a-toner-reset-chip?share=1



https://www.quora.com/Is-there-any-open-source-hardware-for-inkjet-laserjet-printers-and-multi-function-devices?share=1



https://hackaday.io/page/6176-why-is-there-no-open-source-firmware-for-laser-or-inkjet-printers



I used to work at a company making printer software. Basically, a company (Canon, for instance) would come out with a new printer hardware, we would tune our code to run on their platform, they would then put the software into their machine. Any printer that isn't from HP or Apple has some of my code in it.

The software that goes into printers is hundreds of thousands of lines of code.

Basically, the printer is underspec'd for rendering, doesn't have enough memory to render a full page, so the software breaks the page up into slices and renders the next slice while the current slice is printing. That takes a lot of effort to get right.

For example, a laser printer cannot stop in the middle of printing a page, so not only does the slice have to fit in memory it has to be finished rendered at the time the drum reaches that part of the page. 

Then there is verification: the three basic languages are postscript and PCL/GL, and the number of corner cases in those description languages is massive. My company purchased a debug set of reference tests and rendered output for these three languages... and it was massive. We're talking huge amounts of shelf space just to store these books of output, and there were new ones every time the language spec changed. (Postscript and the other languages have versions, and bug fixes.)

The printer hardware is straightforward: the hardware description is usually a known processor type (for which you can get a compiler), and an I/O map that shows which GPIO lights up which LED, how to send data to the laser and so on. That part was pretty straightforward.

To give you an idea of the complexity, IBM came and had us port our existing software to their new machine - software which had been ported to several dozen other hardware systems and was pretty robust - and the initial build released by the software team was found to have 900 bugs.

IMO, Only a company with a dedicated software and QA team and good management will be able to make printer software.

---

too complex

we only want to patch some parts of the firmware,
so we can reset the toner chip with the printer

some printer have a hidden menu for this,
maybe all printers have it?

