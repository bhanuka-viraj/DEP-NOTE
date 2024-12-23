
|                                                 |                               |
| ----------------------------------------------- | ----------------------------- |
| how to remove <br>a file from indexing<br>stage | `git rm --cached <file name>` |
- **Remove a Single File:**
    `git rm filename.txt`(removing from both indexing file and working directory)
- **Remove Multiple Files:**
	`git rm file1.txt file2.txt`
- **Remove a File from Index Only:**
    `git rm --cached filename.txt`
- **Force Remove a File:**
    `git rm -f filename.txt`
- **Remove a Directory Recursively:**
    `git rm -r directory/`
  
The `git rm` command is an essential tool for managing files in a Git repository, providing flexibility in removing files from both the working directory and the staging area. It helps maintain a clean and organized repository by ensuring that only relevant files are tracked.

Q What happen if a file is add to the git ignore after it was added to the working directory

A. Still git tracking the file

