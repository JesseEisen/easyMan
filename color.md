# ANSI Color Codes

Start | Description | End

  `1m`   bold       __22m__
  `3m`   italic     __23m__
  `4m`   underline  __24m__
  `7m`   inverse    __27m__
  
  `37m`  white      __39m__
  `90m`  grey       __39m__
  `30m`  black      __39m__
  
  `31m`  red        __39m__
  `32m`  green      __39m__
  `33m`  yellow     __39m__
  `34m`  blue       __39m__
  `35m`  magenta    __39m__
  `36m`  cyan       __39m__

## Example

  Here are some examples used in different languages.

  **C**

	#define RED   "\x1B[31m"
	#define RESET "\x1B[0m"

	int main() {
		...
		printf("This is" RED "red" RESET "\n");
		...
	}

  another example
 
 	#define FMT "\x1B[3%dm%s\033[0m"

	int main() {
		...
		printf(FMT"\n",1,"this is red");
		...	
	}

  **Shell**

	RED="\033[31m"
	RESET="\033[0m"

	echo -e $RED "this is red" $RESET


  also can use tput to do that

	for (( i = 0; i < 8; i++ )); do
		for (( j = 0; j < 8; j++ )); do
			printf "$(tput setab $i)$(tput setaf $j)(b=$i, f=$j)$(tput sgr0)\n"
		done
	done




