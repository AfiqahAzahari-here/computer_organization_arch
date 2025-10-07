ARCTools User Manual

CONTENTS:
1.0 Introduction

2.0 Launching ARCTools
2.1 Creating/Opening ARC Assembly Programs
2.2 Assembling ARC Programs
2.3 Simulating ARC Programs

3.0 Buttons and Controls
3.1 Register Panel:
3.2 Button Panel:
3.3 Machine Execution Viewer:
3.4 Memory Viewer

4.0 Introduction to TimeModel
4.1 Launching TimeModel
4.2 The TimeModel Editor
4.3 Setting the Clock Frequency / Period
4.4 Configuring Instruction Timing
4.5 Shift Instructions
4.6 Memory / IO Parameters

5.0 TimeModel's Statistics Window
5.1 The Cache Simulator View



1.0 Introduction

ARCTools is an assembly language simulator.  The language it uses is call ARC
and is very similar to the assembly language for SPARC.  ARCTools contains an
assembler and simulator for the ARC assembly language.  With ARCTools you can write, assemble and
simulate the execution of ARC assembly programs.  ARCTools now includes an
additional component called TimeModel.  TimeModel simulates the time it takes
to fetch and execute instructions and includes a cache simulator.


2.0 Launching ARCTools

Please see the README-FIRST.txt file; it contains instructions for launching
ARCTools.  The first window you will see after launching ARCTools is the ARC
Simulator window.


2.1 Creating/Opening ARC Assembly Programs

Create a new ARC Assembly Program:
In the ARC Simulator window click on the 'Edit' button.  This will launch
the ASM Edit Window.  From this window you can create an ARC assembly program
by typing it into the text area.  You can also use copy and paste
functionality from the 'Edit' menu to paste a program into the text area.

Open an Existing ARC Assembly Program:
Alternatively, you can open an existing ARC program in the ASM Edit Window by
clicking on 'File' and then 'Open'.  This will present you with n file
chooser dialog where you can select any file with a .asm extension.

Load a pre-assembled ARC Assembly Program:
Yet another way of opening an ARC program is by loading a .bin file, which is
produced by assembling an ARC program (discussed in the next section).  In the
main ARC Simulator window, click on the 'Load' button.  This will present you
with another file chooser dialog, but in this one you must select a file with
a .bin extension.  After making your file selection, the ARC Simulator window
will be loaded with the pre-assembled ARC program and will be ready to
simulate its execution.  The ARC Edit window will also be launched (if not
already) and will be loaded with the .asm, .lst and .bin files associated with
the .bin file selected (.lst files will be discussed in the next section).


2.2 Assembling ARC Programs

You can assemble ARC programs from the ARC Edit window.  To do so, open or
create an ARC program and then press the 'Assemble' button.  If the program
assembles without error, then the listing file will be displayed and the
message box at the bottom of the window will state that the program assembled
successfully.  If the program has errors in it, then a partial listing file
will be displayed with error messages below each line where errors occurred.  The
message box will also report how many errors were found.

Successfully Assembling an ARC Program:
When a program is assembled successfully a number of things happen: a listing
file and a text version of a binary file are generated.  If the ARC program as been
save to a file, then the listing and "binary" files are also save in files in
which the .asm extension is replaced with .lst and .bin, respectively.  You
can always view these files by pressing the 'Show Lst File' and 'Show Binary
File' buttons, even if you have not save the ARC program to file.  You
can also view the ARC program again by pressing the 'Show Asm File'.

2.3 Simulating ARC Programs

To simulate an ARC program, you must have first successfully assembled one in
the ASM Edit window.  Next you need to press the 'Bin->Sim' button in the ASM
Edit window in order to load the ARC Simulator with the program you want to
simulate.  To simulate, press either the 'Step' or 'Run' buttons.  The 'Step'
button will cause the simulator to execute one instruction and then stop.  The
'Run' button will cause the simulator to continuously execute instructions
until the program is stopped.  There are a number of reasons the simulator
will stop continuous execution: 1) if 'Stop' button is pressed2) if the
simulator executes the 'halt' instruction 3) if the program hits a break point
and 4) if the program produces an error such as memory access that is not word
aligned.


3.0 Buttons and Controls

The ARC Simulator has many buttons, text boxes and labels in it.  Let us divide 
the window up into sections.  The first section is the Register Panel, this
is the region above all the buttons in the center.  The next section is the
Button Panel, where all the buttons in the center reside.  The next section is
the Machine Execution Viewer.  The last section is the Memory Viewer and below
that is the Message Console.

3.1 Register Panel:

In the first row of the Register Panel, is the PC followed by check boxes
representing the N, Z, V and C flags.

In the second row, is the label 'ireq', which lights up when an interrupt is
requested.  Next are a check box and some text boxes which represent the ET,
PIL and TBR flags and registers (all privileged).  Finally there are 8 rows of
4 registers which represent the 32 registers in the ARC machine.

All values in the Register Panel can be changed while the simulator is
stopped.

3.2 Button Panel:

Exit - Exits the ARCTools program.
Print - Prints the ARC Simulator window to a printer.
Load - Loads a .bin file into the ARC Simulator.
Reload - Reloads a .bin file into the ARC Simulator, resetting memory and
registers.
Edit - Launches the ASM Edit window.
Step - Simulates one instruction of an ARC program.
Run - Causes continuous simulation of an ARC program.
Stop - Stops the simulator from simulating instructions.
Clear RegFile - Sets registers r0 through r31 to zero.
Clear BreakPts - Clears all program break points.
Clear Memory - Sets all memory locations to zero.
Time Model Editor - Launches the TimeModel Editor window.
Timing Statistics - Launches the statistics and cache simulator window (part
of TimModel).
Hex - Causes all text boxes to display there values in hexadecimal.
Dec - Causes all text boxes to display there values in decimal.
Update Screen - When checked, causes the registers, Memory Execution Viewer
and Memory Viewer to update while an ARC program is being simulated.  When
unchecked, these components do no update during simulation.

3.3 Machine Execution Viewer:

The section shows the addresses of 8 contiguous instructions, the machine
words making up those instructions and the disassembly of the instructions.
The addresses (Loc column) are in editable boxes so you can jump to any place
in your program and view the disassembly (Source Code column) and machine
words (MachWord column).  You can also set a break point (BreakPt column) by
checking a check box next to an instruction. You can also navigate this viewer
with the six buttons at the right of the viewer.  Please note, the action of
"jumping" described above does not change the PC, it simply changes what part
of the program you can view.

3.4 Memory Viewer

This section shows a total of 16 contiguous words of memory arranged in a 4 by
4 grid.  These 16 words appear under the 'Offset' labels.  The 'Loc' column
shows the addresses of the first word in each row.  You can manually change
memory by typing a new value into a memory text box (under the Offset labels).
You can also change the address of the memory you are viewing by typing a new
address into any of the 'Loc' text boxes and pressing 'Enter'.  Alternatively,
you can press any of the eight navigation buttons to the right of the Memory
Viewer.


4.0  Introduction to TimeModel

TimeModel is an extension to the main ARCTools simulator.  It simulates the
time it takes to fetch and execute instructions.  It also has a cache
simulator and simulates the time for memory operations to complete.  TimeModel
as two windows associated with it: a configuration window and a statistics
window.

4.1 Launching TimeModel

To launch TimeModel's configuration window press the "Time Model Editor" button
and to launch the statistics window press the "Timing Statistics" button.

4.2 The TimeModel Editor

The TimeModel Editor is TimeModel's configuration window.  It allows you to
set all the available parameters supported in TimeModel.  At the top of the
TimeModel Editor are three buttons.  This is what they do:
 - Save - Allows you to save your configuration parameters to a file.
 - Open - Allows you to open saved configuration parameters from a file.
 - Configs -> Sim - When you change the values of parameters in TimeModel,
   they have no effect on the simulator until you press this button (even if
   you saved to a file).

4.3 Setting the Clock Frequency / Period

Below the buttons in section 4.2 are two tabs: "Instruction Parameters" and
"Memory / IO Parameters".  Under the Instruction Parameters tab is a place for
you to edit the clock frequency and period of the ARCTools machine.  You can
edit either the frequency or the period, and the other will automatically be
synchronized.

4.4 Configuring Instruction Timing

Also under the Instruction Parameters tab is a place to edit the time for
instructions to execute.  ARCTools has about 50 instructions.  So to make
things a bit easier, the instructions have been divided into categories (e.g.
Arithmetic, Shift, Memory).  Press the "Expand" button next to a category to
see the complete list of instructions under that category.  Press "Collapse"
to hide them again.

To the right of an instruction categories name is a "Clks" box and two
buttons.  These can be used to set the timing of all or part of an instruction
category.  For example, if you would like all Branch instructions to execute
for 7.0 clock cycles, then enter 7.0 into the "Clks" box next to "Branch" and
press "Apply All" (the one to the right of "Branch").  This will pass the
value of 7.0 to all Branch "Clks" boxes.  If you were to press "Apply to
Checked" instead, then only the Branch instruction that are checked will have
their "Clks" boxes updated with 7.0.

If you would like all instructions of all categories to have the same timing,
then use the "Clks" box and the two "Apply" buttons next to the "Default
Instruction Time:" label.  Please note, the "Clks" boxes next to instruction
categories and next to "Default Instruction Time:" are not used by the
simulator, they are simply there to help you set the timing values for
instructions.

4.5 Shift Instructions

Shift Instructions have a variable execution time and their "Clks" boxes are
labeled with "+ (n-1) Clks".  This means shift instructions execute for an
additional n - 1 clocks cycles on top of the value in the "Clks" box, where n
equals the number if bits to be shifted.

4.6 Memory / IO Parameters

Under the Memory / IO Parameters tab, you will find three additional tabs:
"Memory and I/O", "L1 Cache" and "L2 Cache".  The "Memory and I/O" tab allows
you to set the read/write time to main memory and the ready time for the CRT
device.

The "L1 Cache" and "L2 Cache" tabs have the same content and allow you to
configure the L1 and L2 caches.  The available parameters include:
 - Enabling the cache
 - Cache Size
 - Block Size (cache line size)
 - Bus width
 - Level of Associativity
 - Replacement Algorithm (replacement in the event of a cache line eviction)
 - Read Hit Time
 - Read Miss Time
 - Write Time
 - Write Policy (Write Through vs. Write Back)
 - Write Allocation (Allocation a cache lines upon a write miss)


5.0 TimeModel's Statistics Window

TimeModel's Statistics Window gathers statistics on the ARC program being
simulated.  Specifically it allows you to view the statistics of the most
recently executed instruction, a graphical view of the L1 and L2 caches, and a
log history of instructions that have executed in your ARC program.

The "Execution Statistics" text area shows the statistics of the most recently
executed instruction.  It breaks the execution time of an instruction into its
various parts (i.e. fetch time, execution time, memory operations etc.).
The "L1 Statistics" and "L2 Statistics" show the statistic for the L1 and L2
cache, such as the number of read hits and misses, writes, line evictions, etc.

Below "Execution Statistics" is the "Time Trace Log".  Each time an
instruction is simulated, an entry is added to the Time Trace Log.  Each
entry is a concatenation of the statistics in "Execution Statistics", "L1
Statistics" and "L2 Statistics".  Entries can only be added if the Statistics
Window is open, and by default entries are not added to the Time Trace Log.
You can activate logging with the "Don't log" check box. The reason for this
default is if the log gets very large it will slow the progress of the
simulator down.  Also, you can also clear the log using the "Clear Log"
button.

The Statistics Window has several "Update" check boxes that enable/disable the
updating of the statistics while ARCTools is actively simulating a program
(when the "Run" button is pressed in the main simulator).  If the simulator
stops for any reason, all statistics items will update automatically to the
freshest set of statistics.

5.1 The Cache Simulator View

Below the Time Trace Log is a view of the cache simulator.  The L1 and L2
cache are represented graphically by large blue rectangles.  The rectangles are
divided into a number of rows (indicated by the "Number of Rows" box) and a
number of columns, which is calculated by TimeModel.  The rows and columns
divide the larger rectangle in to a number of smaller rectangles (cache line
rectangles) and each
smaller rectangle represents a cache line (or cache block).  Cache line
rectangles are not necessarily visible until simulation has began.  During
simulation, unused cache lines remain blue, clean cache lines become green and
dirty cache lines turn red.

Graphical Arrangement of the Cache Lines:
Cache lines in the graphic are arranged by row and all cache lines of an
associative set are considered contiguous.  Therefore, the top left cache line
rectangle represents the first line of the cache, and the next cache line
rectangle (to the right of the first rectangle) represents the second line of
the cache.  For a 2-ways set associative cache, the first and second cache
lines are the first and second cache lines in the first associative set.
