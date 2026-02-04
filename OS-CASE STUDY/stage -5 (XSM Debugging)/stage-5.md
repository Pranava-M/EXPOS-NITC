# eXpOS Stage 5 – Debugging with XSM

This stage focuses on debugging SPL programs using the XSM debugger. The breakpoint instruction is used to pause execution and inspect system state.

An SPL program with breakpoints was written:

nano $HOME/myexpos/spl/spl_progs/odd_debug.spl

Program content:

alias counter R0;

counter = 0;

while(counter <= 10) do
    if(counter % 2 != 0) then
        breakpoint;
    endif;
    counter = counter + 1;
endwhile;

The program was compiled:

cd $HOME/myexpos/spl
./spl $HOME/myexpos/spl/spl_progs/odd_debug.spl

The compiled file was loaded as the OS startup program:

cd $HOME/myexpos/xfs-interface
./xfs-interface
load --os $HOME/myexpos/spl/spl_progs/odd_debug.xsm
exit

The XSM simulator was started in debug mode:

cd $HOME/myexpos/xsm
./xsm --debug

Debugger commands were used during execution:

reg  
c  
mem 1  

Execution paused at each breakpoint, allowing inspection of registers and memory. This stage confirms understanding of debugging mechanisms in eXpOS.

---

End of Stage 5.
