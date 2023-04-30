Download Link: https://assignmentchef.com/product/solved-cs2400-homework5-read-and-convert-a-32-bit-2s-complement-into-a-signed-decimal-string
<br>
Write an ARM program to read and convert a 32-bit 2’s complement into a signed <strong>decimal</strong> string

<ul>

 <li>in the data area, o Declare and initialize a <strong><em>null-terminated string</em></strong> with a label of <strong>HexStr</strong> and an initial value of your choice (each byte is the ASCII of a Hex symbol in this 32-bit 2’s complement number). For example, the string could be “A8F”, 0.

  <ul>

   <li>declare and initialize a signed word as 0, label this word as <strong>TwosComp</strong></li>

   <li>reserved a chunk of zeroed memory with a length of 12 bytes, label this chunk of memory as <strong>DecStr</strong></li>

  </ul></li>

</ul>

(why a length of 12 bytes is enough?) o reserved a chunk of zeroed memory with a length of 11 bytes, label this chunk of memory as <strong>RvsDecStr</strong>

(why a length of 11 bytes is enough?) o Store each one of the above four labels as a word with an address label, e.g., “adrHexStr DCD HexStr” for HexStr, and <strong>EXPORT</strong> each address label, e.g., “EXPORT adrHexStr”.

<ul>

 <li>in the main program, o read the ASCII’s of up to eight symbols of a Hex number (e.g., 1A2B3D4D or FFF4B3FA) symbol by symbol from the memory at HexStr, and convert this list of symbols in ASCII into a 32-bit two’s complement number. You may assume that this Hex number will be zero-extended if less than eight symbols are read, i.e., the missing leading symbols are zeros (e.g., A79 means 00000A79).

  <ul>

   <li>store this 32-bit 2’s complement number at TwosComp.</li>

   <li>convert the 32-bit signed number at TwosComp to a NULL terminated ASCII string, each byte is the ASCII of the <strong>minus sign</strong> or a <strong>digit</strong> in this number. A minus sign, ‘–‘, needs to be placed at the beginning if this number is negative. E.g., if [TwosComp] = 0x1A2B3C4D, then it should be converted into “439041101” ; if [TwosComp] = 0xFFF4B3FA, then it should be converted into “–740358” .

    <ul>

     <li>Hint: when you keep dividing the <strong>absolute value of this number </strong>by 10, the list of remainders that you obtain are the digits whose ASCIIs are going to be stored at DecStr. However, the first remainder is the Least Significant Digit and the last remainder is the Most Significant Digit!</li>

     <li>Therefore, you might want to store the ASCIIs of the digits you obtained through division to RvsDecStr first, then reversely store them to the memory at DecStr.</li>

    </ul></li>

   <li>write a your own <strong>subroutine</strong> to divide a <strong>positive</strong> 32-bit number by <strong>10</strong> and put the <strong>quotient</strong> and the <strong>remainder</strong> in two registers, respectively, as the output parameters.</li>

   <li>call this subroutine for division-by-10 while converting the signed number into its decimal equivalent.</li>

  </ul></li>

</ul>

You are NOT allowed to call <strong>the division subroutine</strong> that is provided by the emulator.

<ul>

 <li>Store this decimal string as a NULL-terminated string to memory labeled as DecStr.</li>

</ul>





