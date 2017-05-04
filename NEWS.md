
# reticulate 0.8 (unreleased)

## Features

- Add `import_from_path()` function for importing Python modules from 
  the filesystem.

- Add `py_discover_config()` function to determine which versions of Python 
  will be discovered and which one will be used by reticulate.

- Add `py_function_docs()` amd `py_function_wrapper()` utility functions for 
  scaffolding R wrappers for Python functions.

- Add `py_last_error()` function for retreiving last Python error.

- Convert 0-dimension NumPy arrays (scalars) to single element R vectors 

- Convert "callable" Python objects to R functions

- Automatically add Python bin directory to system PATH for consistent
  version usage in reticulate and calls to system
  
- Added `length()` method for tuple objects

- Enable specification of `__name__` for R functions converted to
  Python functions.
  
- Give priority to the first registered delay load module (previously 
  the last registered module was given priority)
  
- Add additional safety checks to detect use of NULL xptr objects 
  (i.e. objects from a previous session). This should mean that S3
  methods no longer need to check whether they are handling an xptr.
  
- Added `py_eval()` function for evaluating simple Python statements.

- Add `local` option to `py_run_string()` and `py_run_file()`. Modify
  behavior to return local execution dictionary (rather than a reference
  to the main module).
  

## Bug Fixes

- Use `grepl()` rather than `endsWith()` for compatibility with R <= 3.2

- Use `inspect.getmro` rather than `__bases__` for enumerating the base classes
  of Python objects.

- Fix `PROTECT`/`UNPROTECT` issue detected by CRAN 

- Correct converstion of strings with Unicode characters on Windows
  
- Fix incompatibility with system-wide Python installations on Windows

- Fix issue with Python dictionary keys that shared names with  
  primitive R functions (don't check environment inheritance chain
  when looking for dictionary key objects by name).
  
  
# reticulate 0.7

- Initial CRAN release
