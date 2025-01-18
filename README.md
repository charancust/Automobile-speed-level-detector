# Automobile-speed-level-detector
This project involves the simulation and implementation of an automobile speed level detector using digital ICs.

## Problem statement:

An automobile speed sensor provides a 4-bit encoded reading S3 S2 S1 S0 in intervals of one. Design a decoder with the following outputs:

i)slow, denoted by 's' which is asserted when the sensor output is between 0 and 5. 

ii)economy, denoted by 'e' which is asserted when the sensor output is between 6 and 12.

iii) fast, denoted by 'f' which is asserted when the sensor output is between 13 and 15.

## Goal:

(a)Design a decoder for the above system. 

(b)Design a circuit for displaying "1", "2" and "3" in a seven segment display when the respective outputs s, e and f are asserted.

## Implementaion:

1. Designing the decoder:

   Truth table for the decoder:

       Inputs             Outputs      
   
    | S3 | S2 | S1 | S0 | s | e | f |
    |----|----|----|----|---|---|---|
    | 0  | 0  | 0  | 0  | 1 | 0 | 0 |
    | 0  | 0  | 0  | 1  | 1 | 0 | 0 |
    | 0  | 0  | 1  | 0  | 1 | 0 | 0 |
    | 0  | 0  | 1  | 1  | 1 | 0 | 0 |
    | 0  | 1  | 0  | 0  | 1 | 0 | 0 |
    | 0  | 1  | 0  | 1  | 1 | 0 | 0 |
    | 0  | 1  | 1  | 0  | 0 | 1 | 0 |
    | 0  | 1  | 1  | 1  | 0 | 1 | 0 |
    | 1  | 0  | 0  | 0  | 0 | 1 | 0 |
    | 1  | 0  | 0  | 1  | 0 | 1 | 0 |
    | 1  | 0  | 1  | 0  | 0 | 1 | 0 |
    | 1  | 0  | 1  | 1  | 0 | 1 | 0 |
    | 1  | 1  | 0  | 0  | 0 | 1 | 0 |
    | 1  | 1  | 0  | 1  | 0 | 0 | 1 |
    | 1  | 1  | 1  | 0  | 0 | 0 | 1 |
    | 1  | 1  | 1  | 1  | 0 | 0 | 1 |

   The corresponding minterms for s, e, and f are:

   $$s = \sum_{m}^{}(0,1,2,3,4,5)$$

   $$e = \sum_{m}^{}(6,7,8,9,10,11,12)$$

   $$f = \sum_{m}^{}(13,14,15)$$

2. Driving the seven segment display using the 4-bit encoded sensor outputs:

   Truth table for the sevent segment display:

       Inputs                 Outputs

   | S3 | S2 | S1 | S0 | a | b | c | d | e | f | g |
   | -- | -- | -- | -- | - | - | - | - | - | - | - |
   | 0  | 0  | 0  | 0  | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
   | 0  | 0  | 0  | 1  | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
   | 0  | 0  | 1  | 0  | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
   | 0  | 0  | 1  | 1  | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
   | 0  | 1  | 0  | 0  | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
   | 0  | 1  | 0  | 1  | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
   | 0  | 1  | 1  | 0  | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
   | 0  | 1  | 1  | 1  | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
   | 1  | 0  | 0  | 0  | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
   | 1  | 0  | 0  | 1  | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
   | 1  | 0  | 1  | 0  | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
   | 1  | 0  | 1  | 1  | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
   | 1  | 1  | 0  | 0  | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
   | 1  | 1  | 0  | 1  | 1 | 1 | 1 | 1 | 0 | 0 | 1 |
   | 1  | 1  | 1  | 0  | 1 | 1 | 1 | 1 | 0 | 0 | 1 |
   | 1  | 1  | 1  | 1  | 1 | 1 | 1 | 1 | 0 | 0 | 1 |

   Respective equations:

   a = S2S1 + S3
   
   b = 1
   
   c = S3'S2' + S3'S1' + S3S2S1 + S2S1S0
   
   d = S2S1 + S3

   e = S3'S2S1 + S3S2' + S3S1'S0'

   f = 0

   g	= S2S1 +S3

## Simulation:

The simulation was done using proteus 8. 

Refer to the 'asld.pdsprj' for the simulation file.

## Hardware implementaion:

Refer to the components list for the components needed.

The 74 series of ICs were used.

Refer to the datasheets for the pin configuration.

An arduino UNO was used to give the supply voltage Vcc of 5V.

Pin configuration of the common cathode 7 segment display

![image](https://github.com/user-attachments/assets/7558ab17-362e-411a-a97b-f9dc50fe9c23)


While connecting the ground pins (3 and 8) to the ground use current limiting resistors to prevent the seven segment display from getting burnt.

This is the final image of the circuit:

![image](https://github.com/user-attachments/assets/7a23be9a-c7fa-480e-86b2-4e31b3f38a91)




   


   



