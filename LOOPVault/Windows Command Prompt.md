# <center>Windows Command Lines</center>

# Contents

1. [[#FILE|File]]
    - [[#Types of Files]]
    - [[#Metadata]]
2. [[#FOLDER/DIRECTORY|Folder/Directory]]
    - [[#Current Working Directory (cwd)]]
3. [[#PATH|Path]]
    - [[#Types of Paths]]
4. [[#ENVIRONMENT VARIABLES|Environment Variables]]
5. [[#USER INTERFACE|User Interface]]
6. [[#KERNEL|Kernel]]
7. [[#OPERATING SYSTEM VS. KERNEL|Operating System vs. Kernel]]
8. [[#SHELL|Shell]]
9. [[#TERMINAL|Terminal]]
10. [[#Command Prompt|Command Prompt]]
11. [[#Commands]]
12. [[#Input and Output Redirections]]
13. [[#Some more commands]]

---

# FILE

A file is a collection of digital data stored as a single object on a storage device such as a hard disk, SSD, or other media. It acts as a container for information, which can be text, images, audio, video, software programs, or any other type of data.

A file can be identified by its filename and usually a file extension that indicates its type.
The following are some common file extensions:

| File Type | File Extensions |
| :--- | :--- |
| Text file | `.txt` |
| Image | `.jpg`, `.jpeg`, `.png`, `.svg`, `.gif`, `.bmp` |
| Audio | `.mp3`, `.m4a`, `.wav`, `.ogg`, `.flac`, `.aac` |
| Video | `.mp4`, `.avi`, `.mkv` |
| Portable Document Format (PDF) | `.pdf` |
| Archive | `.zip`, `.7z`, `.rar`, `.tar`, `.tar.gz` |
| C Source File | `.c` |
| C Header File | `.h` |
| Windows Executable File | `.exe` |
| Microsoft Software Installer | `.msi` |

## Types of Files

There are mainly two types of files:

1. Text Files
2. Binary Files


| Aspect | Text File | Binary File |
| :----: | ------ | ---- |
| **Content** | Human-readable characters (plain text) | Non-human-readable data (raw bytes: `0`s and `1`s) |
| **Readability** | Can be opened and understood in any basic text editor | Appears as gibberish in a text editor; needs special software |
| **Encoding** | Uses character encoding like ASCII or Unicode | No character encoding; stores data as raw bytes |
| **Examples** | `.txt`, `.csv`, `.html`, `.c` | `.jpg`, `.mp3`, `.exe`, `.pdf` |
| **Usage** | Storing textual information, code, configuration | Storing images, audio, video, executables, custom data structures |
| **Editability** | Easily editable with text editors | Not easily editable; requires specific programs |
| **Metadata** | Typically none | Often contains metadata (headers, magic bytes, etc.) |
| **Storage** | Each character stored as a byte; may take more space for numbers/objects | More compact; stores data in native formats |
| **Line Endings** | Uses special end-of-line characters (e.g., `\n`, `\r\n`) | No line delimiters; data is continuous |
| **End of File** | May use special ASCII character (e.g., 26) to mark end | End determined by file size or structure |

## Metadata

It it defined as "data about data". In binary files it refers to information embedded within the file that describes or provides context about the file's content, structure, or origin.
The metadata is typically stored at a dedicated section of the file, often at the beginning known as header.
It also helps to identify the file format using **magic bytes**.

**Magic bytes** (also known as magic numbers or file signatures) are sequence of specific bytes values located at very beginning of a file. They serve as a unique identifier for the file's format, allowing software and operating systems to recognize the file type regardless of its extension.

---

# FOLDER/DIRECTORY

A folder (also called as directory) is a virtual container in a computer's file system used to organize and store files and other folders (subfolders). Unlike files, folders do not have file extensions and do not directly store data themselves; their size depends on the contents inside them.
A directory can store files, or even, other subdirectories inside them.

## Current Working Directory (cwd)

The current working directory is the directory in a file system that is currently active for a user or a running program. It determines the default location where commands, operations, or programs will look for files and create new ones unless a different path is specified.

Each process or terminal window can have its own current working directory.

---

# PATH

A path is a string of characters that specifies the unique location of a file or directory within a hierarchical file system. It acts as an address that tells the OS how to find and access a particular file or folder.

A path is composed of filenames, directory names (folders) separated by a delimiter, such as a backslash (`\`) in Windows or a forward slash(`/`) in Unix-like systems.

## Types of Paths

There are two types of paths:

1. **Absolute Path:**
    It is a path which starts from root directory and specify the complete location of a file or directory, regardless of the current working directory.
    > [!example]
    > - `C:\mingw64\bin\gcc.exe` (in Windows)
    > - `/usr/bin/gcc` (in Linux)

2. **Relative Path:**
    It is a path which specifies the location of a file or directory, relative to the current working directory.
    > [!example]
    > - `..\file.txt` (in Windows)
    > - `images/photo.png` (in Linux)

> [!info] Special Directory Notations
> - `.` (dot): Refers to the current working directory.
> - `..` (dot dot): Refers to the parent directory of the current working directory.

---

# ENVIRONMENT VARIABLES

Environment variables are named values stored by the operating system or shell that can influence how running processes and applications behave on a computer. They act as dynamic configuration mechanism, allowing you to set parameters—such as file paths, user preferences, or secret keys—outside of your application code.
- Each environment variable has a name (usually uppercase, e.g., `PATH`, `JAVA_HOME`, `API_KEY`) and a value.
- They are defined in different scopes, like system-wide (for all users), per user, or per process/session.

The following are some default environment variables on Windows:

| Variable Name | Description |
| ---- | ---- |
| `USERNAME` | Current user's name |
| `COMPUTERNAME` | Name of the computer |
| `APPDATA` | Path to the application Data folder |
| `OS` | Operating system name (usually `Windows_NT`) |
| `SystemRoot` | Location of the Windows system directory (usually `C:\Windows`) |
| `WINDIR` | Same as `SystemRoot` |
| `PATH` | List of directories where executable programs are located |

---

# USER INTERFACE

User Interfaces (UI) are the means through which people interact with machines, software, of devices. They encompass all the visual, textual, and interactive elements that allow users to input commands, receive feedback, and navigate systems.

## Two Common Type of UI

1. **Graphical User Interface (GUI):**
    A GUI is a type of user interface that allows user to interact with computers and electronic devices through visual elements such as icons, buttons, windows, menus, and pointers.
    They are designed to make interaction intuitive and accessible, even for users with little technical knowledge.

2. **Command Line Interface (CLI):**
    A CLI is a text-based user interface that allows users to interact directly with a computer's operating system or software by typing commands. Unlike GUI, which are visual elements like icons and buttons, a CLI relies solely on text input and output.

---

# KERNEL

A kernel is the core component of a computer's operating system that has complete control over everything in the system. It acts as a bridge between the hardware and software, managing system resources like the CPU, memory, and input/output devices.

# OPERATING SYSTEM VS. KERNEL

| Feature              | Kernel                                                                  | Operating System (OS)                                                                     |
| -------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| **Definition**       | The core component of the OS that manages hardware and system resources | The entire system software that includes the kernel plus utilities, interfaces, and tools |
| **Function**         | Manages CPU, memory, devices, and system calls                          | Provides user interface, runs applications, and coordinates system resources              |
| **User Interaction** | Users don't interact directly with the kernel                           | Users interact with the OS via GUI of CLI (shell).                                        |
| **Components**       | CPU scheduler, memory manager, device manager, system call interface    | Kernel + Shell + File system + GUI/CLI + System apps/utilities                            |
| **Examples**         | Linux kernel, Windows NT kernel, XNU (macOS kernel)                     | Windows 11, Ubuntu, Android, macOS, Linux Mint                                            |

---

# SHELL

A shell is a program that provides an interface between the user and the operating system. It allows users to interact with the system by entering commands.

**Two Main Types of Shells:**

1. **Command-Line Interface (CLI) Shell**
    This is text-based. Users type commands, and the shell executes them.
    - Command Prompt (cmd.exe)
    - PowerShell
    - Bash (Bourne Again SHell)
    - sh (Bourne shell)
    
2. **Graphical Shell**
    Provides a visual interface to the OS, often using windows, icons, menus, etc.
    - Windows Explorer
    - GNOME
    - KDE
    - Plasma

**What a Shell Does:**
- Accepts user input (commands)
- Passes those commands to the operating system to execute
- Displays the output or result of the commands

A shell also manages your environment, including variables, command history, input/output redirection, and piping (sending output of one command as input to another).

Colloquially, when people say "shell", they usually mean the command-line interface shell.

---

# TERMINAL

Originally, a terminal was physical device consisting of a keyboard and a text-only monitor connected to a mainframe or large computer, allowing users to control the computer remotely over wired connections.

<center>
<table>
<tr>
<td style="text-align: center; vertical-align: middle;"><img width="300" src="https://i.redd.it/jqhr6dzw3jez.jpg"></td>
<td style="text-align: center; vertical-align: middle;"><img width="300" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9f/DEC_VT100_terminal_transparent.png/1200px-DEC_VT100_terminal_transparent.png"></td>
</tr>
</table>
</center>

Today, a terminal emulator is a software application that mimics the behavior of those old physical terminals.
I allows user to interact with the operating system using a command-line interface (CLI).
A shell runs inside a terminal.

**The flow goes like this:**

1. You type commands into the terminal (the window or interface).
2. The shell, running inside the terminal, receives those commands.
3. The shell interprets and executes the commands.
4. The output or results are sent back to the terminal, which displays them for you.

**Examples of terminal emulators:**
1. Windows Terminal
2. Kitty
3. GNOME terminal

---

# Command Prompt

The **Command Prompt** (often called **cmd** or **cmd.exe**) is a **Windows application that provides a text-based interface to interact with the operating system** by typing commands. It acts as a **command-line interpreter**, allowing users to execute various commands for file management, system configuration, troubleshooting, and automation without using the graphical user interface (GUI).

%%winget install --id Microsoft.WindowsTerminal --source winget -i%%

## Types of commands in CMD

1. ### Internal Commands

    These commands are built into the command prompt itself. They don't require any external files to run.
    They are stored in memory when CMD starts, offering faster execution, and are always available as long as CMD is running.
    
    > [!example]
    > `cd`,`dir`, `cls`, `copy`, `del`, etc.


2. ### External Commands

    These commands are separate program files (`.exe`, `.com`, `.bat`) stored on disk. CMD launches these files to execute the command. CMD searches for them in `PATH` directories. They require separate files to be present to run.

    > [!example]
    > `ipconfig`, `ping`, `tasklist`, `shutdown`, `gcc`, `g++` etc.


## Flag / Switch

A flag is a keyword usually starting with a `/` in CMD that alters the behavior of a command.

It turns on a specific option or feature of the command.

## Parameters / Argument

A parameter is a value or input you provide to a command — such as a filename, folder name, or number — to tell it what to act on.

## How to Open CMD

- Search `cmd` in Start Menu
- Press `Win + R` and type `cmd` then press `Enter`

##  Wildcards

Wildcards are special characters used to match multiple files or folders based on patterns.

| Wildcard | Meaning                             |
| :------: | ----------------------------------- |
|   `*`    | Matches **zero or more** characters |
|   `?`    | Matches **exactly one** characters  |

# Commands

> [!info]-
> - Commands and switches are **case-insensitive**
> - Use `Tab` for auto-completion
> - Use `↑` and `↓` arrows to navigate command history
> - Commands follow this structure:
>    ```batch
>    command [options] [arguments]
>    ```
> Use `Ctrl + C` to cancel running commands.
> - If a path contains special characters or spaces, then you should enclose it in double quotes.

1. `CD` or `CHDIR` - Change Directory
    Displays the name of or changes the CWD.
    > [!tip] Syntax
    > ```batch
    > CD [path]
    > ```
    - If no path is given then prints the CWD.
    - Use the `/D` switch to change current drive in addition to changing current directory for a drive.
    - You can print the CWD of a drive by typing:
        ```batch
        CD drive:
        ```
        Where, `drive` is the drive letter.
2. `DIR` - List Contents
    Displays a list of files and subdirectories in a directory.
    > [!tip] Syntax
    > ```batch
    > DIR [path]
    > ```
    - If no path is given, lists the content of CWD.
    - You can specify multiple paths separated by spaces to list the contents of all paths.
    - To list hidden files and subdirectories, use the `/A:H` switch.
3. `HELP`
    The `HELP` command displays a list of available commands in the Windows Command Prompt or gives information about a specific command.
    > [!tip] Syntax
    > ```batch
    > HELP [command]
    > ```
    - If no command is specified, displays information about CMD commands.
    - If a command is specified, gives a detailed description and usage of the specified command.
    
    You can also use the following syntax to view help of a given command
    > [!tip] Syntax
    > ```batch
    > COMMAND /?
    > ```
4. `CLS`
    Clears the screen.
    > [!tip] Syntax
    > ```batch
    > CLS
    > ```
5. `EXIT`
    Quits the CMD.exe (command interpreter) or the current batch script.
    > [!tip] Syntax
    > ```batch
    > EXIT
    > ```
6. `MD` or `MKDIR` - Make Directory
    Creates a directory.
    
    > [!tip] Syntax
    > ```batch
    > MKDIR [path][directory_name]
    > ```
    
    - If only directory name is given, then creates a new directory with the given name.
    - If path is also given, then creates a new directory with the given name in the given path.
    - You can create multiple folders by separating each with a space.
    
    > [!info] Note
    > `MKDIR` creates any intermediate directories in the path, if needed.
7. `RD` or `RMDIR` - Remove Directories
    Removes (deletes) a directory.
    
    > [!tip] Syntax
    > ```batch
    > RD [path]
    > ```
    
    - By default,  it removes an empty directory only.
    - To remove a directory tree i.e., the directory including all its content (recursively), use the `/S` switch.
    
8. `COPY` - Copy File(s)
    Copies one or more files to another location.
    > [!tip] Syntax
    > ```batch
    > COPY source [destination]
    > ```
    
    You can combine multiple files while copying using `+`
    > [!tip] Syntax
    > ```batch
    > COPY source1+source2 [destination]
    > ```
9. `XCOPY`
    Copies files and directories, with more control than `COPY`.
    > [!tip] Syntax
    > ```batch
    > XCOPY source [destination]
    > ```
10. `MOVE` - Move File(s)
     Moves files and renames files and directories.
    > [!tip] Syntax
    > ```batch
    > MOVE source [destination]
    > ```
11. `TREE`
    Graphically displays the folder structure of a drive or path.
    > [!tip] Syntax
    > ```batch
    > TREE [path]
    > ```
    
    By default, `TREE` command only displays the name of directories.
    You can use `/F` switch to display file names also.
    
    > [!tip] Syntax
    > ```batch
    > TREE  /F [path]
    > ```
    
12. `REN` or `RENAME`
    Renames a file of files.
    > [!tip] Syntax
    > ```batch
    > RENAME old_name new_name
    > ```
    
13. `ATTRIB`
    Displays or modifies file and folder attributes.
    > [!tip] Syntax
    > ```batch
    > ATTRIB [+R | -R] [+A | -A] [+S | -S] [+H | -H] [path]
    > ```

14. `FIND`
    Searches for a specific text string in files or piped input.
    > [!tip] Syntax
    > ```batch
    > FIND "string" [files]
    > ```

15. `ECHO`
    This command is used to display text or messages in the CMD. It's also commonly used in batch scripts to show status or output values.
    > [!tip] Syntax
    > ```batch
    > ECHO [message]
    > ```
    
    This command also controls whether commands are shown before execution in batch files.
    Typing just `ECHO` will show whether command echoing is currently ON or OFF.
16. `TYPE`
    Displays the contents of a text file or files.
    > [!tip] Syntax
    > ```batch
    > TYPE filename
    > ```
17. `MORE`
    The `more` command is used to **display text one screen at a time**, useful for reading long files or command output.
    > [!tip] Syntax
    > ```batch
    > MORE [files]
    > ```

# Input and Output Redirections

| Operator     | Description                              | Use Case / Behavior                            | Example                                   |
| ------------ | ---------------------------------------- | ---------------------------------------------- | ----------------------------------------- |
| `>`          | Redirect stdout (overwrite file)         | Writes command output to a file                | `DIR > list.txt`                          |
| `>>`         | Append stdout to file                    | Adds command output to the end of a file       | `ECHO done >> log.txt`                    |
| `<`          | Redirect input from file                 | Feeds a file's contents as input to a command  | `SORT < names.txt`                        |
| `2>`         | Redirect stderr to file                  | Sends error messages to a file                 | `DIR missing 2> errors.txt`               |
| `2>&1`       | Redirect stderr to stdout                | Makes stderr follow where stdout is going      | `command > output.txt 2>&1`               |
| <code>&#124</code>          | Pipe stdout to another command's stdin   | Used to chain commands                         | <code>DIR &#124 FIND "file"</code>                       |
| `^>`         | Escape character                         | Outputs a literal `>` in `ECHO`                | `ECHO 2^>1` prints `2>1`                  |

# Some more commands

| Command | Description |
| -- | -- |
| `COLOR` | Sets the default console foreground and background colors |
| `SET` | Displays, sets, or removes cmd environment variables |
| `SETX` | Creates or modifies environment variables in the user or system environment |
| `PATH` | Displays or sets a search path for executable files |
| `PROMPT` | Changes the cmd command prompt |
| `CLIP` | Copies an item to the clipboard |
| `CALC` | Opens Calculator |
| `VER` | Displays the Windows version |
| `REM` | Creates comments |
| `START` | Runs the specified program or command |
| `TIME` | Displays or sets the system time |
| `DATE` | Displays or sets the date |
| `PAUSE` | Suspends processing of a batch program and displays the message<br>`Press and key to continue . . .` |
| `FC` | Compares two files or sets of files and displays the differences between them |
| `TASKLIST` | Displays a list of currently running processes on either a local or remote machine |
| `TASKKILL` | Terminates tasks by process id (PID) or image name |
| `SYSTEMINFO` | Displays operating system configuration information |

## Some Prompts for CMD

### Style 1

```
$E[0;31m$S$E[0;41m$P$E[0;31m$E[0m$S
```

###  Style 2

```
$E[0;103;31m$D$E[93;41m$E[93;41m$S$P$S$E[0;31m$E[0m$S
```

###  Style 3

```
$E[0;96m$S$E[30;106m$P$E[0;96m$E[0m$S
```

###  Style 4

```
╭$E[0;35m$E[0;45m$D$E[0;35m$E[m─$E[0;34m$E[0;44m$P$E[0;34m$E[m$_╰─$G$S
```

###  Style 5

```
$E[0;34m$E[0;44m$S$P$S$E[44;36m$E[0;36m$E[m$S
%%
```