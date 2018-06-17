# Linux cheat sheet
List of some of the common and most helpfull commands

## Common commands
| command             | Description                               |
| ---                 | ---                                       |
| date                | Shows system date                         |
| uptime              | Shows uptime                              |
| whoami              | Shows your username                       |
| w                   | Who is logged in and what they are doing  |
| history             | History of previous commands you have run |

## Common shortcuts
| Command             | Description                                       |
| --------            | -----------------------                           |
| CTRL-c              | Stop current command / Send sigint                |
| CTRL-a              | Same as *home* key, go the beggining of line      |
| CTRL-e              | Same as *end* key, go to the end of line          |
| CTRL-r              | Search history                                    |
| CTRL-U              | Unicode char from unicode hex                     |
| CTRL-u              | Cut from cursor to start of line                  |
| CTRL-k              | Cut from cursor to end of line                    |
| CTRL-y              | Paste the text from the last cut                  |
| ^hello^world        | Run previous command, replacing hello with world  |

| Command             | Description         | Example                                       |
| ---                 | ---                 | ---                                           |
| !!                  | Repeat last command | `sudo !!` When you forgot to use sudo         |

## Directories
| command             | Description                                               |
| ---                 | ---                                                       |
| pwd                 | Shows path to current directory                           |
| mkdir `dir`         | Creates a new directory name dir                          |
| cd `dir`            | Change directory to dir                                   |
| cd ..               | Change to parrent directory / Go up one level             |
| cd ~                | Change to your home directory                             |
| ls                  | List files                                                |
| ls `-lah`           | List files `-l` long `-a` all/hidden `-h` human readable  |

## files
| command                       | Description                                               |
| ---                           | ---                                                       |
| file `file`                   | Type of file                                              |
| touch `file`                  | Creates a empty file named file                           |
| cat `file1` `file2` `filen`   | concatenate files from left to right and prints to output |
| less `file`                   | View the file in paginate format                          |
| less `--follow-name` `+F file`| Follows text appended to the file.                        |
| head `file`                   | Show first 10 lines of file. Use `-n` for specifying number of lines |
| tail `file`                   | Show last 10 lines of file. Use `-n` for specifying number of lines |
| tail `-f` `file`              | Follows text appended to the file.                        |
| grep `pattern` `file`         | Look for a pattern in given files use `-r` for recursive searh of folders.`-v` for a negative match |
| find `dir` `argument`         | Find files matching given arguments. `-name abc` to find files named abc. `-user bob` to find files owned by bob |
| whereis `binary`              | Get the location of a binary in you bin path. |

## Linux system, kernel and distro
| Command             | Description                             |
| --------            | -----------------------                 |
| uname `-a`          | Shows system and kernel version         |
| cat /etc/*-release  | Distro name and version                 |
| lsb_release         | Distro name and version                 |
| cat /proc/version   | Kernel version and gcc version built by |

## Command chaining

### Pipes
<!-- &#124; is a pipe | -->
| command                 | Description                         |
| ---                     | ---                                 |
| cmd1 &#124; cmd2        | stdout of cmd1 to stdin of cmd2     |
| cmd1 &#124;& cmd2       | stderr of cmd1 to stdin of cmd2     |

### Redirections
| command                 | Description                                               |
| ---                     | ---                                                       |
| cmd < `file`            | Use content in a file as input                            |
| cmd <(cmd2)             | Use cmd2 as an input to cmd1                              |
| cmd > `file`            | Writes stdout to file. XXX: Writes over the file content  |
| cmd >> `file`           | Appends stdout to file.                                   |
| cmd > /dev/null         | Discaard data                                             |
| cmd 2> `file`           | Writes stderr to file. XXX: Writes over the file content  |
| cmd 2>&1                | Write stderr to stdout                                    |
| cmd 1>&2                | Write stdout to stderr                                    |
| cmd &> `file`           | Write all output to file                                  |

### Chaining
<!-- &#124; is a pipe | -->
| command                 | Description                                               |
| ---                     | ---                                                       |
| cmd1 ; cmd2             | First run cmd1 then run cmd2                              |
| cmd1 && cmd2            | First run cmd1, if cmd1 is successful then run cmd2       |
| cmd1 &#124;&#124; cmd2  | first rund cmd1, if cmd1 fails then run cmd2              |
| cmd &                   | Run cmd in a subshell/background                          |

## VIM
Some of the common and most usefull shortcuts

| command                 | Description                                               |
| ---                     | ---                                                       |
| :help `keyword`         | Open help for keyword                                     |
| :saveas `file`          | save file as                                              |
| :w                      | write/save the file                                       |
| :w !sudo tee %          | write/save out the current file using sudo, usefull then forgot using sudo opening the file |
| :wq                     | write/save and quit                                       |
| :q                      | quit, fails if their is any changes not saved             |
| :q!                     | force quit                                                |
