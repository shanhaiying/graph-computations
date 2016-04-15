#Good example of how to format a Wiki page.

See http://code.google.com/p/support/wiki/WikiSyntax




# Introduction #

How to test BLOPEX under Beta version of Hypre on Bluefire (IBM).  Hypre does not support complex arithematic, so this test is only for double precision arithematic.
# Setup Hypre #

Goto https://computation.llnl.gov/casc/hypre/software.html and download hypre.
For example the latest beta version of hypre is hypre-2.4.0b.tar.gz

Extract hypre files from download file.
```
be1105en$ gunzip -c hypre-2.4.0b.tar.gz | tar -xof -
```
Copy the BLOPEX modifications tar file hypre\_lobpcg\_modification.tgz to
```
be1105en$ cp hypre_lobpcg_modifications.tgz hypre-2.4.0b/src
```
Change working directory to hypre source code directory.
```
be1105en$ cd hypre-2.4.0b/src
be1105en$ pwd
/blhome/dmccuan/hypre-2.4.0b/src
```
Install the logpcg modifications.
```
be1105en$ gunzip -c hypre_lobpcg_modifications.tgz | tar -xof -
```
While in the src subdirectory and install hypre with standard setup.
Note: this will compiles the BLOPEX source.
Note: the ./nopoe is required for IBM platforms (see Hypre user's manual, Chapter 7.2).
```
be1105en$ ./nopoe ./configure
........  lots of output

be1105en$ make
........  lots of output
```

# Compile Tests #
Shift to test directory execute make to compile and link test cases.
This creates executables struct and ij.
```
be1105en$ cd test
be1105en$ pwd
/blhome/dmccuan/hypre-2.4.0b/src/test
be1105en$ make
......
Building new_ij ...
        mpcc -o new_ij new_ij.o -L/blhome/dmccuan/hypre-2.0.0/src/hypre/lib -lHYPRE -L/blhome/dmccuan/hypre-2.0.0/src/hypre/lib -lHYPRE_utilities  -L/blhome/dmccuan/hypre-2.0.0/src/hypre/lib -lHYPRE_utilities       -lm  -llapi_r -L/usr/lpp/ppe.poe/lib/threads -L/usr/lpp/ppe.poe/lib -L/lib/threads -lmpi_r -lxlf90 -L/usr/lpp/xlf/lib -lxlopt -lxlf -lxlomp_ser -lpthreads -lm    -L/usr/lib/gcc-lib/i386-redhat-linux/3.2.3 -L/usr/lib -L/usr/local/lib -L/usr/apps/lib -L/lib  -blpdata
        mpcc -O3 -qstrict -blpdata -I. -I./.. -I/blhome/dmccuan/hypre-2.0.0/src/hypre/include   -DHYPRE_TIMING -DHYPRE_FORTRAN -DHAVE_CONFIG_H -c sstruct.c 
......
Target "all" is up to date.
```
# Execution of Tests #
Bluefire must execute mpi jobs unders the Load Sharing Facility (LSF).
Jobs are submitted via command bsub.  The easiest way to do this is to setup a script as follows.
Note: You must have a project number to do this.
```
be1105en$ cat mpi_struct.lsf
#!/bin/csh
#
# LSF batch script to run an MPI application
#
#BSUB -P 37481005                   # project number
##BSUB -x                            # exlusive use of node (not_shared)
#BSUB -W 2:00                       # wall clock time (in minutes)
#BSUB -n 64                         # number of tasks
#BSUB -a poe                        # select the poe elim
##BSUB -R "span[ptile=64]"           # run 64 task per node
#BSUB -J mpi_struct                 # job name
#BSUB -o mpi_struct.%J.out          # output filename
#BSUB -e mpi_struct.%J.err          # error filename 
#BSUB -q share                      # queue

# set this env for launch as default binding
setenv TARGET_CPU_LIST "-1"
 mpirun.lsf /usr/local/bin/launch ./struct -solver 10 -n 64 64 64 -P 4 4 4 -lobpcg -pcgitr 0
```
And then execute it as follows:
```
be1105en$ bsub < mpi_struct.lsf
Job <271766> is submitted to queue <share>.
```
Jobs can be monitored via command bjobs as follows:
```
be1105en$ bjobs
JOBID   USER    STAT  QUEUE      FROM_HOST   EXEC_HOST   JOB_NAME   SUBMIT_TIME
271793  dmccuan PEND  share      be1105en                mpi_ij     Apr 28 16:13
```
Output is returned to current directory in files as defined in the script.
```
be1105en$ ls -l mpi_struct*
-rw-r--r--    1 dmccuan  univ            431 Apr 28 16:12 mpi_struct.271766.err
-rw-r--r--    1 dmccuan  univ          15929 Apr 28 16:12 mpi_struct.271766.out
-rw-r--r--    1 dmccuan  univ            776 Apr 28 16:05 mpi_struct.lsf
```

# Test Results #

The test is executed on UCAR Bluefire system in April 2009.  This is an AIX operating system and the IBM XL C/C++ compiler (xlc) and IBM version of lapack libraries are used.

## STRUCT test ##

./struct -solver 10 -n 64 64 64 -P 4 4 4 -lobpcg -pcgitr 0

The eigenvalues computed are
```
Eigenvalue lambda       Residual              
4.4827998188625719e-04  3.4605760440036511e-07
```

BLOPEX execution times
```
6 iterations
PCG Solve:
  wall clock time = 9.470000 seconds
  wall MFLOPS     = 0.000000
  cpu clock time  = 9.028213 seconds
  cpu MFLOPS      = 0.000000
```

Job execution times
```
Resource usage summary:

    CPU time   :   1323.34 sec.
    Max Memory :        29 MB
    Max Swap   :        24 MB

    Max Processes  :         6
    Max Threads    :        10
```

## IJ test ##

./ij -lobpcg -n 50 50 50 -pcgitr 0 -vrand 96 -seed 1

The first 10 eigenvalues computed are

```
Eigenvalue lambda       Residual              
1.1380027577735664e-02  4.8953248756283098e-09
2.2745665707950596e-02  5.3347793118004116e-09
2.2745665707953416e-02  4.9061578272060589e-09
2.2745665707955796e-02  5.0516150816646865e-09
3.4111303838161001e-02  3.4990279741859855e-09
3.4111303838166282e-02  1.9479807632388333e-09
3.4111303838168891e-02  3.5753876490713000e-09
4.1640485684018340e-02  7.9576179689033350e-10
4.1640485684021476e-02  8.6006747881411309e-10
4.1640485684025182e-02  8.4367991930050566e-09
4.5476941968386475e-02  2.4535743998412773e-09
5.3006123814229637e-02  6.5343884561675320e-09
5.3006123814233037e-02  4.9558820820555858e-09
5.3006123814234606e-02  9.8469808900638760e-09
```

BLOPEX execution times
```
100 iterations
LOBPCG Solve:
  wall clock time = 120.390000 seconds
  wall MFLOPS     = 0.000000
  cpu clock time  = 118.929832 seconds
  cpu MFLOPS      = 0.000000
```

Job execution times
```
Resource usage summary:

    CPU time   :   1201.16 sec.
    Max Memory :      1271 MB
    Max Swap   :      1279 MB

    Max Processes  :        16
    Max Threads    :       120
```
