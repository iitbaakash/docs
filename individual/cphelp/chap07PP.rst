


Chapter 7: Programming Projects
===============================

::

    
     1. Write  a  program that allows the user to do a payroll
        listing on any number of employees, up to a maximum of 
        20, for a one week period.  This program must be 
        written using arrays and functions.  The program is to 
        be broken into various tasks, each task will be coded 
        as a function.  Each function will be passed 
        arguments and will return a value or values back from 
        the function.  Several arrays will be used in the 
        program, no array will exceed 20 elements.  One array 
        will hold the employee numbers that are input.  Other 
        arrays will hold the Computed Gross Pay, Computed 
        Federal Tax, Computed State Tax and Computed 
        Net Pay values.  When the user indicates he/she wishes 
        to stop the input of employee data, the program will 
        display a list of employee numbers, and the 
        corresponding computed values, plus a total for each of 
        the computed values. 
     
        The following shows a sample run of the program with 
        user inputs in  **boldface**.
    
        > **payroll**
        BOJ Payroll v2.0
    
        Enter Employee Number                   :  **123-45-6789**
        Enter Regular Hours Worked              :  **40**
        Enter Overtime Hours Worked             :  **0**
        Enter Hourly Pay Rate                   :  **15.00**
        Enter Marital Status( M or S )          :  **M**
        Enter number of Exemptions taken(0-4)   :  **2**
        Computed Gross Pay                      : $600.00
        Computed Federal Tax                    :-$126.90
        Computed State Tax                      :-$ 63.45
                                                ---------------
        Computed Net Pay                        : $409.65
    
        Do you wish to do another(Y/N)?  **Y**
    
        Enter Employee Number                   :  **234-56-7890**
        Enter Regular Hours Worked              :  **40**
        Enter Overtime Hours Worked             :  **0**
        Enter Hourly Pay Rate                   :  **20.00**
        Enter Marital Status( M or S )          :  **S**
        Enter number of Exemptions taken(0-4)   :  **0**
        Computed Gross Pay                      : $800.00
        Computed Federal Tax                    :-$217.50
        Computed State Tax                      :-$108.00
                                                ---------------
        Computed Net Pay                        : $474.50
    
        Do you wish to do another(Y/N)?  **N**
    
                  Employee Payroll Roster
    
        Employee       Gross     Federal   State     Net
        Number         Pay       Tax       Tax       Pay
        ----------     --------- --------- --------- ----------
        123-45-6789    $ 600.00  $ 126.90  $  63.45  $ 409.65
        234-56-7890    $ 800.00  $ 217.50  $ 108.00  $ 474.50
                       --------- --------- --------- ----------
        Totals         $1400.00  $ 471.30  $ 171.45  $ 933.65
    
        Employee  Number  is  declared  as a variable and 
        assigned a value by the user as each employee's data is 
        processed. Character Data. 
    
        Regular Hours Worked is declared as a variable  and  is  
        input by the user as each employee's data is processed. 
        Integer Data. 
    
        Overtime  Hours  Worked  is  delcared  as a variable 
        and is input by the user as each employee's data is 
        processed. Integer Data. 
    
        Hourly Pay Rate is declared as a variable and  is  
        input  by the user as each employee's data is 
        processed. Float Data. 
    
        Marital Status is  declared as a variable and is input 
        by the user as each employee's data is processed.  Only 
        M or S may be input. 
    
        Exemptions is declared as a variable and is  input  by  
        the  user as  each  employee's  data  is  processed.   
        This is the number of tax exemptions  the  employee  is  
        taking.   In  this  program,  the  only allowable 
        values for exemptions is 0 thru 4. Integer Data. 
    
        Weekly  Gross Pay is a computed value derived from 
        Regular Hours Worked  multiplied  by  Hourly  Pay  Rate  
        plus  Overtime  Hours Worked multiplied by the product 
        of Hourly Pay Rate multiplied by 1.5. 
    
        Deductions  is  a  computed value to indicate the 
        amount of tax deductions, both federal and state, 
        needed to be subtracted  from  the Adjusted  Gross  
        Pay.   Adjusted  Gross  Pay is computed by 
        taking the number of Exemptions an employee has and 
        multiplying that  by  $13.50. This  amount  is  then  
        subtracted from the Weekly Gross Pay amount to give 
        Adjusted Gross Pay.  Adjusted Gross Pay is then used to 
        determine the amount of federal tax owed and the amount 
        of state tax owed.   The following indicates how to 
        calculate the federal and state tax amounts based on 
        the Adjusted Gross Pay. 
    
    For Married Employees:
    
                                                     Of Amount
    Adjusted Gross Pay  Federal       State          Over
    ------------------  ----------    -----------   ---------------
    $0.00    - $100      10%           5%            $50.00
    $101     - $300      $20.00 + 20%  $10.00 + 10%  $150.00
    $301     - $600      $60.00 + 30%  $30.00 + 15%  $350.00
    $601     - $9999     $180.00 + 50% $90.00 + 25%  $650.00
    
    For Single Employees:
    
                                                     Of Amount
    Adjusted Gross Pay  Federal       State          Over
    ------------------  ----------    -----------   ---------------
    $0.00    - $100      10%           5%            $50.00
    $101     - $300      $20.00 + 10%  $10.00 + 5%   $150.00
    $301     - $600      $60.00 + 15%  $30.00 + 8%   $350.00
    $601     - $9999     $180.00 + 25% $90.00 + 12%  $650.00
    
        Weekly Net Pay a computed amount showing  the  take  
        home  or net  pay  for the employee.  Weekly Net Pay is 
        computed by subtracting Deductions from Weekly Gross 
        Pay. 
    
        When all employee's payroll  data  has  been  
        processed,  display  the totals for gross pay, 
        deductions and net pay. 
    
        Each  numeric  value displayed on the screen should be 
        formatted using output formatting code.  After the user  
        enters  each  value,  rewrite it  to  the  screen  in  
        proper  format  so  that  all entries will be aligned 
        in columns. 
    
     2. You are given several functions,  **calcday()**, 
         **leapyear()**,  **julian()**, and 
         **gregorian()**.  Using these functions in 
        conjunction with functions that you will write, produce 
        a program that accepts as input a date in the form, 
         **MM-DD-YYYY**, where  **MM** represents the month 
        of the year,  **DD** represents the day within
        the month and  **YYYY** represents the century and 
        year.
    
        After input of the date, display the date in textual 
        format and a calendar of the month the date falls 
        within.  Keep prompting for dates until the user inputs 
        a date of all zeros, 00-00-0000, then terminate the 
        program.  Make sure that all values input are valid.  
    
        In addition to your  **main()** function, you will 
        write a  **builddate()** function, a         
         **buildmonth()** function, and a            
         **show_date_month()** function.  This program will 
        require a two-dimensional array be used. 
    
        The following is an example run of the program with 
        user input in  **boldface**.
    
        C:\>calendar
    	   Enter a date(MM-DD-YYYY):  **10-26-1990**
    
            Friday, October 26, 1990
    
            S  M  T  W  T  F  S
               1  2  3  4  5  6
            7  8  9  10 11 12 13
            14 15 16 17 18 19 20
            21 22 23 24 25 26 27
            28 29 30 31
    
    	   Enter a date(MM-DD-YYYY):  **00-00-0000**
    
            End of program.
    
    /***************************************************************
    *   Function Name  :    int calcday( int, int, int );
    *   Description    :    Returns day of the week for a given
    *                  :    date where 1 = Sunday ... 7 = Saturday
    *                  :    For example, 12-25-1985 returns a value
    *                  :    of 4.  Christmas was on a Wednesday
    *                  :    in 1985.  Arguments passed:
    *                  :    mon  :    the month of the date that the 
    *                  :              ordinal day value is desired
    *                  :              for.
    *                  :    date :    the day of the date that the
    *                  :              ordinal day value is desired
    *                  :              value is desired for.
    *                  :    yr   :    the year of the date that the 
    *                  :              ordinal day value is desired 
    *                  :              for.
    ****************************************************************/
    
    int
    calcday( int mon, int date, int yr )
    {
    int day;
    
       if( mon <= 2 )
       {
          mon += 12;
          yr -= 1;
       }
    
       day = ( date + mon * 2 + (mon + 1) * 6 / 10 + yr + yr / 4 -
               yr / 100 + yr / 400 + 2) % 7;
    
       if( day == 0 )
          return( 7 );
       else
          return( day );
    
    }/* end of calcday() *******************************************/
    
     3. Write a program that will compute the quarter/semester 
        grades 
    for all the students in a class.  This program will make use of 
    functions and arrays.  
    
    There is a maximum of forty students in any given class.  Each 
    student has a maximum of twelve graded items.  Each student is 
    given four tests, four programming assignments, and four homework 
    assignments.  
    
    The program must prompt for and read the course identifier, and 
    section number, the student social security number, and then the 
    scores the student made on each of the twelve items, these scores 
    are a numerical value based upon a maximum score of 100.  Also, 
    each of the items has a different weight in computing the grade.  
    This weight is a percentile.  The sum of the three weights must 
    not exceed 1.00.  The weights need only be input once for a 
    class. 
    
    To terminate the input of student data, input a blank social 
    security number.
    
    After all the students and their grades have been input, the 
    program will then compute the numerical and letter grades for 
    each student.  The grade is arrived at by the sumation of the 
    scores of the items in each category, then computing the average 
    score of each category.  Using the following formula the final 
    numerical grade can be computed: 
    
        numerical_grade = weight_of_test * average_test_score
                        + weight_of_programs * average_program_score
                        + weight_of_homework * 
                          average_homework_score;
    
    After the  **numerical_grade ** is computed then the letter grade is
    determined from the following chart:
    
        100 - 93       A
        92  - 85       B
        84  - 77       C
        76  - 70       D
        69  - 0        F
    
    Finally, the program will produce a report showing each student's 
    social security number, test score average, programming score 
    average, homework score average, numerical grade and letter 
    grade.
    ****




