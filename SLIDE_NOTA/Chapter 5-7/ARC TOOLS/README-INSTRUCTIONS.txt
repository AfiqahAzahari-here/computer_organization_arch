Authors:
Ross Zwisler, Shane Neuville, Vincent P. Heuring and Michael Wilson
Department of Electrical and Computer Engineering
University of Colorado-Boulder
Boulder CO 80309-0425

As of ARCTools version 2.0.3, the following ARC instructions are supported:
ADD
AND
ANDN
ADDCC
ANDCC
ANDNCC
BA
BN
BNE
BE
BG
BLE
BGE
BL
BGU
BLEU
BCC
BCS
BPOS
BNEG
BVC
BVS
CALL
JMPL
LD
LDSB
LDSH
LDUB
LDUH
OR
ORN
ORCC
ORNCC
RD
RETT
SETHI
ST
STB
STH
SRL
SLL
SRA
SUB
SUBCC
TA
WR
XOR
XNOR
XORCC
XNORCC

Also, the following synthetic instructions are supported:
Synthetic Instruction   Instruction Generated           Comment
not rs1, rd             xnor rs1, %r0, rd               1's complement
neg rs2, rd             sub %r0, rs2, rd                2's complement
inc rd                  add rd, 1, rd                   increment by 1
dec rd                  sub rd, 1, rd                   decrement by 1
clr rd                  and rd, %r0, rd                 clear a register
cmp rs1, reg_or_imm     subcc rs1, reg_or_imm, %r0      compare, set cc's
tst rs2                 orcc %r0, rs2, %r0              test
mov reg_or_imm, rd      or %r0, reg_or_imm, rd          move a value
