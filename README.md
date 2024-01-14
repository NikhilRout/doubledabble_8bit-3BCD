# doubledable_8bit-3BCD
Implementation of the Double Dabble Algorithm in Verilog to convert a 8 bit binary number to its 3 digit BCD equivalent (12 bits).\
Also included a general n bit to m digit BCD conversion parameterized module.

## Algorithm
The double dabble SHIFT-ADD-3 algorithm starts with the appropriate number of BCD 4-bit nibbles on the left (initialised to zero) and the binary value on the right. The algorithm starts from here, shifting left, and converting a number in binary to BCD. If a prospective BCD digit is five or larger, add three before shifting left.

<img width="720" alt="image" src="https://github.com/NikhilRout/doubledabble_8bit-3BCD/assets/135248190/ac0a97e9-ec53-41f6-a689-b9a907cc60da">

The rationale for the ADD-3 rule is that whenever the shifted value is 10 or more the weight of that shifted out bit has been reduced to 10 from 16. To compensate, we add 1/2 of that 6, or 3, before shifting. We detect the 10 value after shifting by the fact that the value before shifting is 5 or greater. Notice that the rule ensures that the various digits can never hold any non-BCD values. The shifting is the double part of the algorithm. The ADD-3 is the dabble part.

***From\
An Explanation of the Double-Dabble Bin-BCD Conversion Algorithm\
by C.B. Falconer. 2004-04-16***
