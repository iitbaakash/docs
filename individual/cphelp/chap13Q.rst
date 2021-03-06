


Chapter 13: Review Questions
============================

::

    
     T  F    1.   Standard files are always present and do not 
                  need to be opened or closed.
               
     T  F    2.   The FILE pointer for standard file names can 
                  always be used on the left side of an 
                  assignment.
    
     T  F    3.   The  **fopen()** function returns a NULL if 
                  there is a problem opening the file.
    
     T  F    4.   After opening a file ther is an internal file 
                  pointer which represents the position within 
                  the file where the input or output is being 
                  performed.
    
     T  F    5.   Two backslashes are needed inside strings (to 
                  represent one backslash) because one 
                  backslash merely indicates that the following 
                  character is to be taken literally.
               
     T  F    6.   The  **ftell()** function serves double 
                  duty, both positioning and reporting position 
                  within a file.
               
     T  F    7.   The ANSI standard defines only three standard 
                  file handles: input, output, and error.
               
     T  F    8.   The  **extern** keyword is used to provide 
                  access to variables defined in another source 
                  file.
    
     T  F    9.   Line input and record input are the same 
                  thing in C.
    
     T  F    10.  In binary files any carriage returns that 
                  appear before a line feed are dropped.
                
     T  F    11.  The internal file pointer can be positioned 
                  relative to the first, end or current 
                  location in the file.
    
     T  F    12.   **SEEK_SET** is a value passed to the 
                   **ftell()** function.
                
     T  F    13.  When reading binary files no changes are 
                  automatically made to the characters that are 
                  read.
    
     T  F    14.  The function  **fopen()** returns a NULL if 
                  the requested file cannot be opened.
    
     T  F    15.  Line input is not convenient since the input 
                  lines can be split across two buffers.
    
     T  F    16.  If a binary file is read as a text file, an 
                  integer may appear as a carriage return-line 
                  feed sequence.
    
     T  F    17.  The  **sizeof** operator should be used 
                  when reading data to fill a structure.
    
    18. Match the following:
    
    ____     int                   A.   open fails if the file 
                                           does not exist
    
    ____     virtual void xyz()=0;    B.   open a data stream not 
                                           attached to any file
    
    ____     class B : public A       C.   opens and moves to end
                                           of file
                                                                                  
    ____     ~XYZ() {}                D.   pure virtural function
                                           
    ____     operator+(Str x, Str y); E.   opens the file for read 
                                           only
    
    ____     class B : A              F.   open fails if the file
                                           does exist
                                                                                  
    ____     fstream fd;              G.   class destructor
    
    ____     protected                H.   a reference variable
    
    ____     ios::in                  I.   derived class to access
                                           all sections of base class
                                           as private members
    
    ____     ios::ate                 J.   derived class to access
                                           all sections of base class
                                           as public members
    
    ____     ios::noreplace           K.   operator overloading
    
    ____     ios::nocreate            L.   allows derived classes to
                                           access its members but 
                                           works as private to all 
                                           others
    




