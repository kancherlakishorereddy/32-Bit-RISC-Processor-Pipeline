# 32-Bit-RISC-Processor-Pipeline

This was my Academic Project for Computer Archtecture course during 5th semester at IITBBS. <br> Please read the /README.md completely for clear understandig of the project and how to test it by yourself. 

## Description

This five stage pipeline has a hardwired control unit, dual port register file with 32 GPRs. The memoy address is 24-Bit wide and Data bit width is 32-Bit. You can add more bits to the memory address by adding more RAM components in logisim and multiplex between them.

## Files Description

* Requirements.pdf : <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The requirements according  to which the pipeline was designed. 

* Circuit Design.pdf : <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A Block Diagram of the circuit and a 5-stage architecture view of the whole circuit.

* Main.circ : <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The logisim circuit file of the pipeline, including all the subcircuits.

* Instruction Encoding.pdf : <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Instruction Encoding Scheme I followed, which you will need to convert your assembly code into machine code if you want to test the circuit against new programs.

* Sample Programs.pdf : <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The sample programs used to test the pipeline. The hexadecimal format of the machine code for these two programs is attached in the Instruction Encoding.pdf for ease of testing. However you can write your own programs and test them.

### Note:
   * Check Requirements.pdf before writing your own assembly code to know which instructions are suported and which are not.
   * The RAM component in logisim is used to simulate the memory. So you'll have to convert your machine code which is in binary to a hexadecimal format to load it in the memory.
   * I've done this conversion for the sample programs in Sample Programs.pdf and attached the code in Instruction Encoding.pdf
   * Read the following section to understnad how to test this circuit or just run your own machine codes.

## Testing: <br>
To test any program you **SHOULD FOLLOW** these steps:

* Hit Reset Simulation (CTRL + R) in Logisim. Also disable the ticks.
* Using Poke tool double click on the Memory block in the Main circuit (NOT the Memory Sub-Circuit in the left window pane) to open the Memory sub-circuit.
* Right click on the RAM and select Edit Contents to load the instructions or data in the memory in HEX format. Remember the address of the first instruction.
* Using Poke tool double click on the Control Unit block in the Main circuit (NOT the Control Unit Sub-Circuit in the left window pane) to open the Control Unit sub-circuit.
* Using Poke tool set the value of counter to ‘4’ indicating that stage-5 has completed. So that in the next tick counter starts from 0 analogous to fresh start from stage-1 of pipeline.
* Using Poke tool double click on the Fetch block in the Main circuit (NOT the Fetch Stage Sub-Circuit in the left window pane) to open the Fetch Stage sub-circuit.
* Using Poke tool set the PC to the address of the first instruction of your program in the memory.
* Now hit Enable Ticks and the circuit will start executing your program.
* The HLT instruction at the end will not stop the ticking in the logisim. It only stops the counter I am using to know the currently active stage in the pipline. As a result the pipeline will not fetch anymore istructions.

### Please Star :star:  the repo to show your appreciation. And let me know if you've any suggestions or something is not clear about the project.
