# Binary Bits Option

## Detect if two integers have opposite signs or not
	
	z = x ^ y

  if ^z^ is negative, ^x^ and ^y^ have opposite signs
	
## Add 1 to a given integer

	-~x  

## Swap two numbers without using any third variable

	if(x != y)
	{
		x = x ^ y;
		y = x ^ y;
		x = x ^ y;
	}
	
## Turn off k’th bit in a number

  n is the number and No.k bits from right

	n & ~(1 << (k-1))
	
## Turn on k’th bit in a number

	n | (1 << (k-1))

## Check if k’th bit is set for a number

	n & (1 << (k-1))

## Toggle the k-th bit

	n ^ (1 << (k-1))

## Find position of the rightmost set bit

	if(n & 1) //odd, return 1
		return 1;
	
	n = n ^ (n & (n -1)); //uset rightmost bit and xor with number itself

	int pos = 0;
	while(n){
		n = n >> 1;
		pos++;	
	}

	return pos;

## Convert uppercase character to lowercase

  Also we can use `toupper` and `tolower` function, but here we use the bit trick

 	for(ch = 'A'; ch <= 'Z'; ch++)
		printf("%c ", (ch | ' '));  //abcdefghijklmnopqrstuvwxyz

## Convert lowercase character to uppercase
	
	for(ch = 'a'; ch <= 'z'; ch++)
		printf("%c", (ch & '_' )); //ABCDEFGHIJKLMNOPQRSTUVWXYZ

## Invert alphabet’s case 

	 ch ^ ' '  //this can change upper to lower and  lower to upper at the same times

## Find letter’s position in alphabet

	 (ch & 31) 

## Abs 

	mask = n >> (sizeof(int) * 8 - 1);
	|n| = (n + mask) ^ mask;


