*2014-04-09: Georg Walther (contact@georg.io)*

This Python module was developed by Thomas Finley for GLPK <= 4.47 which was the latest version of GLPK back in 2008.
Starting around version 4.48 / 4.49, the author of GLPK deprecated method and macro names that started with lpx_.
While the author provided a header file for compatibility `glpklpx.h` initially (this header file can be found in 4.49), this header file seems to have been removed in later releases.
Another point of incompatibility between Finley's pyGLPK and more recent versions of GLPK is the, by now, deprecated definition of a C struct called `glp_long`.

In this release I added the header `glpklpx.h` and redefined `glp_long` just to pacify PyGLPK.

As of this writing, I have GLPK 4.54 installed.

With these changes I can do `import glpk` without complaints.
Further, `cobra.test.test_all()` runs without failure.

*2013-03-15: danielhyduke@gmail.com: setup.py was modified to build without compile errors on 64-bit GNU/Linux systems.*

                                 PyGLPK Readme

   *Copyright (c) 2007, 2008, Thomas W. Finley*

Overview

   PyGLPK is a Python module which encapsulates the functionality of the GNU
   Linear Programming Kit (GLPK). The GLPK allows one to specify linear
   programs (LPs) and mixed integer programs (MIPs), and to solve them with
   either simplex, interior-point, or branch-and-bound algorithms. The goal
   of PyGLPK is to give one access to all documented functionality of GLPK.

   This program is free software; you can redistribute it and/or modify it
   under the terms of the GNU General Public License as published by the Free
   Software Foundation; either version 3 of the License, or (at your option)
   any later version.

   This program is distributed in the hope that it will be useful, but
   WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY
   or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License
   for more details.

Availability

   To get the lastest version, see:
   http://tfinley.net/software/pyglpk/

Documentation

   The HTML documentation included with the release in the directory html
   contains information on building, testing, installation and documentation
   of all features of the module.

Building and Installing

   Building this module requires that the user have installed the GLPK 4.18
   or later and GMP libraries. The module builds and appears to work on my
   test files in Python 2.4, and 2.5, with GLPK 4.18 through 4.31. Earlier
   versions of Python and GLPK will not work.

   Ideally, the following will work:

     * make
     * make test
     * make install, or perhaps sudo make install

   See the HTML documentation for troubleshooting information.

Bugs and Commentary

   Please send information on issues of usage to Thomas Finley at
   tfinley@gmail.com .

     ----------------------------------------------------------------------

   Thomas Finley, 2007, 2008
