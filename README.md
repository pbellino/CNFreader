
CNFreader
=========

Script for reading a Canberra Nuclear File (CNF) form GENIE2000 software.

It can be used as a stand alone script or as a module.

Optionally, it generates a text file with the relevant information read from the CNF file. The output file name is the input file plus '.txt' extension.

When used as a module, it returns a dictionary with all the magnitudes read. Depending on the data available, its keys may be:
       
        Sample id
        Channels
        Sample unit
        Sample name
        Channels data
        Energy unit
        Energy coefficients
        Shape coefficients
        Left marker
        Total counts
        Number of channels
        Start time
        Counts in markers
        Right marker
        Sample type
        Sample description
        User name
        Live time
        Energy
        Real time
        Measurement mode
        MCA type
        Data source

Files
-----

  * `read_cnf.py`: CNFreader python scrip.
  * `README.md`: This file
  * `cnf_file_format.txt`: CNF binary file description. Taken from [cnfconv](https://github.com/messlinger/cnfconv).
  * `./Examples/` : Folder with examples files
    - `example_mcs.CNF`: Data file aquired with a multichannel analyzer in MCS mode.
    - `example_pha.CNF`: Data file aquiered with a multichannel analyzer in PHA mode.
    - `cs137.CNF`: Exxample file of a $^{137}$Cs gamma spectrum (PHA mode).

    

Examples
--------

As a standalone script:

```
    >>> python read_cnf.py name_of_the_file.CNF
```
    ('name_of_the_file.CNF.txt' is automatically created)

As a module:

```
    >>> from read_cnf import read_cnf_file
    >>> read_dic = read_cnf_file('name_of_the_file.CNF')
    >>> read_dic['Live time']
```

References
----------

This script was made as a copy of the c program 'cnfconv' written for the same porpouse. That software can be found here: 

[cnfconv](https://github.com/messlinger/cnfconv)

All the information of the binary file encoding was taken from the file 'cnf_file_format.txt' of the above repository.

TODO
----

  * Markers information is not being read correctly.
  * If the CNF file are obtained in a MCA mode, the live and real time are not read correctly.
  * Additional data must be read in case of a file from MCA mode (mainly dwell time).


