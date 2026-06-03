# File Permissions in Linux

## Project Description

As a security professional, I was responsible for reviewing and managing file permissions for a research team. The goal was to ensure that users only had the level of access required for their roles and to remove unauthorized permissions. Using Linux commands, I examined file and directory permissions and updated them to comply with organizational security policies.

---

## Check File and Directory Details

To view the permissions of all files, including hidden files, I used:

```bash
ls -la
```

This command displays detailed information about files and directories, including ownership and permission settings.

Example output:

```bash
-rw-rw-r-- 1 researcher2 research_team 46 Jun 2 06:29 project_k.txt
-rw-r----- 1 researcher2 research_team 46 Jun 2 06:29 project_m.txt
-rw-rw-r-- 1 researcher2 research_team 46 Jun 2 06:29 project_r.txt
-rw-rw-r-- 1 researcher2 research_team 46 Jun 2 06:29 project_t.txt
-rw-r----- 1 researcher2 research_team 46 Jun 2 06:29 .project_x.txt
drwx--x--- 2 researcher2 research_team 4096 Jun 2 06:29 drafts
```

---

## Describe the Permissions String

Example:

```bash
-rw-rw-r--
```

Explanation:

* Character 1 (`-`) indicates that the item is a regular file.
* Characters 2–4 (`rw-`) represent the owner's permissions: read and write.
* Characters 5–7 (`rw-`) represent the group's permissions: read and write.
* Characters 8–10 (`r--`) represent others' permissions: read only.

This permission string is used by Linux to determine which users can read, write, or execute a file.

---

## Change File Permissions

The organization does not allow others to have write access to files. The file `project_k.txt` had excessive permissions.

Command used:

```bash
chmod o-w project_k.txt
```

This command removes write permission from others.

Result:

```bash
-rw-rw-r-- project_k.txt
```

The file now follows the organization's security policy by preventing unauthorized users from modifying it.

---

## Change File Permissions on a Hidden File

The hidden file `.project_x.txt` should allow only the owner and group to read the file and should not allow anyone to write to it.

Command used:

```bash
chmod u-w,g-w,g+r .project_x.txt
```

Result:

```bash
-r--r----- .project_x.txt
```

This removed write permissions and ensured that the owner and group retained read access.

---

## Change Directory Permissions

Only the owner (`researcher2`) should have access to the `drafts` directory.

Command used:

```bash
chmod g-x drafts
```

Result:

```bash
drwx------ drafts
```

This removed the group's execute permission, preventing other users from accessing the directory and its contents.

---

## Summary

In this activity, I used Linux commands to review and modify file and directory permissions. I examined permissions using `ls -la`, interpreted Linux permission strings, and used `chmod` to remove unauthorized access from files and directories. These changes helped ensure that access controls followed the principle of least privilege and supported organizational security requirements.
