# 4 Bit Computer in Verilog [SAP]
- Instruction Set:
    - Add A, B 
    - Sub A, B
    - XCHG B, A
    - mov B, [address]
    - out B
    - jnz Address
    - RCR A
    - mov B, BYTE
    - jmp Address
    - push A
    - pop A
    - CALL Addr
    - RET
    - xor A, [Addr]
    - test B, BYTE
    - HLT

This computer is designed in such a fashion so that all the instructions are executed sequentially.
The instruction pointer for the next instruction is passed at the end of each instruction.

# Instruction 1: ADD A, B
In the first clock cycle, we observe the completion of the add operation which adds the values
stored in register A and B and saves the calculated result in the register A.
# Instruction 2: SUB A,B
In the next instruction, A - B operation is performed. The result is stored in register C. Later the
value stored in C is copied to A and the value in C is overwritten with 0.
# Instruction 3: XCHG B, A
In this case, the value of A is temporarily stored in register C and later the value of B is copied to
register A. Now value stored in B can be replaced with the register value of C to complete the
operation.
# Instruction 4: mov B, [address]
In this case, we are looking at the memory location pointed by the pointer ‘address’. Garbage
values are stored in the MEM at the beginning of the code. So the memory address pointed by the
‘address’ pointer will be copied to register B.
# Instruction 5: OUT B
The value of B is passed to the output buffer OUTPORT.
# Instruction 6: JNZ address
This instruction checks whether the zero flag holds a nonzero value or not. If it holds a nonzero
value the value of the Instruction pointer will be changed to the instruction address pointed by the
pointer ‘address’.
# Instruction 7: RCR A
This instruction rotates the value stored in register A in the right direction and holds it temporarily in
register C. In this case, the carry bit is also associated with the shift operation.
# Instruction 8: MOV B, BYTE
In this instruction, values stored in BYTE will be copied to the register B.
# Instruction 9: JMP Address
In this instruction, the address pointed by address is stored to the instruction pointer so that in the
next clock cycle, the pointed instruction is executed.
# Instruction 10: PUSH A
The value of A is saved to the stack memory at the location pointed by the stack pointer. The value
of stack pointer is increased by one so that if another push command is executed, the new value is
stored at the next memory location of the stack memory.
# Instruction 11: POP A
The value saved in the stack memory is retrieved and saved to the register A. before doing this
operation the value of stack pointer is decreased by one so that it fetches the last saved value from
the stack memory.
# Instruction 12: Call Address
In this case, current instruction pointer value is stored to the stack memory and the value of
instruction pointer is set to the value pointed by Address.
# Instruction 13: RET
Returns to the last instruction pointer saved previously in the stack memory.
# Instruction 14: xor A, [address]
The value stored in the memory address pointed by the ‘address’ pointer, is xored by the value
stored in the register A. The result is temporarily saved in register C. Later this value is moved to
the register A.
# Instruction 15: TEST B, BYTE
This instruction performs AND operation between B and BYTE but discards the result. It only
updates the flags based on the result .
# Instruction 16: HLT
This instruction sets the HLT flag indicating the end of the code.