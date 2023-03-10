This program is a simple shell that allows users to enter and execute commands. It supports both built-in and external commands. Global variables used include str, args, argsCount, and statusPtr. The str stores the user's input, args stores the parsed input arguments, argsCount keeps track of the number of arguments, and statusPtr is used to store the status of the child process.

The main functions of the program are:

onChildExit function: called when a child process exits, it logs the termination process to a file called "log.txt".
log function: called by onChildExit to write the log message to the file.
setupEnvironment function: sets up the current working directory of the shell.
shell function: the main loop of the program that reads input from the user, parses it, evaluates it, and executes it.
executeCommand function: executes the external commands.
executeBuiltIn function: executes the built-in commands.
cdCommand function: contains the implementation of the cd command with its different cases.
echoCommand function: contains the implementation of the echo command.
exportCommand function: contains the implementation of the export command and deals with the double quotes for getting a string with in-between spaces then storing the variables and their values in the environment.
Secondary functions of the program are:

getInput function: gets the input from the user.
parseInput function: parses the user's input into arguments.
evaluateArgs function: evaluates each argument and replaces any environment variable references with their values.
getType function: determines the type of input whether it is a built-in command, an external command, or exit command.
closeFile function: prints a line in the logging file when exiting the shell to separate between different runs in the same logging file.
The main function registers a signal handler for child processes using the signal function and then calls the setupEnvironment and shell functions.
