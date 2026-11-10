Linux File Permissions Management

## Project Overview

This project demonstrates how Linux command-line tools can be used to inspect and manage file and directory permissions.

The scenario involved a research team that needed to review access permissions within a projects directory. Some files and directories had permissions that did not match the organisation’s security requirements.

Using Linux commands, I inspected existing permissions, identified excessive access privileges and modified permissions to follow the principle of least privilege.

## Objectives

* Inspect file and directory permissions using ls -la.
* Understand Linux permission types: read, write and execute.
* Identify permissions assigned to users, groups and others.
* Modify file permissions using chmod.
* Restrict access to hidden files and directories.
* Apply the principle of least privilege to improve security.

## Tools and Commands Used

* Linux command-line interface (CLI)
* ls -la
* chmod
* Linux file permission notation

## Understanding Linux File Permissions

Linux uses file permissions to control who can access files and directories and what actions they can perform.

There are three main permission types:

* Read (r): Allows a user to view the contents of a file or list the contents of a directory.
* Write (w): Allows a user to modify a file or create, delete and rename entries within a directory.
* Execute (x): Allows a user to run an executable file or access a directory.

Permissions are assigned to three categories:

* User (u): The owner of the file or directory.
* Group (g): Users who belong to the file’s assigned group.
* Other (o): All other users on the system.

Linux displays permissions as a 10-character string. For example:

-rw-rw-r--

The first character identifies the file type. The remaining nine characters represent read, write and execute permissions for the user, group and others respectively.

A hyphen (-) means that a particular permission has not been granted.


## Checking File and Directory Permissions

The first step in the investigation was to identify the existing permissions assigned to files and directories within the projects directory.

I used the following Linux command:

ls -la

This command displays a detailed listing of files and directories, including hidden files.

The output provides information about file permissions, ownership, group membership and file sizes.

By reviewing the results, I was able to identify files and directories with permissions that did not meet the organisation’s security requirements.

This information helped determine which permissions needed to be modified to prevent unauthorised access.


## Changing File Permissions

After reviewing the existing permissions, I identified that the file project_k.txt allowed other users to modify its contents.

The organisation’s security requirements stated that other users should not have write access to this file.

I used the `chmod` command to remove write permissions from other users.

`chmod o-w project_k.txt`

The `o-w` argument removes write permission from the other user category.

I then used `ls -la` to verify that the permissions had been updated successfully.

This demonstrates how Linux file permissions can be modified to restrict unauthorised access and enforce the principle of least privilege.


## Changing permissions on a hidden file

The organisation had archived a hidden file named .project_x.txt. The requirement was to remove write permissions from both the user and group while ensuring that the group retained read access.

I used the following Linux commands:

chmod u-w,g-w,g+r .project_x.txt

The u-w argument removes write permission from the user, while g-w removes write permission from the group. The g+r argument ensures that the group has read permission.

I then used ls -la to verify that the changes had been applied successfully.

This demonstrates how Linux permissions can be adjusted to protect hidden files and ensure that users only have the access required for their role.

## Changing Directory Permissions

The organisation required that only the researcher2 user should have execute permissions for the drafts directory. The group and other users should not have execute access.

I used the following Linux command to remove execute permissions from the group:

chmod g-x drafts

I then used ls -la to review the updated permissions.

The g-x argument removes execute permission from the group while leaving the user’s existing permissions unchanged.

This demonstrates how Linux directory permissions can be restricted to prevent unauthorised users from accessing directory contents and helps enforce the principle of least privilege.

## Summary

This project demonstrates how Linux commands can be used to inspect and manage file and directory permissions.

I used `ls -la` to review existing permissions and `chmod` to make changes based on the organisation's security requirements.

These tasks reinforced the importance of the principle of least privilege by ensuring users only have the access required for their roles.

Managing file permissions correctly helps protect sensitive information, reduce unauthorised access and improve overall system security.