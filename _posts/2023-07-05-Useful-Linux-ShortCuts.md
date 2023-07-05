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

# Users

|  Command                     | Description        | Syntax Below? |
|:-----------------------------|:-------------------|--------------:|
| whoami | Confirm Current User    | No |


# Directories
## Directory Navigation

|  Command                     | Description        | Syntax Below? |
|:-----------------------------|:-------------------|--------------:|
| cd directory| Change directory to named directory    | No |
| find       | Search for files and directories in a specified location or directory hierarchy    | Yes |

find - Search for files and directories in a specified location or directory hierarchy
```bash
find -name filename.txt
```

## Directory Contents

|  Command                     | Description           | Syntax Below? |
|:-----------------------------|:-----------------|-:|
| pwd    | Print the current working directory     | No |
|ls      | List files and directories in the current directory   | No |
| ls -a  | List all files and directories, including hidden ones| No |
| ls -lh | List files and directories in long format with readable file sizes | No |
| cat filename | List files and directories in long format with readable file sizes | No |
| grep | Search for a pattern in a file | Yes |

grep - Search for a pattern in a file
```bash
grep "String to lookup" filename.extension
```


## Directory Commands