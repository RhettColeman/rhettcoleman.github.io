---
title: "Basic Useful Linux Shortcuts and Commands"
date: 2023-07-05 11:00:00 -05:00
categories: [Linux]
tags: [Linux,Terminal]
pin: true
math: true
mermaid: true
---
# Use the following in a Linux Terminal
example:
> root@linux1:~$ `whoami`
{: .prompt-info }

## Connection
### SSH
The syntax to use SSH is very simple. We only need to provide two things:
1. The IP address of the remote machine
2. Correct credentials to a valid account to login with on the remote machine

```bash
ssh username@MACHINE_IP
```

## Users

|  Command                     | Description        | Syntax  |
|:-----------------------------|:-------------------|--------------:|
| whoami | Confirm Current User    | whoami |
| su | Switch Current User    | su username |


## Directories
### Directory Navigation

|  Command                     | Description        | Syntax |
|:-----------------------------|:-------------------|--------------:|
| cd directory| Change directory to named directory    | cd location |
| find       | Search for files and directories in a specified location or directory hierarchy    | Below |

find - Search for files and directories in a specified location or directory hierarchy
```bash
find -name filename.txt
```

### Directory Contents

|  Command                     | Description           | Syntax|
|:-----------------------------|:-----------------|-:|
| pwd    | Print the current working directory     | pwd  |
|ls      | List files and directories in the current directory   | ls  |
|ls --help | List the possible options that the command accepts   | ls --help |
|man ls | Provide the manual for ls   | man ls |
| ls -a  | List all files and directories, including hidden ones| ls -a  |
| ls -lh | List files and directories in long format with readable file sizes | ls -lh  |
| cat | Display the contents of a file | cat filename |
| grep | Search for a pattern in a file | Below |

grep - Search for a pattern in a file
```bash
grep "String to lookup" filename.extension
```
### Directory Commands

|  Command                     | Description           | Syntax |
|:-----------------------------|:-----------------|------:|
|touch   | Create file     | touch filename |
|mkdir   | Create a folder  | mkdir directoryname |
|cp  | Copy a file or folder    | cp filename filename2 |
|mv | Move a file or folder | mv filename2 filename3 |
|rm   | remove     | rm filename |
|file  | Determine the type of a file  | file filename  |

## Permissions

|  Command                     | Description           | Syntax |
|:-----------------------------|:-----------------|------:|
|ls -lh  | List files with permissions    | ls -lh |

Learn more about [**Linux permissions**](https://rhettcoleman.github.io/posts/linux-permissions/).