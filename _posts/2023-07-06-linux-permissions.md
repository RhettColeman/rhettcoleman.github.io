---
layout: post
title: Linux Permissions
date: '2023-07-06 09:05:22 -0400'
categories: [Linux]
tags: [linux, permissions]
pin: false
math: true
mermaid: true
---
## Context
Linux permissions are a fundamental aspect of the Linux file system that determine who can perform specific actions on files and directories. They serve to protect sensitive data and maintain system security. Linux uses a permission system based on three levels of access: 

- Read (`r`): Allows the user to view the contents of a file or the names of files within a directory.
- Write (`w`): Grants the user the ability to modify a file or add/remove files within a directory.
- Execute (`x`): Permits the user to execute a file or traverse (enter) a directory.

##  Permission Display
Permissions are represented by a series of ten characters displayed when using the `ls -l` command to list files. The first character represents the file type (e.g., - for a regular file, d for a directory), while the next nine characters are divided into three groups of three. 

Each group corresponds to the permissions for the owner, group, and others, respectively.

Here's an example of the permission display:
```bash
-rw-r--r--  1 owner group  4096 Jul 1 10:00 example.txt
```

In this example, the permissions `-` `rw-` `r--` `r--` indicate the following:

- The file is a a regular file and not a directory (`-`) 
- The owner has read and write permissions (`rw-`).
- The group has read-only permissions (`r--`).
- Others (all users not in the owner or group) have read-only permissions (`r--`).

##  Modify Permissions
To modify permissions, the `chmod` command is used. It allows you to change the permissions for the owner, group, and others using a numeric or symbolic representation.

Numeric representation:
- Read (r): 4
- Write (w): 2
- Execute (x): 1

By summing these values, you can assign the desired permissions. For example:
```bash
chmod 764 example.txt
```
This would set the permissions to `-rwxrw-r--`, granting:
- Owner: read, write, and execute permissions
- Group: read and write permissions
- Others: read-only permissions

## Breakdown 
`chmod 764`

Result: `-rwxrw-r--`

|  User | Read | + Write  | + Execute  | = Total |
|:------|:----:|:-----:|:-------:|:-------:|
| Owner | 4    | 2     | 1 | 7 |
| Group | 4    | 2     | 0 | 6 |
| Other | 4    | 0     | 0 | 4 |

## Another Example 
`chmod 777` - Grant all access to everyone.

Result: `-rwxrwxrwx`

|  User | Read | + Write | + Execute |= Total |
|:------|:----:|:-----:|:-------:|:-------:|
| Owner | 4    | 2     | 1 | 7 |
| Group | 4    | 2     | 1 | 7 |
| Other | 4    | 2     | 1 | 7 |

## Another Example 
`chmod 600` - Grant read and write to owner

Result: `-rw-------`

|  User | Read | + Write | + Execute |= Total |
|:------|:----:|:-----:|:-------:|:-------:|
| Owner | 4    | 2     | 0 | 6 |
| Group | 0    | 0     | 0 | 0 |
| Other | 0    | 0     | 0 | 0 |

