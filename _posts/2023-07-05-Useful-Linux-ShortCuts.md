---
title: "Basic Linux Shortcuts and Commands"
date: 2023-07-05 11:00:00 -05:00
categories: [Linux]
tags: [linux,terminal]
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
| cd | Change directory to named directory    | cd /dir1/dir2 |
| cd .. | Go up a directory    | cd .. |
| cd / | Go to home directory    | cd / |
| cd /var/log       | Access system logs    | cd /var/log  |
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
| clear | clear all terminal text | clear |
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

## Terminal Text Editors

|  Command                     | Description           | Syntax |
|:-----------------------------|:-----------------|------:|
|nano   | create (new filename) or edit (filename) a file using nano | nano filename |
|VIM   | create (new filename) or edit (filename) a file using VIM | VIM filename |

## Viewing Processes

|  Command                     | Description           | Syntax |
|:-----------------------------|:-----------------|------:|
|ps   | Provide a list of the running processes as our user's session | ps |
|ps aux   | See system processes and other user tasks | ps aux  |
|top  | Real-time statistics system processes | ps aux  |
|kill  | Kill a command with associated PID  | kill 0123  |
