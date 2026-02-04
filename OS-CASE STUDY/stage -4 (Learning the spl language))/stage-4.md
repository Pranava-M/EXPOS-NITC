# eXpOS Stage 4 – SPL Programming

This stage introduces SPL (System Programming Language), a higher-level language that compiles into XSM assembly. SPL allows the use of variables, loops, and conditional statements.

An SPL program to print odd numbers was written:

nano $HOME/myexpos/spl/spl_progs/oddnos.spl

Program content:

alias counter R0;

counter = 0;

while(counter <= 20) do
    if(counter % 2 != 0) then
        print counter;
    endif;
    counter = counter + 1;
endwhile;

The SPL program was compiled using the SPL compiler:

cd $HOME/myexpos/spl
./spl $HOME/myexpos/spl/spl_progs/oddnos.spl

The generated XSM file was loaded as the OS startup program:

cd $HOME/myexpos/xfs-interface
./xfs-interface
load --os $HOME/myexpos/spl/spl_progs/oddnos.xsm
exit

The program was executed using the XSM simulator:

cd $HOME/myexpos/xsm
./xsm

The output displayed odd numbers up to 20, confirming correct SPL compilation and execution.
