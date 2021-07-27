# Signal structure

the data are always in pairs and offset by one column. For example, the fan level is in column 5 and is inverted in column 7

5 and 7 fan level (0 - 3) // 0 is auto fan / auto mode only acept fan 0
6 and 8 function (Swing, LED off/on, OFF)
9 and 11 temperature (17 - 30 C˚)
10 and 12 mode (auto, cool, heat, dry)

a data record is introduced by 4400 4400 then the data follow in the format 1 = 550 1650 and 0 = 550 550. At the end comes 5500 and a repetition of the data

4400  4400  DATA  5500  4400  4400  DATA

|1 ? |2 ?   |3 ?   |4 ?   |5 fan |6 func|7 fan |8 func|9 temp|10 mode   |11 temp|12 mode    |Mode  |C˚  |FAN Level
|----|------|------|------|------|------|------|------|------|------|------|------|------|----|---
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0000 | 1000 | 1111 | 0111 | Auto | 17 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0001 | 1000 | 1110 | 0111 | Auto | 18 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0011 | 1000 | 1100 | 0111 | Auto | 19 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0010 | 1000 | 1101 | 0111 | Auto | 20 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0110 | 1000 | 1001 | 0111 | Auto | 21 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0111 | 1000 | 1000 | 0111 | Auto | 22 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0101 | 1000 | 1010 | 0111 | Auto | 23 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0100 | 1000 | 1011 | 0111 | Auto | 24 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1100 | 1000 | 0011 | 0111 | Auto | 25 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1101 | 1000 | 0010 | 0111 | Auto | 26 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1001 | 1000 | 0110 | 0111 | Auto | 27 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1000 | 1000 | 0111 | 0111 | Auto | 28 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1010 | 1000 | 0101 | 0111 | Auto | 29 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1011 | 1000 | 0100 | 0111 | Auto | 30 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0000 | 0000 | 1111 | 1111 | Cool | 17 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0001 | 0000 | 1110 | 1111 | Cool | 18 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0011 | 0000 | 1100 | 1111 | Cool | 19 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0010 | 0000 | 1101 | 1111 | Cool | 20 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0110 | 0000 | 1001 | 1111 | Cool | 21 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0111 | 0000 | 1000 | 1111 | Cool | 22 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0101 | 0000 | 1010 | 1111 | Cool | 23 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0100 | 0000 | 1011 | 1111 | Cool | 24 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1100 | 0000 | 0011 | 1111 | Cool | 25 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1101 | 0000 | 0010 | 1111 | Cool | 26 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1001 | 0000 | 0110 | 1111 | Cool | 27 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1000 | 0000 | 0111 | 1111 | Cool | 28 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1010 | 0000 | 0101 | 1111 | Cool | 29 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1011 | 0000 | 0100 | 1111 | Cool | 30 | 0
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0000 | 0000 | 1111 | 1111 | Cool | 17 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0001 | 0000 | 1110 | 1111 | Cool | 18 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0011 | 0000 | 1100 | 1111 | Cool | 19 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0010 | 0000 | 1101 | 1111 | Cool | 20 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0110 | 0000 | 1001 | 1111 | Cool | 21 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0111 | 0000 | 1000 | 1111 | Cool | 22 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0101 | 0000 | 1010 | 1111 | Cool | 23 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0100 | 0000 | 1011 | 1111 | Cool | 24 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1100 | 0000 | 0011 | 1111 | Cool | 25 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1101 | 0000 | 0010 | 1111 | Cool | 26 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1001 | 0000 | 0110 | 1111 | Cool | 27 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1000 | 0000 | 0111 | 1111 | Cool | 28 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1010 | 0000 | 0101 | 1111 | Cool | 29 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1011 | 0000 | 0100 | 1111 | Cool | 30 | 1
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0000 | 0000 | 1111 | 1111 | Cool | 17 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0001 | 0000 | 1110 | 1111 | Cool | 18 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0011 | 0000 | 1100 | 1111 | Cool | 19 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0010 | 0000 | 1101 | 1111 | Cool | 20 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0110 | 0000 | 1001 | 1111 | Cool | 21 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0111 | 0000 | 1000 | 1111 | Cool | 22 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0101 | 0000 | 1010 | 1111 | Cool | 23 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0100 | 0000 | 1011 | 1111 | Cool | 24 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1100 | 0000 | 0011 | 1111 | Cool | 25 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1101 | 0000 | 0010 | 1111 | Cool | 26 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1001 | 0000 | 0110 | 1111 | Cool | 27 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1000 | 0000 | 0111 | 1111 | Cool | 28 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1010 | 0000 | 0101 | 1111 | Cool | 29 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1011 | 0000 | 0100 | 1111 | Cool | 30 | 2
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0000 | 0000 | 1111 | 1111 | Cool | 17 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0001 | 0000 | 1110 | 1111 | Cool | 18 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0011 | 0000 | 1100 | 1111 | Cool | 19 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0010 | 0000 | 1101 | 1111 | Cool | 20 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0110 | 0000 | 1001 | 1111 | Cool | 21 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0111 | 0000 | 1000 | 1111 | Cool | 22 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0101 | 0000 | 1010 | 1111 | Cool | 23 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0100 | 0000 | 1011 | 1111 | Cool | 24 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1100 | 0000 | 0011 | 1111 | Cool | 25 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1101 | 0000 | 0010 | 1111 | Cool | 26 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1001 | 0000 | 0110 | 1111 | Cool | 27 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1000 | 0000 | 0111 | 1111 | Cool | 28 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1010 | 0000 | 0101 | 1111 | Cool | 29 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1011 | 0000 | 0100 | 1111 | Cool | 30 | 3
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0000 | 1100 | 1111 | 0011 | Heat | 17 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0001 | 1100 | 1110 | 0011 | Heat | 18 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0011 | 1100 | 1100 | 0011 | Heat | 19 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0010 | 1100 | 1101 | 0011 | Heat | 20 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0110 | 1100 | 1001 | 0011 | Heat | 21 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0111 | 1100 | 1000 | 0011 | Heat | 22 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0101 | 1100 | 1010 | 0011 | Heat | 23 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 0100 | 1100 | 1011 | 0011 | Heat | 24 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1100 | 1100 | 0011 | 0011 | Heat | 25 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1101 | 1100 | 0010 | 0011 | Heat | 26 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1001 | 1100 | 0110 | 0011 | Heat | 27 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1000 | 1100 | 0111 | 0011 | Heat | 28 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1010 | 1100 | 0101 | 0011 | Heat | 29 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1011 | 1100 | 0100 | 0011 | Heat | 30 | 0
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0000 | 1100 | 1111 | 0011 | Heat | 17 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0001 | 1100 | 1110 | 0011 | Heat | 18 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0011 | 1100 | 1100 | 0011 | Heat | 19 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0010 | 1100 | 1101 | 0011 | Heat | 20 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0110 | 1100 | 1001 | 0011 | Heat | 21 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0111 | 1100 | 1000 | 0011 | Heat | 22 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0101 | 1100 | 1010 | 0011 | Heat | 23 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 0100 | 1100 | 1011 | 0011 | Heat | 24 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1100 | 1100 | 0011 | 0011 | Heat | 25 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1101 | 1100 | 0010 | 0011 | Heat | 26 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1001 | 1100 | 0110 | 0011 | Heat | 27 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1000 | 1100 | 0111 | 0011 | Heat | 28 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1010 | 1100 | 0101 | 0011 | Heat | 29 | 1
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1011 | 1100 | 0100 | 0011 | Heat | 30 | 1
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0000 | 1100 | 1111 | 0011 | Heat | 17 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0001 | 1100 | 1110 | 0011 | Heat | 18 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0011 | 1100 | 1100 | 0011 | Heat | 19 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0010 | 1100 | 1101 | 0011 | Heat | 20 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0110 | 1100 | 1001 | 0011 | Heat | 21 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0111 | 1100 | 1000 | 0011 | Heat | 22 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0101 | 1100 | 1010 | 0011 | Heat | 23 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 0100 | 1100 | 1011 | 0011 | Heat | 24 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1100 | 1100 | 0011 | 0011 | Heat | 25 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1101 | 1100 | 0010 | 0011 | Heat | 26 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1001 | 1100 | 0110 | 0011 | Heat | 27 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1000 | 1100 | 0111 | 0011 | Heat | 28 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1010 | 1100 | 0101 | 0011 | Heat | 29 | 2
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1011 | 1100 | 0100 | 0011 | Heat | 30 | 2
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0000 | 1100 | 1111 | 0011 | Heat | 17 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0001 | 1100 | 1110 | 0011 | Heat | 18 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0011 | 1100 | 1100 | 0011 | Heat | 19 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0010 | 1100 | 1101 | 0011 | Heat | 20 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0110 | 1100 | 1001 | 0011 | Heat | 21 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0111 | 1100 | 1000 | 0011 | Heat | 22 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0101 | 1100 | 1010 | 0011 | Heat | 23 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 0100 | 1100 | 1011 | 0011 | Heat | 24 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1100 | 1100 | 0011 | 0011 | Heat | 25 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1101 | 1100 | 0010 | 0011 | Heat | 26 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1001 | 1100 | 0110 | 0011 | Heat | 27 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1000 | 1100 | 0111 | 0011 | Heat | 28 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1010 | 1100 | 0101 | 0011 | Heat | 29 | 3
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1011 | 1100 | 0100 | 0011 | Heat | 30 | 3
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0000 | 0100 | 1111 | 1011 | Dry  | 17 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0001 | 0100 | 1110 | 1011 | Dry  | 18 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0011 | 0100 | 1100 | 1011 | Dry  | 19 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0010 | 0100 | 1101 | 1011 | Dry  | 20 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0110 | 0100 | 1001 | 1011 | Dry  | 21 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0111 | 0100 | 1000 | 1011 | Dry  | 22 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0101 | 0100 | 1010 | 1011 | Dry  | 23 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 0100 | 0100 | 1011 | 1011 | Dry  | 24 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1100 | 0100 | 0011 | 1011 | Dry  | 25 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1101 | 0100 | 0010 | 1011 | Dry  | 26 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1001 | 0100 | 0110 | 1011 | Dry  | 27 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1000 | 0100 | 0111 | 1011 | Dry  | 28 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1010 | 0100 | 0101 | 1011 | Dry  | 29 | 0
1011 | 0010 | 0100 | 1101 | 0001 | 1111 | 1110 | 0000 | 1011 | 0100 | 0100 | 1011 | Dry  | 30 | 0
1011 | 0010 | 0100 | 1101 | 1011 | 1111 | 0100 | 0000 | 1110 | 0100 | 0001 | 1011 | FAN  |    | 0
1011 | 0010 | 0100 | 1101 | 1001 | 1111 | 0110 | 0000 | 1110 | 0100 | 0001 | 1011 | FAN  |    | 1
1011 | 0010 | 0100 | 1101 | 0101 | 1111 | 1010 | 0000 | 1110 | 0100 | 0001 | 1011 | FAN  |    | 2
1011 | 0010 | 0100 | 1101 | 0011 | 1111 | 1100 | 0000 | 1110 | 0100 | 0001 | 1011 | FAN  |    | 3
1011 | 0010 | 0100 | 1101 | 0110 | 1011 | 1001 | 0100 | 1110 | 0000 | 0001 | 1111 | Swing|    | 
1011 | 0101 | 0100 | 1010 | 1111 | 0101 | 0000 | 1010 | 1010 | 0101 | 0101 | 1010 | LED  |    | 
1011 | 0010 | 0100 | 1101 | 0111 | 1011 | 1000 | 0100 | 1110 | 0000 | 0001 | 1111 | OFF  |    | 	
