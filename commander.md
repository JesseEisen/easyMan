# Commander
  Command option parser proted to C.

## Usage
  The __example__ below would produce the following ^--help^:

	Usage: example [options]

	Options:

		-V, --version                 output program version
		-h, --help                    output help information
		-v, --verbose                 enable verbose stuff
		-r, --required <arg>          required arg
		-o, --optional [arg]          optional arg

## Example

	#include <stdio.h>
	#include "commander.h"

	static void
	verbose(command_t *self) {
		  printf("verbose: enabled\n");
	}

	static void
	required(command_t *self) {
		  printf("required: %s\n", self->arg);
	}

	static void
	optional(command_t *self) {
		  printf("optional: %s\n", self->arg);
	}

	int
	main(int argc, const char **argv){
		command_t cmd;
		command_init(&cmd, argv[0], "0.0.1");
		command_option(&cmd, "-v", "--verbose", "enable verbose stuff", verbose);
		command_option(&cmd, "-r", "--required <arg>", "required arg", required);
		command_option(&cmd, "-o", "--optional [arg]", "optional arg", optional);
		command_parse(&cmd, argc, argv);
		printf("additional args:\n");
		for (int i = 0; i < cmd.argc; ++i) {
			printf("  - '%s'\n", cmd.argv[i]);
		}
		command_free(&cmd);
		return 0;
	}

## Interface
  
    	void command_init(command_t *self, const char *name, const char *version)
    	void command_option(command_t *self, const char *small, const char *large, const char *desc, command_callback_t cb)
    	void command_parse(command_t *self, int argc, char **argv)
    	void command_free(command_t *self)

## Commander Structure
	
	typedef struct command {
		void *data;
		const char *usage;
		const char *arg;
		const char *name;
		const char *version;
		int option_count;
		command_option_t options[COMMANDER_MAX_OPTIONS];
		int argc;
		char *argv[COMMANDER_MAX_ARGS];
		char **nargv;
	} command_t;

