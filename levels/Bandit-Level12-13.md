##Bandit level 12-13


###Objective
Retrieve the password for the next level,stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed.


###Approach
-Created a temporary working directory using mktemp -d to safety manipulate files
-Copied data.txt into the temporary directory
-Converted the hexdump back into its original binary format using xxd -r
-Identified the file type using the file command
-Repeatedly decompressed the file based on its detected format:
    -gzip---gunzip
    -bzip2---bunzip2
    -tar-tar ---xf
-Continued this process iteratively until the final readable file was obtained
-Extracted the password using cat
-Used the password to log into the next level




###Commands used
mktemp -d
cd /tmp/tmp.YHyiB3W7na
 cp $HOME/data.txt
 xxd -r data.txt > data.bin

 file data.bin
 mv data.bin data.gz
 gunzip data.gz
 file data
 mv data.bin data.bz2
 bunzip2 data.bz2
 file data
 mv data data.gz
 gunzip data.gz
 file data
 tar -xf data
 ls
 file data5.bin
 tar -xf data5.bin
 ls
 file data6.bin
 mv data6.bin data6.bz2 
 bunzip2 data6.bz2
 ls
 file data6.bz2
 file data6
 tar -xf data6
 ls
 file data8.bin
 mv data8.bin data8.bz2
 bunzip2 data8.bz2
 mv data8.bz2 data8.gz  
 gunzip data8.gz
 ls
 file data8
 cat data8
 ssh bandit13@bandit.labs.overthewire.org -p 2220



###Key Concepts learned
-Safe file handling using temporary directories(/tmp)
-Converting hexdump to binary 
-Identifying file formats using file
-Handling multiple compression formats
