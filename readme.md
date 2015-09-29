# Software experiments

RPUadpt is a board I am working on that plugs into an Arduino Uno R3 pinout it does have a few extra pins that match my Irrigate7 and PulseDAQ boards. RPUadpt has an ATTINY1634 that I will most likely need to be programmed with Atmel Studio but who knows, perhaps the Arduino IDE can work also. 

First I just want to get things started with a simple blink program. That should ensure I've connected the ICSP pins correctly and get the fuse settings.

    I'm starting with the Fuse Defaults
    Low 62 :[CKDIV8:CKOUT:-:SUT:CKSEL3:CKSEL2:CKSEL1:CKSEL0] 0 1 1 0 0010
        Int. RC Osc. 8 MHz; Start-up time PWRDWN/RESET: 6CK 16CK 16MS
    High DF: [RSTDISBL:DWEN:SPIEN:WDTON:EESAVE:BODLEVEL2:BODLEVEL1:BODLEVEL0] 1 1 0 1 1 111
    Extended FF :[-:-:-:BODPD1:BODPD0:BODACT1:BODACT0:SELFPRGEN] 111 11 11 1
    Lock Bits FF :[LB2:LB1] 11 No memory lock features enabled

It is a little like an ATtiny167

http://eleccelerator.com/fusecalc/fusecalc.php?chip=attiny167&LOW=62&HIGH=DF&EXTENDED=FF&LOCKBIT=FF

I'm using an AVR Dragon and AtmelStudio 7, the dragon will detect the target voltage which is 3V3 on my board. I have connected the FTDI USB to power the target.

![](https://raw.githubusercontent.com/epccs/RPUadpt/master/14226^1_ICSPwithDragon.jpg)