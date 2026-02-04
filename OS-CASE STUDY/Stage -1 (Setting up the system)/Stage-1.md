# eXpOS Stage 1 – Environment Setup

This stage is the foundation of the eXpOS project. In this stage, the complete development environment required for building and running the Experimental Operating System (eXpOS) is set up. All essential tools, libraries, and project files are installed and compiled successfully.

The system is prepared to support filesystem operations, OS startup programs, SPL compilation, and XSM simulation in later stages.

The following commands were executed to complete this stage:

sudo apt-get install libreadline-dev flex bison make gcc wget curl

This installs all required dependencies such as the compiler, parser generators, build tools, and readline support needed by eXpOS utilities.

Next, the official eXpOS bootstrap script was used to download the project structure and required source files:

curl -sSf https://raw.githubusercontent.com/eXpOSNitc/expos-bootstrap/main/download.sh | sh

After downloading, the project was built using the make utility:

cd $HOME/myexpos
make

This command compiles the XSM simulator, SPL compiler, XFS interface, and other required components.

At the end of this stage, the directory structure for the eXpOS project is created successfully and all tools compile without errors. The system is now fully ready to proceed to filesystem and OS programming stages.
