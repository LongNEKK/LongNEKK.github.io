

---
layout: project
type: project
image: img/punyC.jpg
title: "PunyC: A ByteSized Computer"
date: 2024
published: true
labels:
  - Computer Archictecture
  - Verilog
  - MIPS ISA 
summary: "I developed a simulation of a small computer using standard practices for pipelining, operation implementation, and memory operations in Verilog called PunyC."
---

In this project, I developed a small "computer" that was capable of fetching instructions, executing instructions, and reading and writing to memory. This involved the implementations of the different stages of the instruction pipeline as well as the architecture where memory is read and written from. In addition, individual opcodes were designed and then implemented in a testbench file to represent a computer running a real set of instructions. An excerpt of my code that essentially acts as my "main" in the verilog program has various wires and registers defined as well as the different opcodes. In addition, the pc logic for moving between instructions as well as the ALU is written here. 



```cpp

`include "define.sv"
`include "prog.sv"
`include "prog1.sv"
`include "prog2.sv"

module puny2(
  input instrValue instr,
  input logic clk,
  input logic reset,
  output logic [7:0] pc
);
  
  pcSelValue pcSel;
  logic raWrite;
  logic rfileWrite;
  aluSelValue aluSel;
  aluInSelValue aluInSel;
  logic [7:0] rfile [0:3];
  logic [7:0] aluA, aluB, aluOutput;
  logic [7:0] raReg;
  
  always_ff @(posedge clk) // Return address register
    if (raWrite==1)
      raReg <= pc+1;
 
  assign aluA=rfile[instr.src1]; // Register file
  
  always_ff @(posedge clk)
    if (rfileWrite==1) rfile[instr.dst] = aluOutput;
  
  always_comb  // ALU mux
    begin
      case(aluInSel)
        REG: aluB = rfile[instr.src2];
        IMM: aluB = instr.imm;
       endcase
    end
  
  
  always_comb // ALU
    begin
    case(aluSel)
      ADD: aluOutput=aluA+aluB;
      SUB: aluOutput=aluA-aluB;
      PASSA: aluOutput = aluA;
      PASSB: aluOutput = aluB;
      default: aluOutput = 0;
    endcase
    end

  always_ff @(posedge clk) // PC logic
    begin
      if (reset==1) 
        begin
          pc<=0;
        end
      else
        case(pcSel)
          INC: pc<=pc+1;
          J: pc<=instr.imm;
          JZ: if (rfile[instr.src1]== 0) pc<=instr.imm; else pc<=pc+1;
          CALL: pc<=instr.imm; 
          RET: pc<=raReg;
          default: pc<=pc+1;
        endcase
    end
  
  
  always_comb // Controller
    begin
      case(instr.opcode)
        opJ:
          begin
            pcSel=J;
            rfileWrite=0;
            raWrite=0;
            aluSel=ADD;
            aluInSel=IMM;
          end
        opSET:
          begin
            pcSel=INC;
            rfileWrite=1;
            raWrite=0;
            aluSel=PASSB;
            aluInSel=IMM;
          end
        opADD:
          begin
            pcSel=INC;
            rfileWrite=1;
            raWrite=1;
            aluSel=ADD;
            aluInSel=REG;
          end
        opSUB:
          begin
            pcSel=INC;
            rfileWrite=1;
            raWrite=1;
            aluSel=SUB;
            aluInSel=REG;
          end
        opADDI:
          begin
            pcSel=INC;
            rfileWrite=1;
            raWrite=0;
            aluSel=ADD;
            aluInSel=IMM;
          end
        opSUBI:
          begin
            pcSel=INC;
            rfileWrite=1;
            raWrite=0;
            aluSel=SUB;
            aluInSel=IMM;
          end
        opJZ:
          begin
            pcSel=JZ;
            rfileWrite=0;
            raWrite=0;
            aluSel=ADD;
            aluInSel=IMM;
          end
        opCALL:
          begin
            pcSel=CALL;
            rfileWrite=0;
            raWrite=1;
            aluSel=ADD;
            aluInSel=IMM;
          end
        opRET:
          begin
            pcSel=RET;
            rfileWrite=0;
            raWrite=0;
            aluSel=ADD;
            aluInSel=IMM;
          end
        default:
          begin
            pcSel=INC;
            rfileWrite=0;
            raWrite=0;
            aluSel=PASSB;
            aluInSel=IMM;
          end
      endcase
    end
  
endmodule:  puny2
```
