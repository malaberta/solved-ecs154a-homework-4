Download Link: https://assignmentchef.com/product/solved-ecs154a-homework-4
<br>
<h1>Problem 1: CPU.circ</h1>

Build a 4-bit single cycle CPU that can implement the given instructions.




<h2>Instruction Format</h2>

Our CPU will be using fixed length instructions. Our CPU will also have two types of instruction formats: R-type and I-type. In R-type instructions both operands come from registers. In I-type instructions, the first operand comes from a register and the second will be contained within the instruction.

<h3>R-Type</h3>




<table width="624">

 <tbody>

  <tr>

   <td width="150">Name</td>

   <td width="209">Bits</td>

   <td width="265">Description</td>

  </tr>

  <tr>

   <td width="150">OpCode</td>

   <td width="209">15 – 12</td>

   <td width="265">Determines what operation should be performed</td>

  </tr>

  <tr>

   <td width="150">C</td>

   <td width="209">11 – 8</td>

   <td width="265">The destination register. The C in Reg<sub>C</sub> = Reg<sub>A</sub> OP Reg<sub>B</sub></td>

  </tr>

  <tr>

   <td width="150">A</td>

   <td width="209">7 – 4</td>

   <td width="265">The first source register. The A in Reg<sub>C</sub> = Reg<sub>A</sub> OP Reg<sub>B</sub></td>

  </tr>

  <tr>

   <td width="150">B</td>

   <td width="209">3 – 0</td>

   <td width="265">The second source register. The B in Reg<sub>C</sub> = Reg<sub>A</sub> OP Reg<sub>B</sub></td>

  </tr>

 </tbody>

</table>




<h3></h3>

<h3>I-Type</h3>




<table width="624">

 <tbody>

  <tr>

   <td width="150">Name</td>

   <td width="209">Bits</td>

   <td width="265">Description</td>

  </tr>

  <tr>

   <td width="150">OpCode</td>

   <td width="209">15 – 12</td>

   <td width="265">Determines what operation should be performed</td>

  </tr>

  <tr>

   <td width="150">C</td>

   <td width="209">11 – 8</td>

   <td width="265">The destination register. The C in Reg<sub>C</sub> = Reg<sub>A</sub> OP Imm</td>

  </tr>

  <tr>

   <td width="150">A</td>

   <td width="209">7 – 4</td>

   <td width="265">The first source register. The A in Reg<sub>C</sub> = Reg<sub>A</sub> OP Imm</td>

  </tr>

  <tr>

   <td width="150">Immediate</td>

   <td width="209">3 – 0</td>

   <td width="265">The second source register. The Imm in Reg<sub>C</sub> = Reg<sub>A</sub> OP Imm</td>

  </tr>

 </tbody>

</table>




<h2></h2>

<h2>Instructions</h2>




<table width="624">

 <tbody>

  <tr>

   <td width="208">Operation</td>

   <td width="208">Encoding (The value in the OpCodeField)</td>

   <td width="208">Description</td>

  </tr>

  <tr>

   <td width="208">STOP</td>

   <td width="208">0000</td>

   <td width="208">The CPU ceases execution</td>

  </tr>

  <tr>

   <td width="208">NOP</td>

   <td width="208">0001</td>

   <td width="208">Do nothing</td>

  </tr>

  <tr>

   <td width="208">LOAD</td>

   <td width="208">0010</td>

   <td width="208">Reg<sub>C</sub> = Immediate</td>

  </tr>

  <tr>

   <td width="208">MOVE</td>

   <td width="208">0011</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub></td>

  </tr>

  <tr>

   <td width="208">ANDR</td>

   <td width="208">0100</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> AND Reg<sub>B</sub></td>

  </tr>

  <tr>

   <td width="208">ANDI</td>

   <td width="208">0101</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> AND Immediate</td>

  </tr>

  <tr>

   <td width="208">ORR</td>

   <td width="208">0110</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> OR Reg<sub>B</sub></td>

  </tr>

  <tr>

   <td width="208">ORI</td>

   <td width="208">0111</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> OR Immediate</td>

  </tr>

  <tr>

   <td width="208">XORR</td>

   <td width="208">1000</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> XOR Reg<sub>B</sub></td>

  </tr>

  <tr>

   <td width="208">XORI</td>

   <td width="208">1001</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> XOR Immediate</td>

  </tr>

  <tr>

   <td width="208">NOT</td>

   <td width="208">1010</td>

   <td width="208">Reg<sub>C</sub> = NOT Reg<sub>A</sub></td>

  </tr>

  <tr>

   <td width="208">NEGATE</td>

   <td width="208">1011</td>

   <td width="208">Reg<sub>C</sub> = -Reg<sub>A</sub></td>

  </tr>

  <tr>

   <td width="208">ADDR</td>

   <td width="208">1100</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> + Reg<sub>B</sub></td>

  </tr>

  <tr>

   <td width="208">ADDI</td>

   <td width="208">1101</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> +Immediate</td>

  </tr>

  <tr>

   <td width="208">SUBR</td>

   <td width="208">1110</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> – Reg<sub>B</sub></td>

  </tr>

  <tr>

   <td width="208">SUBI</td>

   <td width="208">1111</td>

   <td width="208">Reg<sub>C</sub> = Reg<sub>A</sub> – Immediate</td>

  </tr>

 </tbody>

</table>







<h2></h2>

<h2>Inputs</h2>

<table width="624">

 <tbody>

  <tr>

   <td width="208">Pin</td>

   <td width="208">Size (in bits)</td>

   <td width="208">Explanation</td>

  </tr>

  <tr>

   <td width="208">Instruction</td>

   <td width="208">16</td>

   <td width="208">The instruction located at Instruction_Address</td>

  </tr>

  <tr>

   <td width="208">ClkIn</td>

   <td width="208">1</td>

   <td width="208">The Clock. Connect this to the clock ports of your registers/flip-flops. Do nothing else with this.</td>

  </tr>

 </tbody>

</table>

<h2>Outputs</h2>

<table width="624">

 <tbody>

  <tr>

   <td width="208">Pin</td>

   <td width="208">Size (in bits)</td>

   <td width="208">Explanation</td>

  </tr>

  <tr>

   <td width="208">Instruction_Address_Out</td>

   <td width="208">5</td>

   <td width="208">The address of the instruction you want to execute</td>

  </tr>

  <tr>

   <td width="208">Reg0-15</td>

   <td width="208">4</td>

   <td width="208">The values in the register file. This has already been connected for you</td>

  </tr>

 </tbody>

</table>

<h2>CPU Components</h2>

Your CPU should have

<ul>

 <li>A Program Counter (PC)

  <ul>

   <li>This stores and keeps track of what instruction you are on</li>

  </ul></li>

 <li>Instruction Decoder

  <ul>

   <li>This is a bunch of combinational logic that sets the control signals inside of your CPU</li>

  </ul></li>

 <li>Register File

  <ul>

   <li>A bunch of registers as well as ways to specify which ones you want. This has already been created for you.</li>

   <li>The <strong>only outputs</strong> of the register file that you are allowed to use are A_Out and B_Out. The rest are for testing purposes and <strong>should not be used.</strong> Using them will result in a 50% penalty in your grade.</li>

  </ul></li>

</ul>