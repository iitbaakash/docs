


Chapter 8: Programming Exercises
================================

::

     
    1. One very useful search algorithm for sorted lists is the
       binary search.  Write a program that will display the 
       following menu: 
    
        0. Quit
        1. Input Names
        2. Sort Names
        3. Search for Name
    
      The program will prompt for an input of a last name and 
      store the name into an array of pointers,  **char 
      *theNames[20]**.  A maximum of twenty names will be 
      input or until the user indicates completion of input.
      The array can be sorted in ascending order using the 
      bubble sort algorithm.  A given name can be searched for 
      with the binary search algorithm. The algorithm is as 
      follows: 
    
      A.  Divide the sorted list into two halves.
      B.  Compare the element searched for with the midpoint 
          element.
      C.  If the midpoint element is equal to the searched 
          element, then we are finished.  If not, determine 
          which sublist the element should be in, top or 
          bottom.  This is the new list to search.
      D.  Repeat steps A through C until the element is found 
          or the searched list shrinks to zero, whichever 
          occurs first.
    
    2. Write a program that prompts for the input of a text 
       string.  The program should loop accepting text strings 
       until the word 'end' is input as the only text on the 
       input line.  The lines input must be stored into an 
       array of pointers,  **char *text[20];**, 
       no more than twenty lines to be input and allow the user 
       to quit input early.  Write a function  **encrypt()** 
       that encrypts the text held in the array.  The 
       encryption algorithm will be your year of birth bitwise 
       exclusive or-ed with each character in the text 
       string.  Print the text strings before encryption and 
       after encryption. 
    
    3. Write a program that will find, search and replace text 
       strings.  The program must prompt for the input of an 
       initial line of text.  The program will then prompt for 
       a phrase to be searched for and a phrase to replace the 
       found phrase with.  The replacement phrase can be 
       shorter or longer than the searched for phrase.  Show 
       the updated initial line of text on the display.




