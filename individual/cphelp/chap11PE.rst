


Chapter 11: Programming Exercises
=================================

::

    
    Given the following class interface file.
     
    //***************************************************************
    //  File :    cstring.h
    //
    //  Declare a "CString" data type.
    //
    //  Note:     Couldn't use String.h as name because we include
    //            ANSI C's string.h, and some systems (such as MS-DOS)
    //            do not differentiate between uppercase and lowercase
    //            letters in file names.
    //***************************************************************
    #pragma interface
    
    #ifndef CSTRING_H      // Make sure file is included only once
    #define CSTRING_H
    
    #ifndef bool
        enum bool { false, true };
    #endif
    
    #include  
    #include           // for size_t type
    #include           // for ANSI C string library
    #include types.h>
    
    #define MAXLEN     256
    #define DEFAULT_STRING_SIZE_INCREM     10
    
    class CSubstring;
    
    class CString
    {
    public:
        /  Constructor
        CString();
        CString( const size_t );
        CString( const char *);
        CString( const CString& );
        CString( const char *, const size_t );
        CString( const CString&, const size_t );
        //  Destructor
        ~CString() { delete s; }
        //  Overloaded operators
        //***********************************************************
        // CString equality operator.  Returns nonzero if strings
        // are equal
        bool operator==(const CString& str) const
        {
             // Use ANSI C's strcmp() function to compare the
             // strings.  Remember strcmp() returns 0 if strings
             // match, but this function has to return non-zero
             // for a match
             return( (strcmp( str.s, s ) ? false : true) );
    
        }
        //***********************************************************
        // CString equality operator.  Returns nonzero if string
        // and pointer to char are equal
        bool operator==(const char *str) const
        {
             // Use ANSI C's strcmp() function to compare the
             // strings.  Remember strcmp() returns 0 if strings
             // match, but this function has to return non-zero
             // for a match
             return( (strcmp( str, s ) ? false : true ) );
    
        }
        //***********************************************************
        // CString less than operator.  Returns nonzero if string 1
        // is less than string 2
        bool operator<(const CString& str) const
        {
             // Use ANSI C's strcmp() function to compare the
             // strings.  Remember strcmp() returns 0 if strings
             // match, but this function has to return non-zero
             // for a match
             return( (strcmp( str.s, s ) < 0 ? true : false ) );
    
        }
        //***********************************************************
        // CString greater than operator.  Returns nonzero if string1
        // is greater than string2
        bool operator>(const CString& str) const
        {
             // Use ANSI C's strcmp() function to compare the
             // strings.  Remember strcmp() returns 0 if strings
             // match, but this function has to return non-zero
             // for a match
             return( (strcmp( str.s, s ) > 0 ? true : false) );
    
        }
        //***********************************************************
        // CString less than or equal to operator.  Returns nonzero if
        // string1 is less than or equal to string2
        bool operator<=(const CString& str) const
        {
             // Use ANSI C's strcmp() function to compare the
             // strings.  Remember strcmp() returns 0 if strings
             // match, but this function has to return non-zero
             // for a match
             return( (strcmp( str.s, s ) <= 0 ? true : false ) );
    
        }
        //***********************************************************
        // CString greater than or equal to  operator.  Returns
        // nonzero if string1 is greater than or equal to string2.
        bool operator>=(const CString& str) const
        {
             // Use ANSI C's strcmp() function to compare the
             // strings.  Remember strcmp() returns 0 if strings
             // match, but this function has to return non-zero
             // for a match
             return( (strcmp( str.s, s ) >= 0 ? true : false ) );
    
        }
        //***********************************************************
        // CString not equal to operator.  Returns nonzero if string1
        // is not equal to
        bool operator!=(const CString& str) const
        {
             // Use ANSI C's strcmp() function to compare the
             // strings.  Remember strcmp() returns 0 if strings
             // match, but this function has to return non-zero
             // for a match
             return( (strcmp( str.s, s ) != 0 ? true : false ) );
    
        }
        //***********************************************************
        // CString not equal to operator.  Returns nonzero if string1
        // is not equal to
        bool operator!=( const char *str ) const
        {
             return( (strcmp( str, s) != 0 ? true : false ));
        }
        //  Assignment operator
        CString& operator=(const CString&);
        CString& operator=(const char *);
        CString& operator=(const char);
        //  Type conversion operator from CString to char *
        operator const char*() const { return s; }
        //  The += operator concatenates and assigns
        CString& operator+=(const CString& );
        CString& operator+=(const char* );
        CString& operator+=(const char );
        //  The + operator concatenates strings
        friend CString operator+(char *, CString& );
        friend CString operator+(CString&, CString& );
        friend CString operator+(CString&, char *);
        //  Access operator
        char& operator[](int index);
        // resize of string
        CString& resize(unsigned );
        // return string content as char *
        char *getContent()
        {
             return s;
        }
        //  Function giving access to internal variable
        size_t length( void ) const { return ( len ); }
        //  Function to print a CString
        void print( ostream& os ) const;
        void print( void ) const;
        //  Function to access a character in a CString
        char& char_at_pos( int );
        //  Replace a portion of a string with another
        //  Used to insert or delete parts of a string
        CString& replace( size_t pos, size_t len, const char* s);
        //  operator ()
        //  Overload the function call operator to return a 
        //  CSubstring
        CSubstring operator()( size_t pos, size_t len );
    
    protected:
        //  Internal data members of this class
        char *s;            //   pointer to allocated space
        size_t len;         //   current length of string
        size_t maxlen;      //   numbers of bytes allocated
        size_t sizeIncr;    //   increment on resize
    
    };
    // Stream I/O operators for CString class
    
    // #include 
    
    ostream& operator<<(ostream& os, CString& str);
    istream& operator>>(istream& is, CString& str);
    
    //**************************************************************
    //  Declare the Substring class
    
    class CSubstring    :    public CString
    {
    public:
        friend CString;// Give the CString class access to this class
    
        //   CSubstring operators ...
        CString& operator=( const char* str )
        {
             return s_original.replace( pos, len, str );
        }
    
        CString& operator=( CSubstring& s1 )
        {
             return s_original.replace( pos, len, s1.s );
        }
    
    private:
        CString&   s_original;   // Reference to original CString
        size_t    pos;           // Position of Substring in CString
    
        //   CSubstring constructor
        CSubstring( CString& s1, const char *cs, size_t pos1
                  , size_t len1 )
        : CString(cs, len1), s_original(s1), pos( pos1 ) {}
    
        //   CSubstring copy constructor
        CSubstring( const CSubstring& s1) : CString( s1 ),
             s_original( s1.s_original) , pos( s1.pos ) {}
    };
    #endif
    
    Develop the following operator overload functions:
    
     1. CString equality operator.  Returns 'true' if strings
        are equal and 'false' if not.
    
     2. CString equality operator.  Returns 'true' if string
        and pointer to char are equal and 'false' if not.
    
     3. CString less than operator.  Returns 'true' if string 1 
        is less than string 2 and 'false' if not.
    
     4. CString greater than operator.  Returns 'true' if 
        string1 is greater than string2 and 'false' if not.
    
     5. CString less than or equal to operator.  Returns 'true' 
        if string1 is less than or equal to string2 and 'false' 
        if not.
    
     6. CString greater than or equal to  operator.  Returns
        'true' if string1 is greater than or equal to string2
        and 'false' if not.
    
     7. CString not equal to operator.  Returns 'true' if 
        string1 is not equal to and 'false' if not.
    
     8. CString not equal to operator.  Returns 'true' if 
        string1 is not equal to string2 and 'false' if not.
    
     9. CString& operator=(const CString&);
        CString& operator=(const char *);
        CString& operator=(const char);
        //  Type conversion operator from CString to char *
        operator const char*() const { return s; }
        //  The += operator concatenates and assigns
        CString& operator+=(const CString& );
        CString& operator+=(const char* );
        CString& operator+=(const char );
        //  The + operator concatenates strings
        friend CString operator+(char *, CString& );
        friend CString operator+(CString&, CString& );
        friend CString operator+(CString&, char *);
        //  Access a single character operator
        char& operator[](int index);
    
    10. Develop a test program that tests all of the operator 
        overload functions of the CString class.




