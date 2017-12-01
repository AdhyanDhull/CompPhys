# Cpp - C++ code and examples; C++ code and examples for Computational Physics and Computational Fluid Dynamics (CFD)


## Abstract

This directory has C++ code examples that helps me (i.e. "developer tools") for the applications I'm interested in: Computational Physics, Computational Fluid Dynamics.  

(20160713) I'm reading and going through 

**C++ Primer** (5th Edition) 5th Edition, by Stanley B. Lippman, Josée Lajoie, Barbara E. Moo.

Those scripts related to that is in the subdirectory `/CompPhys/Cpp/primer`, and the `README.md` there has (an incomplete) dictionary between script and reading.  

Included in this repository (repo) are code examples straight from M. Hjorth-Jensen's **Computational Physics**, University of Oslo (2015) [mhjensen](http://www.mn.uio.no/fysikk/english/people/aca/mhjensen/).  

Hjorth-Jensen's material motivated me to (try to) dive deeper into C++ and so I picked up Bjarne Stroustrup's **A Tour of C++** (Addison-Wesley Professional, 2013).  This book is based on **C++11** and I suspect that a lot of computational physics code was written *before* this 2011 (keep in mind that I still need to find a good book for C++14).  I include code for Stroustrup's **A Tour of C++** in the `./tour` subdirectory.  

> C++ feels like a new language. That is, I can express my ideas more clearly, more simply, and
more directly in C++11 than I could in C++98.  Furthermore, the resulting programs are better
checked by the compiler and run faster. -*Bjarne Stroustrup*

You're (as I was) reading Hjorth-Jensen's excellent lecture notes (latest I found is from 2015) on Computational Physics (with an emphasis on C++).  You want to run the C++ code *simultaneously* as you are reading, as I found that I learn *much* faster watching how the code works than a book explanation - along with playing around with the code "in real-time" (it makes learning fun!).  But you don't know which code follows along which part of the lectures.  So I'll try to make a listing (a dictionary) or index of code to lecture, below.  

P.S. There are some non-trivial typos both in the code and lecture that made the material confusing to understand (as in, did he really mean that?) and some things weren't obvious to me when I read it, and so I try to make sense of it in my notes in [CompPhys.pdf](https://github.com/ernestyalumni/CompPhys/blob/master/LaTeXandpdfs/CompPhys.pdf) and have my own code type-ups here in this repository, even though there's the [CompPhys repository](https://github.com/CompPhysics).

## Table of Contents  
Be aware that this Table of Contents maybe incomplete (one way around this is to search for key words with some kind of search function).  

- Modularity
- File I/O in C and C++
- **stack** vs. **heap**
- `hdf5` - C, C++, Python, saving files, File I/O from Python hdf5 to C++
- **[Design Patterns](https://github.com/ernestyalumni/CompPhys/tree/master/Cpp/DesignPatterns)**

## Listing of which program or script corresponds to which section, chapter, part for Hjorth-Jensen's material

See Hjorth-Jensen's lectures for 2015.  

| codename        | directory      | Chapter | Section | page (pp) | Description            |
| --------------- | -------------- | :-----: | ------- | --------- | ---------------------- |
| argcargv.cpp    | ./             |         |         |           | This is my own pedagogical example of using argc, argv in C++; it's also a good example of looping through an array as a pointer |
| program1.cpp    | ./progs/ch02/  | 2       | 2.1.1   | 10        | Scientific Hello World!|
| program7.cpp    | ./progs/ch02/  | 2       | 2.5.2   | 34        | Pointers and arrays in C++ |
| program7b.cpp   | ./progs/ch02/  | 2       | 2.5.2   | 34        | Pointers and arrays in C++ (further experimentation by me) |
| program1.cpp    | ./progs/ch03/  | 3       | 3.1.1.1 | 51        | calculates second derivative of exp(x); take note of C style file IO |
| program3.cpp    | ./progs/ch03/  | 3       | 3.1.1.4 | 54        | calculates second derivative of exp(x); take note of C++ style file IO |
| usecomplex.cpp  | ./progs/ch03/  | 3       | 3.3.1   | 68        | Using standard template library (STL) for <complex>, complex<double>  |
| usecomplexb.cpp | ./progs/ch03/  | 3       | 3.3.1   | 68        | More usage, such as x.real(), x.imag(), and exp(z) by me |
| complex.h       | ./progs/ch03/  | 3       | 3.3.1   | 67        | header file for Complex class |
| complex.cpp     | ./progs/ch03/  | 3       | 3.3.1   | 68        | contains Complex class |
| customCC.cpp    | ./progs/ch03/  | 3       | 3.3.1   | 68        | contains `main()` to demonstrate Complex class |
| Integrate.ipynb | ./             | 5       | 5.1     | 109-112   | jupyter (.ipynb) notebook to symbolic compute, using sympy, the derivation of trapezoid rule |
| program1.cpp    | ./progs/ch05/  | 5       | 5.3.6   | 127       | example using trapezoid rule, Simpson's rule, Gauss-Legendre method|
| integrate1d.h   | ./progs/ch05/  | 5       | 5.3.6   | 127       | header file for 1-dimensional numerical integration routines, only |
| integrate1d.cpp | ./progs/ch05/  | 5       | 5.3.6   | 127       | function definitions for 1-dimensional numerical integration routines, only |
| diffusion1dexplicit.cpp | ./progs/ch10pde/ | 10 | 10.2.1 | 307   | 1-dim. diffusion eq. solved with *"explicit method"*; while Hjorth-Jensen explained at lengths about transforming the problem into a matrix multipying a vector problem, in his pseudocode, there's no matrix multiplication!  Here it is, using `gsl`  |
| diffusion1dimplicit.cpp | ./progs/ch10pde/ | 10 | 10.2.2 | 309   | Full C++ implementation of 1-dim. diffusion eq. using *backward Euler* for time-evolution or *implicit scheme*.  cf. [14.17 Tridiagonal Systems](https://www.gnu.org/software/gsl/manual/html_node/Tridiagonal-Systems.html) has a great, clear, explicit explanation of the tridiagonal matrix solvers using `gsl` |
| diffusion1dCrankNicolson.cpp | ./progs/ch10pde/ | 10 | 10.2.3 |  | C++ implementation with gsl library (for linear algebra) of *Crank-Nicolson* method; see my CompPhys.pdf notes for an explanation, because I improve on the exposition from Hjorth-Jensen (2015) |
| LaplaceEqJacobi.cpp | ./progs/ch10pde/ | 10 | 10.3.2 | 319       | *Jacobi method* for solving the *Laplace equation* or *Poisson equation* in 2-dims., see also [3.1 Poisson's Equation and Relaxation Methods](http://www.physics.buffalo.edu/phy410-505/2011/topic3/app1/index.html) of 410-505 Physics for a clear explanation and my notes CompPhys.pdf.  In particular, it solves Example 4.5 of Cebeci, Shao, Kafyeke, Laurendeau's **Computational Fluid Dynamics for Engineers** (2005)  | 
| diffusion2dim.cpp | ./progs/ch10pde/ | 10   |         |          | Solves 2-dim. diffusion equation or Poisson equation using Jacobi's iterative method, but this version uses **`gsl`** Scientific library (C/C++) for linear algebra.  cf. [`diffusion2dim.cpp` from `CompPhysics`](https://github.com/CompPhysics/ComputationalPhysics/blob/master/doc/Programs/LecturePrograms/programs/PDE/cpp/diffusion2dim.cpp)  |


## Listing of which program or script corresponds to which section, chapter, part for Stroustrup's **A Tour of C++** (2013)

| codename        | directory      | Chapter      | Section           | page (pp) | Description            |
| --------------- | -------------- | :----------: | ----------------- | --------- | ---------------------- |
| helloworld.cpp    | ./tour         | 1 The Basics | 1.3 Hello, World! | 2         | Hello, World! and standard-library namespace std::cout |
| typesvararith.cpp | ./tour         | 1 The Basics | 1.5 Types, Variables, and Arithmetic | 5 | notice initialization by double d2 {2.3}; |
| const.cpp         | ./tour         | 1 The Basics | 1.7 Tests         | 8        | notice `constexpr` for compile-time evaluated constants |
| test.cpp          | ./tour         | 1 The Basics | 1.9 Tests         | 12        | switch tests in C++11 |
| structcls.cpp     | ./tour         | 2 Used-Defined Types | 2.2 Structures; 2.3 Classes | 16-18  | structs; notice how member initializer list is a C++11 feature for the class constructor |
...

20160629 I continue this incomplete listing in the [README.md](https://github.com/ernestyalumni/CompPhys/blob/master/Cpp/tour/README.md) of the [tour subdirectory](https://github.com/ernestyalumni/CompPhys/tree/master/Cpp/tour) - go there for the entire list.  


- `hdf5` - working with it between C, C++, Python 

| codename        | directory      |  Description            | Compilation tip |
| :-------------- | :------------: | ----------------------- | :-------------- |
| `h5_crtdat.c` | `./hd5/` | Create a dataset, cf. [HDF5 Introductory Examples](https://support.hdfgroup.org/HDF5/examples/intro.html) | `gcc h5_crtdat.c -lhdf5 -o h5_crtdat.exe` |   
| `h5tutr_crtdat.cpp`    | ./hdf5/         | Create a dataset, cf. [HDF5 Introductory Examples](https://support.hdfgroup.org/HDF5/examples/intro.html)  | `g++ -std=c++14 h5tutr_crtdat.cpp -o h5tutr_crtdat.exe -lhdf5_cpp` |   
| `h5_rdwt.c` | `./hd5/` | Read and write to a dataset, cf. [HDF5 Introductory Examples](https://support.hdfgroup.org/HDF5/examples/intro.html)  | `gcc h5_rdwt.c -lhdf5 -o h5_rdwt.exe` |
| `h5tutr_rdwt.cpp` | `./hd5/` | Read and write to a dataset, cf. [HDF5 Introductory Examples](https://support.hdfgroup.org/HDF5/examples/intro.html) | `g++ -std=c++14 h5tutr_rdwt.cpp -o h5tutr_rdwt.exe -lhdf5_cpp -lhdf5` |   






...


### Compiling C++11
This worked for me, as I had obtained a c++11 compiling error when I trued to use `for (char ch: act) { ... }`:

```
g++ -std=c++11 test.cpp
```

## File I/O in C and C++

### Quick and Dirty File I/O for C++

I find myself having to write out results into `.csv` text files to see what my C++ program is doing.  

Here's the raw C++ code I have in (draft) github repository `Propulsion/CUDACFD/NavierStokes/commonlib/sharedmem.cu`:

```  
// test print outs, file IO out
	std::ofstream ofile1;
	ofile1.open("testfx_sin1.csv");
	ofile1 << testfx[ testgrid3d.flatten( 0, testgrid3d.N_is[1]/2, testgrid3d.N_is[2]/2) ] ; 
	
	for (int i = 1; i < ( testgrid3d.N_is[0] ); ++i) {
		ofile1 << ", " << testfx[ testgrid3d.flatten( i, testgrid3d.N_is[1]/2, testgrid3d.N_is[2]/2) ];
	}
	ofile1 << std::endl;
	
	ofile1 << testfx[ testgrid3d.flatten( 0, 0, 0) ] ; 
	for (int i = 1; i < ( testgrid3d.N_is[0] ); ++i) {
		ofile1 << ", " << testfx[ testgrid3d.flatten( i, 0, 0 ) ];
	}
	ofile1 << std::endl;

	ofile1 << testfx[ testgrid3d.flatten( 0, testgrid3d.N_is[1]*3/4, testgrid3d.N_is[2]*3/4) ] ; 
	for (int i = 1; i < ( testgrid3d.N_is[0] ); ++i) {
		ofile1 << ", " << testfx[ testgrid3d.flatten( i, testgrid3d.N_is[1]*3/4, testgrid3d.N_is[2]*3/4)  ];
	}
	ofile1 << std::endl;

	ofile1.close();
	
	std::ofstream ofile2;
	ofile2.open("testdfx_cos1.csv");
	
	ofile2 << testdfx[ testgrid3d.flatten( 0, testgrid3d.N_is[1]/2, testgrid3d.N_is[2]/2) ] ; 
	
	for (int i = 1; i < ( testgrid3d.N_is[0] ); ++i) {
		ofile2 << ", " << testdfx[ testgrid3d.flatten( i, testgrid3d.N_is[1]/2, testgrid3d.N_is[2]/2) ];
	}
	ofile2 << std::endl;
	
	ofile2 << testdfx[ testgrid3d.flatten( 0, 0, 0) ] ; 
	for (int i = 1; i < ( testgrid3d.N_is[0] ); ++i) {
		ofile2 << ", " << testdfx[ testgrid3d.flatten( i, 0, 0 ) ];
	}
	ofile2 << std::endl;

	ofile2 << testdfx[ testgrid3d.flatten( 0, testgrid3d.N_is[1]*3/4, testgrid3d.N_is[2]*3/4) ] ; 
	for (int i = 1; i < ( testgrid3d.N_is[0] ); ++i) {
		ofile2 << ", " << testdfx[ testgrid3d.flatten( i, testgrid3d.N_is[1]*3/4, testgrid3d.N_is[2]*3/4)  ];
	}
	ofile2 << std::endl;

	ofile2.close();

	std::ofstream ofile3;
	ofile3.open("dev_testdfx_sin1.csv");
	
	ofile3 << testdfx_res[ testgrid3d.flatten( 0, testgrid3d.N_is[1]/2, testgrid3d.N_is[2]/2) ] ; 
	
	for (int i = 1; i < ( testgrid3d.N_is[0] ); ++i) {
		ofile3 << ", " << testdfx_res[ testgrid3d.flatten( i, testgrid3d.N_is[1]/2, testgrid3d.N_is[2]/2) ];
	}
	ofile3 << std::endl;
	
	ofile3 << testdfx_res[ testgrid3d.flatten( 0, 0, 0) ] ; 
	for (int i = 1; i < ( testgrid3d.N_is[0] ); ++i) {
		ofile3 << ", " << testdfx_res[ testgrid3d.flatten( i, 0, 0 ) ];
	}
	ofile3 << std::endl;

	ofile3 << testdfx_res[ testgrid3d.flatten( 0, testgrid3d.N_is[1]*3/4, testgrid3d.N_is[2]*3/4) ] ; 
	for (int i = 1; i < ( testgrid3d.N_is[0] ); ++i) {
		ofile3 << ", " << testdfx_res[ testgrid3d.flatten( i, testgrid3d.N_is[1]*3/4, testgrid3d.N_is[2]*3/4)  ];
	}
	ofile3 << std::endl;

	ofile3.close();
```  

Let's generalize this (as this is my template).  Let `testfx, testdfx, testdfx_res` be 1-dimensional arrays.  The indexing was handled by `testgrid3d.flatten`, a (I defined) class member function.  But I can have a simple indexing and looping through that index e.g. `for (int i =0; i< Lengthofmy1dimarray; ++i) { testfx[i]; // and so on }`.  

You'd have to use the `<<` C++ "operator" to input into your ofile, an "instance" of `std::ofstream` each string.  

**See also**, for an *example of usage* [Writing .csv files from C++](http://stackoverflow.com/questions/25201131/writing-csv-files-from-c), in particular, this answer from [BHawk](http://stackoverflow.com/users/4434679/bhawk):
```  
#include <iostream>
#include <fstream>
int main( int argc, char* argv[] )
{
      ofstream myfile;
      myfile.open ("example.csv");
      myfile << "This is the first cell in the first column.\n";
      myfile << "a,b,c,\n";
      myfile << "c,s,v,\n";
      myfile << "1,2,3.456\n";
      myfile << "semi;colon";
      myfile.close();
      return 0;
}
```  
This is what I implemented and adopted here in [`../moreCUDA/samples02/sinsin2dtex.cu`](https://github.com/ernestyalumni/CompPhys/blob/master/moreCUDA/samples02/sinsin2dtex.cu).  


cf. `program1.cpp` in `./progs/ch03` subdirectory; pp. 51 Subsection 3.1.1.1 Initializations and main program, Ch. 3 Numerical differentiation and interpolation of Hjorth-Jensen (2015); [CompPhysics/ComputationalPhysicsMSU/doc/Programs/LecturePrograms/programs/Classes/cpp/
](https://github.com/CompPhysics/ComputationalPhysicsMSU/blob/master/doc/Programs/LecturePrograms/programs/Classes/cpp/program1.cpp)

Take a look at `program1.cpp`.  It appears that the "C"-style file IO is first considered.  Reading this wikipedia article on [C file input/output](https://en.wikipedia.org/wiki/C_file_input/output) helped me understand what was used here.

`FILE` - known as a file *handle*, abstract reference to a resource, this is an "opaque type" - points to some unspecified type - containing information about a file or text stream, and we can do IO (input output) operations on.

So `FILE *output_file;` declares a pointer `output_file` to a `FILE`. 

`stdio.h` contains `fopen`, `fprintf`, `fclose`:
- `fopen` - opens a file
- `fprintf` - prints formatted byte/wchar_t output to stdout, file stream, or buffer; syntax:

```
int fprintf_s(FILE *restrict stream, const char *restrict format, ...);
```
cf. http://en.cppreference.com/w/c/io/fprintf

[`main.cpp` of `dd_1d_global`](https://github.com/ernestyalumni/CompPhys/blob/master/moreCUDA/cudaforengineers/dd_1d_global/main.cpp), and [`main.cpp` of `dd_1d_shared`](https://github.com/ernestyalumni/CompPhys/tree/master/moreCUDA/cudaforengineers/dd_1d_shared), in the `moreCUDA/cudaforengineers/dd_1d_global` and `moreCUDA/cudaforengineers/dd_1d_shared` directories, respectively, of this same repository (CompPhys) demonstrate the use of `fprintf`, and then taking that generated `.csv` file, using Python's `matplotlib` on a `jupyter` notebook for "data visualization" (plotting).  

- `fclose` - closes a file

cf. `program3.cpp` in `./progs/ch03` subdirectory, pp. 54-55, Subsection 3.1.1.4 The output function of Hjorth-Jensen (2015), [CompPhysics/ComputationalPhysicsMSU/doc/Programs/LecturePrograms/programs/Classes/cpp/
](https://github.com/CompPhysics/ComputationalPhysicsMSU/blob/master/doc/Programs/LecturePrograms/programs/Classes/cpp/program3.cpp)

#### `<fstream>` header

cf. http://www.cplusplus.com/reference/fstream/

`<fstream>` in `#include <fstream>` is a header providing file stream classes.  So apparently, for narrow characters [`char`], there is `fstream` (input/output file stream class) and `ofstream` (output file stream).

In `program3.cpp`, `ofile` is an "instance" of class `ofstream`:

```
ofstream ofile;
```
Here are examples of using this class `ofstream` (in this particular situation, its "instance" is called `ofile`):

```
ofile.open(outfilename);
ofile.close();
```
and then the actual "outputting":

```
ofile << setw(15) << setprecision(8) << log10(h_step[i]);
ofile << setw(15) << setprecision(8) << epsilon << endl;
```

`setw` is a class belonging to `<iomanip>`.  It stands for **Set field width** and sets the *field width* to be used on output operations (cf. http://www.cplusplus.com/reference/iomanip/setw/ ).  

#### `.csv` file output of an array for C++

[Export data from an array to a csv file](http://www.cplusplus.com/forum/general/170845/)

From [Duoas](http://www.cplusplus.com/user/Duoas/) answer,

> Don't forget to put something (like a comma) between outputs. This takes a little thinking, 
> because you want to see:
```
    1,2,3,4
```
> and not:
```
    1,2,3,4,
```

Fortunately, that's a pretty simple fix:

```  
// for each row
for (i=0; ...)
{
  // print first column's element
  outfile << arr[i][0];

  // print remaining columns
  for (j=1; ...)
  {
    outfile << ", " << arr[i][j];
  }

  // print newline between rows
  outfile << endl;
}
```  
#### Examples of Usage

As mentioned before, examples of good usage, in particular of `fprintf`, are [`main.cpp` of `dd_1d_global`](https://github.com/ernestyalumni/CompPhys/blob/master/moreCUDA/cudaforengineers/dd_1d_global/main.cpp), and [`main.cpp` of `dd_1d_shared`](https://github.com/ernestyalumni/CompPhys/tree/master/moreCUDA/cudaforengineers/dd_1d_shared), in the `moreCUDA/cudaforengineers/dd_1d_global` and `moreCUDA/cudaforengineers/dd_1d_shared` directories, respectively, of this same repository (CompPhys), demonstrating the use of `fprintf`, and then taking that generated `.csv` file, using Python's `matplotlib` on a `jupyter` notebook for "data visualization" (plotting).  




## Classes (C++)

See `complex.h, complex.cpp, customCC.cpp` in `./progs/ch03` subdirectory for useful (pedagogical) examples.

### header files

Define header file (e.g. complex.h) which contains declarations of the class.
The header file contains
- class declaration (data and functions)
- declaration of stand-alone functions, and all inlined functions,

To understand

```
#ifndef HEADERFILE_H  
#define HEADERFILE_H  
```

See (http://stackoverflow.com/questions/1653958/why-are-ifndef-and-define-used-in-c-header-files) and (https://en.wikipedia.org/wiki/Include_guard).

### Modularity

Stroustrup makes a chapter on *Modularity.*  Here's what I found in practice.  

I wanted to test out a new class which I want to put in a header file, with its class definition split away in another `.cpp` file.  This is because the header file is the "interface" and the definition is separated.

Then I wanted to have a test `main` function in a directory "above."  Next, I wanted to compile it to test it out.  In the command prompt, you'd do something like this:

```  
g++ -std=c++14 testR3grid.cpp ./physlib/R3grid.cpp ./physlib/R3grid.h  
```

i.e. you're going to have to include all the files in that command line for `g++`.  

### Useful links related to splitting up header files for declaration, split to `.cpp` files for definitions

- [ C++ Class Example | Separate header and implementation file from DeepakSingh in the wrox forums](http://p2p.wrox.com/c-programming/92954-c-class-example-separate-header-implementation-file.html)

- [Declaring struct in header C++](http://stackoverflow.com/questions/25179244/declaring-struct-in-header-c)

- [How to define a template class in a .h file and implement it in a .cpp file from `codeproject.com`](http://www.codeproject.com/Articles/48575/How-to-define-a-template-class-in-a-h-file-and-imp)

- [What should and what shouldn't be in a header file? [closed]](http://programmers.stackexchange.com/questions/167723/what-should-and-what-shouldnt-be-in-a-header-file) Wow, some people can get angry and indignant about coding practices on the Internet/stackexchange.  This could all be out-dated due to C++14 standards.  

- [Why can templates only be implemented in the header file?](http://stackoverflow.com/questions/495021/why-can-templates-only-be-implemented-in-the-header-file)

#### 

[33.2 How do I pass a pointer-to-member-function to a signal handler, X event callback, system call that starts a thread/task, etc?](http://yosefk.com/c++fqa/function.html#fqa-33.2)

>  FAQ: You don't. A member function can't be used without an object of the class, so the whole thing can't work. What you can do is write a non-member function wrapping your pointer-to-member-function call.

> For example, thread creation callbacks usually have a void* argument. You could pass an object pointer in that argument to the callback (which has to be a non-member). The callback would then cast the void* down to the actual type and call the object's method.

> Some functions, like signal, use callbacks without a void* argument or anything similar. In that case, you have no choice but save a pointer to the object in a global variable. The callback can get the object pointer from that global variable and call the method.

> static member functions can be used in the contexts where a C callback is expected, if they are extern "C". Although on most compilers it would probably work without extern "C", the standard says it doesn't have to work. 

This also answers 33.3 Why do I keep getting compile errors (type mismatch) when I try to use a member function as an interrupt service routine?

So a member function of a class can't be used without an object (in my case, an "instantiation") of the class, so the function can't be an argument, or passed by value or passed by reference, to another (outside) function.

## **stack** vs. **heap**  

cf. [Segmentation fault on large array sizes](https://stackoverflow.com/questions/1847789/segmentation-fault-on-large-array-sizes)  

```   
int main()
{
   int c[1000000];
   cout << "done\n";
   return 0;
}
```  
results in a stack overflow.  Array is too big to fit in a program's stack address space (for example).

If you allocate the array on the *heap*, it should be fine, assuming the machine has enough memory.   
```  
int* array = new int[1000000];
```

But remember that this will require you to `delete[]` the array. A better solution would be to use `std::vector<int>` and resize it to 1000000 elements.

"Thanks for the answer, but could you explain me why arrays are allocated on the stack and why not in the main program memory." – [Mayank](https://stackoverflow.com/users/224863/mayank) Dec 4 '09 at 15:51  

"The given code allocates on the stack because it's specified as an array with a constant number of elements at compile time. Values are only put on the heap with `malloc, new,` etc." – [Seth Johnson](https://stackoverflow.com/users/118160/seth-johnson) Dec 4 '09 at 16:05 

[Proper stack and heap usage in C++?](https://stackoverflow.com/questions/599308/proper-stack-and-heap-usage-in-c)

 221
down vote
accepted
	

No, the difference between stack and heap isn't performance. It's lifespan: any local variable inside a function (anything you do not malloc() or new) lives on the stack. It goes away when you return from the function. If you want something to live longer than the function that declared it, you must allocate it on the heap.

```   
class Thingy;

Thingy* foo( ) 
{
  int a; // this int lives on the stack
  Thingy B; // this thingy lives on the stack and will be deleted when we return from foo
  Thingy *pointerToB = &B; // this points to an address on the stack
  Thingy *pointerToC = new Thingy(); // this makes a Thingy on the heap.
                                     // pointerToC contains its address.

  // this is safe: C lives on the heap and outlives foo().
  // Whoever you pass this to must remember to delete it!
  return pointerToC;

  // this is NOT SAFE: B lives on the stack and will be deleted when foo() returns. 
  // whoever uses this returned pointer will probably cause a crash!
  return pointerToB;
}
```  

For a clearer understanding of what the stack is, come at it from the other end -- rather than try to understand what the stack does in terms of a high level language, look up "call stack" and "calling convention" and see what the machine really does when you call a function. Computer memory is just a series of addresses; "heap" and "stack" are inventions of the compiler.  [Crashworks](https://stackoverflow.com/users/53543/crashworks).





## Makefiles

### Useful links

- [so-called "official" GNU manual for GNU make](https://www.gnu.org/software/make/manual/make.html#Overview)

- [Using make and writing Makefiles from cs.swarthmore.edu](https://www.cs.swarthmore.edu/~newhall/unixhelp/howto_makefiles.html)  

- From [isaacs's makefile basics](https://gist.github.com/isaacs/62a2d1825d04437c6f08): 
[isaacs's excellent "glossary" explanation of Makefiles](https://gist.github.com/isaacs/62a2d1825d04437c6f08)

### Makefiles, quick and dirty, or my experience so far

First thing that I had to learn first was from 2.4 Variables Make Makefiles Simpler of the GNU make "manual."

Define variables by `=` sign and then, for each place we want to put the variable, e.g. `CPP = g++ -std=c++14` substitute in the variable's value by writing `$(CPP)`.  See [How to Use Variables](https://www.gnu.org/software/make/manual/make.html#Using-Variables).  Apparently, in 6.1 Basics of Variable References, `$(CPP)` and `${CPP}` are the same thing - parentheses or braces can be used (they do the same thing apparently (!!!)).

#### Glossary (for Makefiles)

From [isaac](https://gist.github.com/isaacs/62a2d1825d04437c6f08)
- `$@` The file that is being made right now by this rule (aka the "target").  You can remember this because it's like the `$@` list in a shell script  
- `$<`  The input file (that is, the first prerequisite in the list).  You can remember this because the `<` is like a file input pipe in bash.  
- `$^`  This is the list of ALL input files, not just the first one.  You can remember it because it's like `$<`, but turned up a notch.  If a file shows up more than once in the input list for some reason, it's still only going to show one time in `$^`.

At this point, knowing what some "commonly used" `g++` compiler flags mean would help.  

From [die.net `g++(1)` - Linux man page](http://linux.die.net/man/1/g++)

- `-c` -- Compile or assemble the source files, but do not link. The linking stage simply is not done. The ultimate output is in the form of an object file for each source file.  
By default, the object file name for a source file is made by replacing the suffix `.c, .i, .s`, etc., with `.o`.
- `-o` *file* -- Place output in file file. This applies regardless to whatever sort of output is being produced, whether it be an executable file, an object `f`.   

## C++11, C++14 `std::array` and Multidimensional `std::array`

From [stackexchange, "Multidimensional std::array"](http://stackoverflow.com/questions/17759757/multidimensional-stdarray)

[billz's answer](http://stackoverflow.com/users/951757/billz):

> You need extra brackets, until c++14 proposal kicks in.
```  
 std::array<std::array<int, 3>, 3> arr = {{{5, 8, 2}, {8, 3, 1}, {5, 3, 9}}};  
```  






## C++ Operator Overloading in expression; lvalues vs. rvalues

cf. [C++ Operator Overloading in expression](http://stackoverflow.com/questions/6377786/c-operator-overloading-in-expression)

Take a look at this link: [C++ Operator Overloading in expression](http://stackoverflow.com/questions/6377786/c-operator-overloading-in-expression).  This point isn't emphasized enough, as in Hjorth-Jensen (2015).  This makes doing something like  

```
d = a*c + d/b
```

work the way we expect.  Kudos to user [fredoverflow](http://stackoverflow.com/users/252000/fredoverflow) for his answer:

``The expression `(e_x*u_c)` is a rvalue, and references to non-const won't bind to rvalues.

Also, member functions should be marked `const` as well.''  

### What are lvalues and rvalues in C and C++?

[C++ Rvalue References Explained](http://thbecker.net/articles/rvalue_references/section_01.html)

Original definition of *lvalues* and *rvalues* from *C*:  
*lvalue* - expression `e` that may appear on the left or on the right hand side of an assignment  
*rvalue* - expression that can only appear on right hand side of assignment =.

Examples:

```
  int a = 42;
  int b = 43;

  // a and b are both l-values
  a = b; // ok
  b = a; // ok
  a = a * b; // ok

  // a * b is an rvalue:
  int c = a * b; // ok, rvalue on right hand side of assignment
  a * b = 42; // error, rvalue on left hand side of assignment
  
```

In *C++*, this is still useful as a first, intuitive approach, but   
*lvalue* - expression that refers to a memory location and allows us to take the address of that memory location via the & operator.  
*rvalue* - expression that's not a lvalue

So & reference *functor* can't act on rvalue's.

### Results of Numerical Integration

See the lecture notes (2015) of Hjorth-Jensen; pp. 128, Ch. 5 Numerical Integration, Tables 5.2-5.3.  I wanted to reproduce those results.

My thought is that making a "smaller" file containing only the 1-dimensional (numerical) integration routines would be more useful (pedagogically).  Hence, including `integrate1d.h` header file in the working directory, you'd compile

```
g++ program1.cpp integrate1d.cpp
```

i.e. compile `program1.cpp` with `integrate1d.cpp` and then one can integrate your desired integrand, by including those "integrate1d" files.

My results are as follows:

For $\int_1^{100} \exp{(-x)/x \, dx$,

| N        | Trapezoid     | Simpson  | Rectangular | Gauss-Legendre |
| -------- | ------------- | :------: | ----------  | -------------- |
| 10       | 1.82102       | 0.607023 | 0.00433585  | 0.146045       |
| 20       | 0.912678      | 0.306397 | 0.0442333   | 0.217809       |
| 40       | 0.478456      | 0.181965 | 0.123049    | 0.219383       |
| 100      | 0.273724      | 0.170579 | 0.194204    | 0.219384       |
| 1000     | 0.219984      | 0.213317 | 0.219084    | 0.219384       |

For $\int_0^3 1/(2+x^2) \, dx$,

| N        | Trapezoid     | Simpson  | Rectangular | Gauss-Legendre |
| -------- | ------------- | :------: | ----------  | -------------- |
| 10       | 0.798861      | 0.769685 | 0.824581    | 0.799233       |
| 20       | 0.79914       | 0.78446  | 0.812373    | 0.799233       |
| 40       | 0.799209      | 0.791846 | 0.805925    | 0.799233       |
| 100      | 0.799229      | 0.796278 | 0.80194     | 0.799233       |
| 1000     | 0.799233      | 0.798937 | 0.799505    | 0.799233       |


# `hdf5` - C, C++, Python, saving files, File I/O from Python hdf5 to C++

## Compilation tips for `hdf5`

First I checked if hd5 was installed at all on Fedora Linux:   
```     
  dnf list hdf5*   
```  

I checked that   
```
	hdf5.x86_86    
	hdf5-devel.x86_64
```   	

were installed.  (I'm on `x86_64`)

Then I did
```
	h5c++ -show h5tutr_crtdat.cpp
```   	
to show what libraries to include.   
`h5c++ -show h5tutr_crtdat.cpp -showconfig` has interesting, explicit data of the configuration and library flags used.   

`h5c++` is a helper application. cf. [Problems building C++ getters #3](https://github.com/tbertinmahieux/MSongsDB/issues/3)

**Bottom line, (short) answer**:
```
g++ -std=c++14 h5tutr_crtdat.cpp -o h5tutr_crtdat.exe -lhdf5_cpp -lhdf5   
```   

For `C` files, all this was needed:
```
gcc h5_crtdat.c -lhdf5 -o h5_crtdat.exe
```


*Notice how I placed those `-lx`, e.g. `-lhdf5` flags afterwards, after the file to be compiled.*  This is because of cf. [Strange linking error: DSO missing from command line](http://stackoverflow.com/questions/19901934/strange-linking-error-dso-missing-from-command-line) - "Explanation: the linking is dependent on the order of modules. Symbols are first requested, and then linked in from a library that has them. So you have to specify modules that use libraries first, and libraries after them. Like this:"  

### HDF5 Libraries   
   
```   
    libhdf5_hl_cpp.a    - HDF5 High Level C++ APIs    
    libhdf5_cpp.a       - HDF5 C++ Library    
    libhdf5hl_fortran.a - HDF5 High Level Fortran APIs    
    libhdf5_fortran.a   - HDF5 Fortran Library    
    libhdf5_hl.a        - HDF5 High Level C APIs    
    libhdf5.a           - HDF5 C Library    
```   

### Error messages obtained from compilation, compiling, when I didn't include the correct library flags

If you did
```
g++ -std=c++14 h5tutr_crtdat.cpp -o h5tutr_crtdat.exe
```    
or `g++ -std=c++14 h5tutr_crtdat.cpp -o h5tutr_crtdat.exe -lhdf5`.  

```
/tmp/ccsk3JGD.o: In function `main':
h5tutr_crtdat.cpp:(.text+0xf): undefined reference to `H5::Exception::dontPrint()'
h5tutr_crtdat.cpp:(.text+0x23): undefined reference to `H5check_version'
h5tutr_crtdat.cpp:(.text+0x2d): undefined reference to `H5::FileAccPropList::DEFAULT'
h5tutr_crtdat.cpp:(.text+0x32): undefined reference to `H5::FileCreatPropList::DEFAULT'
h5tutr_crtdat.cpp:(.text+0x44): undefined reference to `H5::H5File::H5File(std::__cxx11::basic_string<char, std::char_traits<char>, std::allocator<char> > const&, unsigned int, H5::FileCreatPropList const&, H5::FileAccPropList const&)'
h5tutr_crtdat.cpp:(.text+0x6e): undefined reference to `H5::DataSpace::DataSpace(int, unsigned long long const*, unsigned long long const*)'
h5tutr_crtdat.cpp:(.text+0x84): undefined reference to `H5::DSetCreatPropList::DEFAULT'
h5tutr_crtdat.cpp:(.text+0x8c): undefined reference to `H5::PredType::STD_I32BE'
h5tutr_crtdat.cpp:(.text+0x99): undefined reference to `H5::CommonFG::createDataSet(std::__cxx11::basic_string<char, std::char_traits<char>, std::allocator<char> > const&, H5::DataType const&, H5::DataSpace const&, H5::DSetCreatPropList const&) const'
h5tutr_crtdat.cpp:(.text+0xa5): undefined reference to `H5::DataSet::~DataSet()'
h5tutr_crtdat.cpp:(.text+0xb1): undefined reference to `H5::DataSpace::~DataSpace()'
h5tutr_crtdat.cpp:(.text+0xbd): undefined reference to `H5::H5File::~H5File()'
h5tutr_crtdat.cpp:(.text+0xdb): undefined reference to `H5::DataSpace::~DataSpace()'
h5tutr_crtdat.cpp:(.text+0xef): undefined reference to `H5::H5File::~H5File()'
h5tutr_crtdat.cpp:(.text+0x15a): undefined reference to `H5::Exception::printError(_IO_FILE*) const'
h5tutr_crtdat.cpp:(.text+0x16e): undefined reference to `H5::FileIException::~FileIException()'
h5tutr_crtdat.cpp:(.text+0x1b7): undefined reference to `H5::Exception::printError(_IO_FILE*) const'
h5tutr_crtdat.cpp:(.text+0x1cb): undefined reference to `H5::DataSetIException::~DataSetIException()'
h5tutr_crtdat.cpp:(.text+0x214): undefined reference to `H5::Exception::printError(_IO_FILE*) const'
h5tutr_crtdat.cpp:(.text+0x228): undefined reference to `H5::DataSpaceIException::~DataSpaceIException()'
h5tutr_crtdat.cpp:(.text+0x244): undefined reference to `H5::FileIException::~FileIException()'
h5tutr_crtdat.cpp:(.text+0x266): undefined reference to `H5::DataSetIException::~DataSetIException()'
h5tutr_crtdat.cpp:(.text+0x288): undefined reference to `H5::DataSpaceIException::~DataSpaceIException()'
/tmp/ccsk3JGD.o: In function `H5::FileIException::FileIException(H5::FileIException const&)':
h5tutr_crtdat.cpp:(.text._ZN2H514FileIExceptionC2ERKS0_[_ZN2H514FileIExceptionC5ERKS0_]+0x1f): undefined reference to `H5::Exception::Exception(H5::Exception const&)'
h5tutr_crtdat.cpp:(.text._ZN2H514FileIExceptionC2ERKS0_[_ZN2H514FileIExceptionC5ERKS0_]+0x24): undefined reference to `vtable for H5::FileIException'
/tmp/ccsk3JGD.o: In function `H5::DataSetIException::DataSetIException(H5::DataSetIException const&)':
h5tutr_crtdat.cpp:(.text._ZN2H517DataSetIExceptionC2ERKS0_[_ZN2H517DataSetIExceptionC5ERKS0_]+0x1f): undefined reference to `H5::Exception::Exception(H5::Exception const&)'
h5tutr_crtdat.cpp:(.text._ZN2H517DataSetIExceptionC2ERKS0_[_ZN2H517DataSetIExceptionC5ERKS0_]+0x24): undefined reference to `vtable for H5::DataSetIException'
/tmp/ccsk3JGD.o: In function `H5::DataSpaceIException::DataSpaceIException(H5::DataSpaceIException const&)':
h5tutr_crtdat.cpp:(.text._ZN2H519DataSpaceIExceptionC2ERKS0_[_ZN2H519DataSpaceIExceptionC5ERKS0_]+0x1f): undefined reference to `H5::Exception::Exception(H5::Exception const&)'
h5tutr_crtdat.cpp:(.text._ZN2H519DataSpaceIExceptionC2ERKS0_[_ZN2H519DataSpaceIExceptionC5ERKS0_]+0x24): undefined reference to `vtable for H5::DataSpaceIException'
/tmp/ccsk3JGD.o:(.gcc_except_table+0x3c): undefined reference to `typeinfo for H5::DataSpaceIException'
/tmp/ccsk3JGD.o:(.gcc_except_table+0x40): undefined reference to `typeinfo for H5::DataSetIException'
/tmp/ccsk3JGD.o:(.gcc_except_table+0x44): undefined reference to `typeinfo for H5::FileIException'    
```

So hdf5 library seems missing.

For `g++ -std=c++14 h5tutr_crtdat.cpp -o h5tutr_crtdat.exe -lhdf5_cpp` (so we're excluding `-lhdf5`), then this is obtained:  
```  
/usr/bin/ld: /tmp/ccfrKbeZ.o: undefined reference to symbol 'H5check_version'
/usr/lib64/libhdf5.so.10: error adding symbols: DSO missing from command line
collect2: error: ld returned 1 exit status
```

Note that I've also tried adding flags `-lrt -lm -lrz -Wall -ldl -lz` but they didn't see to be necessary.




