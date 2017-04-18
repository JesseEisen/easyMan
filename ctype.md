# Standard Lib For C

** ctype **
 As found in `<ctype.h>`.

	 isalpha(c)    [a-zA-Z]
	 isupper(c)    [A-Z]
	 islower(c)    [a-z]
	 isdigit(c)    [0-9]
	 isalnum(c)    isalpha(c) | isdigit(c)
	 isspace(c)    \t \f \v \n \r
	 ispunct(c)    ! " # $ % & ' ( ) * + , - . / : ; < = > ? @ [ \ ] ^ _ ` { | } ~
	 isxdigit(c)   [a-fA-F0-9]
	 isgraph(c)
	 isctrl(c)

	tolower(c)    return c converted to lower case
	toupper(c)    return c converted to upper case

** Limit **

  As found in `<limits.h>`

	CHAR_BIT	size of the char Type
	CHAR_MIN	minimum possible value of char
	CHAR_MAX	maximum possible value of char
	SHRT_MIN	minimum possible value of short int
	SHRT_MAX	maximum possible value of short int
	INT_MIN		minimum possible value of signed int
	INT_MAX		maximum possible value of signed int
	LONG_MIN	minimum possible value of signed long
	LONG_MAX	maximum possible value of signed long
	LLONG_MIN	minimum possible value of signed long long
	LLONG_MAX	maximum possible value of signed long long

  The `unsigned` only need to add ^**U**^ before each marco.
  The range of the each type will display below

 	signed char     -- 		[-127,127]
	unsigned char   -- 		[0,2^CHAR_BIT-1]
	signed short    --		[-32767, +32767](at least)
	signed int      --		[-32767, +32767]
	signed long	    -- 		[-2147483647,+2147483647]
	signedlong long	--		[−9223372036854775807 , +9223372036854775807]
		

