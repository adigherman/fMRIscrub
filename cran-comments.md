## Test environments

* Linux, R 4.0.4
* Windows 10 x64, R 4.1.1

## R CMD check results

> checking compiled code ... NOTE
  Note: information on .o files for x64 is not available
  File 'C:/Users/damon/Desktop/fMRI/fMRIscrub.Rcheck/fMRIscrub/libs/x64/fMRIscrub.dll':
    Found 'abort', possibly from 'abort' (C), 'runtime' (Fortran)
    Found 'exit', possibly from 'exit' (C), 'stop' (Fortran)
    Found 'printf', possibly from 'printf' (C)
  
  Compiled code should not call entry points which might terminate R nor
  write to stdout/stderr instead of to the console, nor use Fortran I/O
  nor system RNGs. The detected symbols are linked into the code but
  might come from libraries and not actually be called.
  
  See 'Writing portable packages' in the 'Writing R Extensions' manual.
   WARNING
  'qpdf' is needed for checks on size reduction of PDFs
  
> checking for old-style vignette sources ... NOTE
  Vignette sources only in 'inst/doc':
    'projection_scrubbing.rmd'
  A 'vignettes' directory is required as from R 3.1.0
  and these will not be indexed nor checked

0 errors v | 1 warning x | 2 notes x

--------------------------------------------------------------------------------

We indeed use a "vignettes" directory.

`abort`, `exit` and `printf` is never called by our code.

## Downstream dependencies

`templateICAr` works fine with this new version.

## Tests

Passes all the tests in `tests/testthat.R`.