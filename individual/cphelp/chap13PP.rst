


Chapter 13: Programming Projects
================================

::

    
     1. Write a line oriented text editor program in C++ that 
        accepts the input of the file to be edited on the 
        command line.  If the file name is not input on the 
        command line, the program indicates that the file does 
        not exist and terminates.  If the file is present, 
        the contents of the file are read into memory and 
        placed into a list for further processing.
    
        A line editor is represented by a doubly linked list of 
        nodes, each of which contains a pointer to the text of 
        the line.  In addition, each node contains the number 
        of bytes in the text line.  There is one external 
        pointer to this list, which points to the "current" 
        line position in the text being edited.  The 
        list has a header node, which contains the string: 
    
        '----Top of File----'
    
        and a trailer node, which contains the string:
    
        '----Bottom of File----'
    
        Write a line editor that only supports the listing of 
        lines of text to the screen.  The program will execute 
        and display the first line of text in the file along 
        with the line number of that line.  The program will 
        then show its prompt, a ' **?**', and is ready to 
        accept commands.  For example:
    
        ----Top of File----
        1: main()
    ?
    
        If a list or print of lines goes to the end of the 
        file, the trailer node holding 
    
        ' **----Bottom of File----**' 
    
        must be displayed as the last line.
    
        Each node of the linked list holds a  **CTextLine** 
        class item.  A  **CTextLine** is a class that is 
        derived from  **CRecord** which is an abstract base 
        class that generically defines records that are 
        held within a document.  The  **CTextLine** class has 
        the following data members.  
    
        char *textLine;    // the text of a line from the file
        size_t textLgth;   // the length of the line being held
    
        The abstract base class  **CRecord** defines two pure 
        virtual functions for reading input from the disk and 
        for placing data onto the disk. 
    
         **virtual void readRecord( size_t length) const = 0;**
         **virtual void writeRecord( size_t length) const = 0;**
    
        The  **CTextLine** class implements its own versions 
        of these functions in order to read and write data to 
        disk. 
    
        This program will create the following C++ classes.  
    
        CDocument - opens a disk file and stores or retrieves 
                    data from the file depending upon which 
                    method of the class is called. The 
                    constructor is passed two arguments:
    
                    - the name of the file to open, if the file 
                      does not exist a boolean is set                   indicating such.
     
            	    - the address of a  **CRecord** class or 
                      derived class.
    
                    This class has a pointer to the 
                     **CRecord** class which holds the
                    address passed as a parameter of the 
                    constructor.  Overload the following 
                    operators:
    
             ++ : move to next item in document
             -- : move to previous item in document
             +  : add a new item to the document
             -  : delete an item from the document
    
                   Use the pointer to the  **CRecord** type 
                   to access the correct derived class that 
                   knows how to read and write data of the 
                   correct type to and from the disk.
    
        CView - displays data on the screen, one screen at a 
                time
    
        CCommandSet - this class holds the commands allowed and 
                      maps those keys to methods within this 
                      class.  The initial command set will be 
                      as follows:
                     ( **** means that the RETURN key is 
                          pressed)
    
                            show next line in file
                                m,np  show the lines of 
                                text starting with line number 
                                 **m** and ending with line 
                                number ' **n**'
    
                      n     show the text for line number 
                                ' **n**'
    
                      np    show the next ' **n**' lines 
                                of text in the file
       
                w filename  write the contents of the 
                                linked list to the 
             			    ' **filename**' specified.
    
                      q     quit the editor
    
     2. Develop the following classes:
    
             CDataBase - a data base class that opens a data 
                         file and an index file.  This class 
                         supports a 'has-a' relationship with 
                          **CRecord** and  **CIndex**.  
                         This class will support methods for:
    
                  - define the location of a key in each record
                    as being a specified number of bytes from
                    the beginning of the record and being a 
                    stated number of bytes in length.
    
                  - receiving an address of  **CRecord** type 
                    object and placing the data held in the 
                    object on the data file through polymorphic 
                    behavior
    
                  - retrieving data from the data file by using 
                    an address of a  **CRecord** type object 
                    that reads the data file.
                    
                  - has an instance of  **CIndex** type data 
                    that is used to maintain a sorted list of 
                    keys into the data file.
    
             CRecord - an abstract base class that defines 
                       generic behavior for a record that is to 
                       be written to or read from the data file 
                       of the data base.
    
             CIndex - a class that keeps a sorted array of keys 
                      into the data file.  A key is a structure 
                      that has a the following format:
    
                  struct Key
                  {
                       char *keyValue;     // holds the value that is
                                           // used as a key to access
                                           // the associated data 
                                           // record; keys are always
                                           // characters
                       long dataOffset;    // the number of bytes
                                           // from the beginning of
                                           // the data file where the
                                           // associated record is 
                                           // stored
                  };
    
                    The index is saved into an index file when 
                    the data base is closed.
    
        Also, develop a test program that will save student 
        information,  **CStudent**, into the data base, using 
        student social security number as the key.     
         **CStudent** will be a derived class from 
         **CRecord**.  Make the program present a
        menu,  **CMenu**, that has the following items.
    
    
             1. Add students
             2. View students
             3. Quit application
    
        The program must acquire student data interactively 
        from the keyboard and store that data into the data 
        base.  When processing a request to view the data, the 
        data will be show in the ascending order of the key 
        field, student social security number.
    
         **CStudent** has the following data members.
    
             Social Security Number
             Last Name
             First Name
             Street
             City
             State
             Zip
             Area Code
             Phone
             Major
    




