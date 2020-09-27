# rMakevars
A set of flags that are useful for getting OpenMP to work on Fortran, C and C++ for R packages on Amazon Linux AMIs

# Who is this for?
Anybody who is struggling to get R packages like `data.table`, `fst` or `vroom` to work by leveraging all processor cores present on your Linux machine, and specifically for those using AmazonLinux.

# What does this address?
This is primarily intended for use in Linux based systems that have a different version of a compiler installed that doesn't yet support OpenMP, and need to allow R packages that leverage this framework to be able to use it during compilation. You might need to do additional things (check steps on [`data.table`'s wiki](https://github.com/Rdatatable/data.table/wiki/Installation) for something specific to `data.table`) like installing or removing incompatible version of the GCC on your system, or create correct symlinks for the compiler before these flags can really work, and are outside the scope of this ReadMe.

# How can I leverage this?
Copy the text in `flags.txt` into a text file with the name `Makevars` (note the lack of extensions and the capital M) inside your home directory, inside a folder `.R` (note the dot). More information [here](https://stackoverflow.com/questions/43597632/understanding-the-contents-of-the-makevars-file-in-r-macros-variables-r-ma). Then, install any packages that leverage OpenMP and see if they leverage parallelization after loading them. If they don't, check for incompatible versions of `gcc` present on your system - StackOverflow is a good source for questions on this.

# License
It's a text file - do whatever you want with it. :)

