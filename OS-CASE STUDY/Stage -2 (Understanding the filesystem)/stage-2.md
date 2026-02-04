# eXpOS Stage 2 – Understanding the File System

In this stage, the eXpOS filesystem (eXpFS) is explored using the XFS interface. The objective is to understand how files are created, stored, and managed inside the XSM disk.

The XFS interface was launched and the disk was formatted using the fdisk command:

cd ~/myexpos/xfs-interface
./xfs-interface
fdisk
exit

A sample data file was then created in the host Linux system:

cd ~/myexpos
echo "Hello eXpOS Stage-2" > sample.dat
echo "This is a sample file." >> sample.dat
cat sample.dat

The created file was loaded into the XSM disk using the XFS interface:

cd ~/myexpos/xfs-interface
./xfs-interface
load --data /home/vboxuser/myexpos/sample.dat
ls
exit

To understand the internal structure of the filesystem, the inode user table and root file were dumped:

cd ~/myexpos/xfs-interface
./xfs-interface
dump --inodeusertable
dump --rootfile
exit

The dumped tables were viewed using:

cat inodeusertable.txt
cat rootfile.txt

Finally, the loaded file and disk free list were verified:

cd ~/myexpos/xfs-interface
./xfs-interface
ls
cat sample.dat
df
exit

This stage confirms that files can be successfully loaded into the XSM disk and that filesystem metadata such as inodes, root directory, and free disk blocks can be inspected.
