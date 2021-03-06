


Chapter 6: Programming Projects
===============================

::

    
     1. Write  a  program that allows the user to do a payroll 
        listing on any number of employees, up to a maximum of 
        20, for a one week period.   **This program must be 
        written using functions**.  The program is to be 
        broken into various tasks, each task will be coded as a 
        function.  Each function will be passed arguments and
        possibly will return a value back from the function.
    
        When the user indicates he/she wishes to stop the input 
        of employee data, the program will display totals for 
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
    
    		    Employee Payroll Summary
    
    			    Gross     Federal   State     Net
    			    Pay       Tax       Tax       Pay
    			    --------- --------- --------- ----------
        Totals         $1400.00  $ 471.30  $ 171.45  $ 933.65
    
        Employee  Number  is  declared  as a variable and 
        assigned a value by the user as each employee's data is 
        processed. Character Data.
    
        Regular Hours Worked is declared as a variable and is  
        input by the user as each employee's data is processed. 
        Integer Data. Not to exceed 40 hours.
    
        Overtime  Hours  Worked  is  declared  as a variable 
        and is input by the user as each employee's data is 
        processed. Integer Data.
    
        Hourly Pay Rate is declared as a variable and is input  
        by the user as each employee's data is processed. Float 
        Data.  Not to exceed 55.00 dollars per hour.
    
        Marital Status is declared as a variable and is input 
        by the user as each employee's data is processed.  Only 
        M or S may be input.
    
        Exemptions is declared as a variable and is input by 
        the user as each employee's data is processed.   This 
        is the number of tax exemptions the employee is taking.   
        In this  program,  the only allowable values for 
        exemptions is 0 thru 4. Integer Data.
    
        Weekly  Gross Pay is a computed value derived from 
        Regular Hours Worked  multiplied  by  Hourly  Pay  Rate  
        plus  Overtime  Hours Worked multiplied by the product 
        of Hourly Pay Rate multiplied by 1.5.
    
        Deductions  is  a  computed value to indicate the 
        amount of tax deductions, both federal and state, 
        needed to be subtracted  from the Adjusted  Gross  Pay.   
        Adjusted  Gross  Pay is computed by taking the number 
        of Exemptions an employee has and multiplying that by
        $13.50. This  amount  is  then  subtracted from the
        Weekly Gross Pay amount to give Adjusted Gross Pay.  
        Adjusted Gross Pay is then used to determine the amount 
        of federal tax owed and the amount of state tax owed.   
        The following indicates how to calculate the federal 
        and state tax amounts based on the Adjusted Gross Pay.
    
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
       home  or net pay  for the employee.  Weekly Net Pay is 
       computed by subtracting Deductions from Weekly Gross 
       Pay.
    
       When all employee's payroll data has been processed, 
       display  the totals for gross pay, state and federal 
       withholding and net pay.
    
     2. Write a program that acts as a simple "printing" 
        calculator. The program should allow the user to type 
        in expressions of the form
    
        number    operator
    
        The following operators should be recognized by the 
        program:
    
        +    -    *    /    %    S    E
    
        The S operator tells the program to set the 
        "accumulator" to the typed-in number.  The E operator 
        tells the program that execution is to end.  The 
        arithmetic operations are performed on the contents of 
        the accumulator with the number that was keyed in
        acting as the second operand.  The following is a 
        "sample run" showing how the program should operate.  
        The user input is in  **boldface **.
    
        > **calc**
        Begin Calculations
         **10 S**                /* set accumulator to 10 */
        = 10.000000         /* contents of accumulator */
         **2 /**                 /* divide by 2 */
        = 5.000000          /* contents of accumulator */
         **55 -**                /* subtract 55 */
        = -50.000000        /* contents of accumulator */
         **2 %**                 /* modulo divide by 2 */
        = 2.000000          /* contents of accumulator */
         **100.25 S**            /* set accumulator to 100.25 */
        = 100.250000        /* contents of accumulator */
         **4 ***                 /* multiply by 4 */
        = 401.000000        /* contents of accumulator */
         **0 E**                 /* end of program */
        = 401.000000        /* contents of accumulator */
        End of Calculations.
    
     3. Write a program that will update a bank balance.  A 
        sample run is below.  The user's response is in 
         **boldface**.
    
        Bank Account Program
        --------------------
    
        Enter the old balance:  **1234.50**
        Enter the transactions now. Enter an  **F** for the transaction
        type when you are finished.
        Transaction Type (D=deposit, W=withdrawal, F=finished):  **D**
        Amount:  **568.34**
        Transaction Type (D=deposit, W=withdrawal, F=finished):  **W**
        Amount:  **25.68**
        Transaction Type (D=deposit, W=withdrawal, F=finished):  **W**
        Amount:  **167.40**
        Transaction Type (D=deposit, W=withdrawal, F=finished):  **F**
        Your ending balance is $1609.76
        End of Program
    
     4. The sequence of Fibonacci numbers is defined 
        recursively by 
    
        f(0) = 0,      f(1) = 1, f(i+1) = f(i) + f(i+-1)
    
        for i = 1, 2, ..
    
        Except for f(0) and f(1), every element in the sequence 
        is the sum of the previous two elements.  It is easy to 
        write down the first few elements of the sequence.
    
        0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, ...
    
        Fibonacci numbers have lots of uses and many 
        interesting properties.  One of the properties has to 
        do with the Fibonacci quotients defined by
    
        q(i) = f(i) / f(i-1)     for i = 2, 3, ...
    
        It can be show that the sequence of quotients converges 
        to the golden mean, which is the real number 
        (1+ sqrt(5)) / 2.  We want to write a program that 
        prints Fibonacci numbers and quotients.  If  **f1** 
        contains the value of the current Fibonacci number and 
         **f0** contains the value of the previous
        Fibonacci number, then we can
    
        1.   Save the value of  **f1** (the current Fibonacci 
             number in a temporary.
    
        2.   Add  **f0** and  **f1** and store the value in 
              **f1**, the new Fibonacci number.
    
        3.   Store the value of the temporary in  **f0** so 
             that  **f0** will contain the previous Fibonacci 
             number.
    
        4.   Print, and then repeat this process.
    
        Because the Fibonacci numbers grow large very quickly, 
        we are not able to compute many of them.
    
    ****




