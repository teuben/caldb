# CALDB

This is my attempt to keep an organized caldb database for HEASOFT.

See https://heasarc.gsfc.nasa.gov/docs/heasarc/caldb/install.html for the official

## Example

here's an example how your **.bashrc** setup could look

      export HEADAS=/n/astromake/opt/heasoft/6.34/x86_64-pc-linux-gnu-libc2.34
      source $HEADAS/headas-init.sh

      export CALDB=/n/astromake/opt/heasoft/caldb
      source $CALDB/caldbinit.sh

## HEASOFT Building Example

starting from source, and assuming all preconditions are satisfied, here's an example of a build at "astroumd"

      cd /n/astromake/opt/heasoft
      tar zxf heasoft-6.34src.tar.gz
      cd heasoft-6.34/BUILD_DIR
      
      export CC=/usr/bin/gcc
      export CXX=/usr/bin/g++
      export FC=/usr/bin/gfortran
      export PERL=/usr/bin/perl
      export PYTHON=/local/bin/python3

      ./configure --prefix=/n/astromake/opt/heasoft/6.34
      make > make.log  2>&1
      make  install

## CALDB Assembly Example

for a series of mission/instruments, as listed on,
https://heasarc.gsfc.nasa.gov/docs/heasarc/caldb/caldb_supported_missions.html,
there is a tar file to be downloaded and untarred inside of the $CALDB directory.
Maintenance of this could be better automated here via a config file which
combos you want.
