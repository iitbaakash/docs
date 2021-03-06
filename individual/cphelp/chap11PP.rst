


Chapter 11: Programming Projects
================================

::

    
     1. You are to create an interactive program that will 
        present the following menu. 
    
        0: Quit
        1: Add an Event
        2: View Events
    
        An Event is a structure or class as follows:
    
        long julianDate;    // the date the event is scheduled 
                            // for
        long theTime;       // the time the event is scheduled 
                            // for
        char theEvent[256]; // the statement about the event
    
        This program will be written in C++ and you will create 
        the following C++ classes.  
    
        CMenu - stores a list of menu items; presents those 
                menu items on the screen; reads a selected menu 
                item and returns an integer value representing 
                the item selected.
    
        CDateTime - acquires the current date and time from the 
                    system; keeps the date in gregorian and 
                    julian formats; holds a string that 
                    represents the current date, i.e. 
                    "Monday, November 27, 1995"; holds the time 
                    in hh:mm:ss format and in twenty-four hour 
                    format.  Overload the following operators:
    
             + : adds a specified number of days to a julian
                 date.
             - : substracts a specified number of days from a
                 julian date.
    
        CDocument - opens a disk file and stores or retrieves 
                    data from the file depending upon which 
                    method of the class is called. The 
                    constructor is passed the name of the file 
                    to open, if the file does not exist then it 
                    is created.  The file is assumed to always 
                    be a binary data file.  This class holds 
                    the data for the events.  Overload the 
                    following operators:
    
             ++ : move to next item in document
             -- : move to previous item in document
             +  : add a new item to the document
             -  : delete an item from the document
    
        CView - displays data on the screen, one screen at a 
                time; supports the input of 'N' or 'n' for next 
                screen and 'P' or 'p' for previous screen; 
                also, 'q' or 'Q' for quit which returns back to 
                the main menu.
    
        In order for the program to obtain the current date and 
        time from the operating system.  The date and time can 
        be obtained by calling the  **time()** and 
         **localtime()** functions. The following is a 
        sample program that obtains the date and time from the 
        system: 
    
        #include 
        #include types.h>
        #include <time.h>
    
        main()
        {
        struct tm *ptr;
        int nseconds;
    
             nseconds = time( (time_t)NULL );
             ptr = localtime( &nseconds );
             printf("\nptr->tm_sec = %d",ptr->tm_sec);
             printf("\nptr->tm_min = %d",ptr->tm_min);
             printf("\nptr->tm_hour = %d",ptr->tm_hour);
             printf("\nptr->tm_mday = %d",ptr-tm_mday);
             printf("\nptr->tm_mon = %d",ptr->tm_mon);
             printf("\nptr->tm_year = %d",ptr->tm_year);
             printf("\nptr->tm_wday = %d",ptr->tm_wday);
             printf("\nptr->tm_yday = %d",ptr->tm_yday);
             printf("\nptr->tm_isdst = %d",ptr->tm_isdst);
             printf("\n");
        }
    
        The structure, <B>struct tm<B>, has the following 
        layout:
    
        struct tm
        {
             int tm_sec;    /* seconds after the minute ( 0 - 59 ) */
             int tm_min;    /* minutes after the hour ( 0 - 59 ) */
             int tm_hour;   /* hours since midnight ( 0 - 23 ) */
             int tm_mday;   /* day of the month ( 1 - 31 ) */
             int tm_mon;    /* month of the year ( 0 - 11 ) */
             int tm_year;   /* years since 1900 */
             int tm_wday;   /* days since Sunday ( 0 - 6 ) */
             int tm_yday;   /* day of the year ( 0 - 365 ) */
             int tm_isdst;  /* daylight savings time flag */ 
                            /* ( 1 = dst ) */
        };
    
     2. Write a program that maintains a list of contacts that 
        you have made at various businesses.  The program will 
        be menu driven and present the following menu:
    
        1. Add a contact
        2. Show contacts
        3. Quit application.
    
        The data held for each contact should be as follows: 
    
    Field              Type         
    -----------------------------
    First Name         CString   
    Last Name          CString   
    Title              CString   
    Company            CString   
    Company Type       CString   
    Address            CString   
    Address2           CString   
    City               CString   
    State              CString   
    Zip                CString   
    Voice Phone        CString   
    Fax Phone          CString   
    Home Phone         CString   
    Home Fax Phone     CString   
    E-Mail Address     CString   
    Last Contact       CDateTime
    
        The following classes need to be developed for the 
        application:
    
    
        CMenu - stores a list of menu items; presents those 
                menu items on the screen; reads a selected menu 
                item and returns an integer value representing 
                the item selected.
    
        CDateTime - acquires the current date and time from the 
                    system; keeps the date in gregorian and 
                    julian formats; holds a string that 
                    represents the current date, i.e. 
                    "Monday, November 27, 1995"; holds the time 
                    in hh:mm:ss format and in twenty-four hour 
                    format.  Has a constructor that is 
                    initialized with the month, day, and year 
                    for a specified date.  Overload the 
                    following operators:
    
             + : adds a specified number of days to a julian
                 date.
             - : substracts a specified number of days from a
                 julian date.
    
        CDocument - opens a disk file and stores or retrieves 
                    data from the file depending upon which 
                    method of the class is called. The 
                    constructor is passed the name of the file 
                    to open, if the file does not exist then it 
                    is created.  The file is assumed to always 
                    be a binary data file.  This class 
                    holds the data that is being managed.  
                    Overload the following operators:
    
             ++ : move to next item in document
             -- : move to previous item in document
             +  : add a new item to the document
             -  : delete an item from the document
    
        CView - displays data on the screen, one screen at a 
                time;  supports the input of 'N' or 'n' for 
                next screen and 'P' or 'p' for previous screen; 
                also, 'q' or 'Q' for quit which returns back to 
                the main menu.




