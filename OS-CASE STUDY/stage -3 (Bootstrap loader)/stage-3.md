# eXpOS Stage 3 – Bootstrap Loader

This stage introduces the concept of an OS startup program in eXpOS. A simple XSM assembly program is written and loaded as the operating system image to verify the boot process.

A directory for SPL and XSM programs was created:

mkdir -p $HOME/myexpos/spl/spl_progs

A basic XSM program was written to print a message on the screen:

nano $HOME/myexpos/spl/spl_progs/helloworld.xsm

Program content:

MOV R0, "HELLO_WORLD"
MOV R16, R0
PORT P1, R16
OUT
HALT

The program was loaded into the OS boot block using the XFS interface:

cd $HOME/myexpos/xfs-interface
./xfs-interface
load --os $HOME/myexpos/spl/spl_progs/helloworld.xsm
exit

The XSM simulator was then started:

cd $HOME/myexpos/xsm
./xsm

The message HELLO_WORLD was displayed on execution, confirming that the OS startup code was successfully loaded and executed. This stage demonstrates how boot-time OS code works in eXpOS.
