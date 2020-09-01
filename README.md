# x86utm
This is an x86 based Universal Turing Machine (UTM) that directly executes COFF object files generated by the Microsoft "C" compiler. 
There are two restrictions on the "C" code that can be executed in this virtual machine: (1) All global data must be initalized. 
(2) No library function can be called. The UTM environment is like a tiny little operating system here are its only functions:

u32* Allocate(u32 size);------------------------------// allocates memory from HeapSpace.<br>
u32 DebugStep(u32* master_state, u32* slave_state);---// executes a slave UTM in single debug-step mode <br>
u32 SaveState(u32* state_data); ----------------------// Saves the execution state of a UTM to state_data<br>
u32 LoadState(u32* state_data);-----------------------// Loads the execution state of a UTM from state_data<br>

When a UTM is running the execution trace of each assembly language instruction / operating system function call is provided. 
