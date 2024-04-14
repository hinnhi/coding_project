# 8051 Micro-controller
The C51ASM assembler is a two-pass macro assembler for the AT89 Family of 8051 microcontrollers with specific features for the AT89LP single-cycle devices. C51ASM is installed as a part of the AT89LP Developer Studio. It is also available separately for the Microsoft Windows and Linux platforms.

## [AT89S52](https://ww1.microchip.com/downloads/en/DeviceDoc/doc1919.pdf) from Atmel
The [8051 architecture](https://en.wikipedia.org/wiki/MCS-51) was created by Intel in the last 70's. Ok, it's an old architecture, but very simple to understand, and easy to use. 
This chip has the following features:

- 8K Bytes of In-System Programmable (ISP) Flash Memory
- 32 Programmable I/O Line, divided in 4 ports (P0, P1, P2 and P3)
- Three 16-bit Timer/Counters
- 256 bytes on internal RAM
- Eight Interrupt Sources
- Full duplex UART
- Watchdog...

This chip follows the industry-standard 80C51 instruction set and pin-out. It means that you can replace it by a compatible model from an other supplier, they should work the same way.

### Logical and arithmetic operator:
```
ANL A,B   ;and
ORL A,B   ;or
XRL A,B   ;exc-or
CLR A   ;clear accumulator
CPL A   ;complement accumulator

ADD A,#data   ;add data to accumulator
SUBB A,#data   ;subb data to accumulator
INC A   ;increment accumulator
DEC A   ;decrement accumulator
MULL A,B   ;multiply A and B
DIV A,B   ;divide A and B A=quoziente B=resto
CJNE A,#data,rel   ;compare data to accumulator and jump if not equal
DJNE A,rel   ;decrease and jump if not zero
```

### Other:
```
ACC   ;accumulator
B   ;Register B
PSW   ;State register(flag)
SP   ;Stack pointer
Px   ;Port x
SBUF   ;Serial port data buffer
```

### Sample code: 
Read serial port:
```
jnb ri,$   ;read the first value
mov A, SBUF
clr ri
jnb ri,$   ;read the second value
mov B, SBUF
clr ri
add A,B   ;add the result in A
end
```
