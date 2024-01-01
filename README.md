# BASIC-COMMAND-SHELL
I MADE IT USING C LANGUAGE


Overview:
The program is a simple command-line shell written in C. It allows users to interact with the system by entering commands, executing them, and even running scripts. The shell provides features such as executing commands, changing directories, and running scripts.

Key Features:
Signal Handling:

The program sets up a signal handler (signalHandler) to catch signals, such as Ctrl+C (SIGINT). This allows for graceful termination or cleanup if needed.
Input Parsing:

The parseInput function is responsible for breaking down user input into individual command arguments. It tokenizes the input string based on spaces, tabs, and newline characters.
Command Execution:

The executeCommand function is used to fork a child process and execute a command. It employs execvp to replace the child process with the specified command.
Script Execution:

The program supports script execution using the "source" command. Users can run scripts by providing a filename following the "source" command.
Security Considerations:

Security measures have been implemented to minimize potential risks:
The program drops privileges in the child process using setuid(getuid()) to reduce the risk of privilege escalation.
Input validation is in place for script filenames to ensure they do not contain special characters or directory separators, helping prevent injection attacks.
Command arguments are validated to avoid special characters that could be exploited for injection attacks.
Directory Change (cd command):

The program supports changing directories using the "cd" command. It checks for the "cd" command and handles directory changes securely.
User Interaction Loop:

The main loop of the program continuously prompts the user with "Shell>" and waits for input. It reads user input using fgets.
Exit Mechanism:

The user can exit the shell by entering the "exit" command, which sets shouldRun to 0.
How to Use:
Executing Commands:

Users can enter standard shell commands (e.g., ls, pwd) directly into the shell.
Changing Directories:

To change directories, users can use the "cd" command followed by the desired directory.
bash
Copy code
Shell> cd /path/to/directory
Executing Scripts:

Users can run scripts using the "source" command followed by the script filename.
bash
Copy code
Shell> source myscript.sh
Exiting the Shell:

To exit the shell, users can enter the "exit" command.
bash
Copy code
Shell> exit
Security Considerations:
Privilege Separation:

The use of setuid(getuid()) in the child process helps limit the privileges of the executed commands.
Input Validation:

Script filenames are validated to ensure they do not contain special characters or directory separators, reducing the risk of injection attacks.
Command Argument Validation:

Each command argument is checked for special characters that could be exploited for injection attacks.
Conclusion:
This shell program provides a basic command-line interface with essential features and incorporates security considerations to mitigate potential risks associated with user input and command execution. However, in a production environment, additional security measures and thorough testing would be necessary to ensure a high level of security and reliability.





