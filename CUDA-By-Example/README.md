# `CUDA-By-Example` CUDA by Example
### cf.

I also cloned in this same repository the github repository from [jiekebo](https://github.com/jiekebo) for [CUDA-By-Example](https://github.com/jiekebo/CUDA-By-Example), and this is a general observation: it may help to first search on github for the code you seek because it seems likely that someone already wrote it.

## Note on examples out of CUDA by Example

It seems that a header file `book.h` out of the `common` subdirectory is needed to run the scripts.  I've tried to write my own scripts without needing the `book.h` header.  However, it's found in jiekebo's repository and in this repository, in the subdirectory (from here) `CUDA-By-Example`.  I don't know the rationale behind `book.h` or why the authors made you need it for their examples (as I am reading the book, it's not explained (!!!)).  