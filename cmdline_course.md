---
layout: default
---

![Command-Line Tools](assets/img/img1.png)

# Command-Line Tools Course Summary

This course covered a wide range of topics and techniques including introduction to command line tools, navigating a UNIX system, basic and advanced corpus processing, scripting, installing and running programs and version control.
The following summary of the course is formatted and organized with the help of ChatGPT. In the following sections, you can read a summary of the commands covered during each week with simple examples on how to use them.

## Week 1: Introduction to the Command Line Environments

- **Learned how to use basic commands:**
  - `ls`: Lists the contents of the current directory.
    - Example:
      ```bash
      ls -l
      ```
      This command lists files and directories in long format.
  
  - `cd`: Changes the current directory.
    - Example:
      ```bash
      cd /path/to/directory
      ```
      Here, `/path/to/directory` is the directory you want to navigate to.

  - `pwd`: Prints the working directory.
    - Example:
      ```bash
      pwd
      ```
      The function of this command is to display the full path of the current directory.

- **Practiced navigating directories and managing files:**
  - Created a new directory:
    - Example:
      ```bash
      mkdir new_directory
      ```
      The function of this command is to create a directory called `new_directory` in the current directory path.

  - Removed a file:
    - Example:
      ```bash
      rm file.txt
      ```
      This command deletes `file.txt` from the current directory.

- **Learned how to download content from the internet:**
  - Downloaded a file using `wget`:
    - Example:
      ```bash
      wget https://example.com/file.txt
      ```
      The `wget` command is used for downloading files from the internet and the downloded content is placed in the current directory path with its original name.



## Week 2: Navigating a UNIX System

- **Learned commands for file manipulation:**
  - **`cp`**: Copies files or directories.
    - Example:
      ```bash
      cp file.txt /path/to/destination/
      ```
      This command copies `file.txt` to the specified destination directory.

  - **`mv`**: This command can be used for both moving or renaming files or directories.
    - Example:
      ```bash
      mv file.txt /path/to/destination/
      ```
      Here, `file.txt` is moved to the destination directory. If the destination is the same directory but with a new name, this command renames the file.

  - **`rm`**: Removes files.
    - Example:
      ```bash
      rm file.txt
      ```
      The function of this command is to remove `file.txt` from the current directory.

- **Learned how to visit the root directory of the system:**
  - Example:
    ```bash
    cd /
    ```
    The function of this command is to take the user to the root directory (`/`), irrespective of the user's current directory. The root directory is the top-level directory in the UNIX filesystem.


## Week 3: Basic Corpus Processing

- **Learned the difference between encoding systems:**
  - **ASCII**: A standard method for encoding English characters and it is limited to 128 characters.
  - **UTF-8**: It is a universal encoding system and includes characters from many languages and symbols. It is also compatible with ASCII.

- **Learned how to convert a text file from Latin-1 to UTF-8 encoding:**
  - Example:
    ```bash
    iconv -f ISO-8859-1 -t UTF-8 input.txt -o output.txt
    ```
    The function of the command `iconv` is to convert the file `input.txt` from Latin-1 encoding to UTF-8 encoding, and according to this example, it saves the result as `output.txt`.

- **Learned how to convert Windows text files to UNIX format and vice versa:**
  - **Convert Windows (CRLF) to UNIX (LF):**
    - Example:
      ```bash
      dos2unix windows_file.txt
      ```
      The function of the command `dos2unix` is to convert `windows_file.txt` from Windows format (CRLF line endings) to UNIX format (LF line endings).

  - **Convert UNIX (LF) to Windows (CRLF):**
    - Example:
      ```bash
      unix2dos unix_file.txt
      ```
      The `unix2dos` command converts `unix_file.txt` from UNIX format (LF line endings) to Windows format (CRLF line endings).


## Week 4: Advanced Corpus Processing

- **Learned how to delete lines from a file using `sed`:**
  - Example:
    ```bash
    sed '3d' file.txt
    ```
    The function of this command is to delete the third line from `file.txt`. The `d` command in `sed` is used to delete specified lines.

- **Learned how to find and replace patterns in a file using `sed`:**
  - Example:
    ```bash
    sed 's/old_text/new_text/g' file.txt
    ```
    The function of this command is to find all occurrences of the `old_text` in `file.txt` and replaces them with `new_text`. In this command, the `s` part in the beginning means substitution, and the `g` part in the end makes the replacement global (applies to all matches on each line).

- **Learned how to use regular expressions with `sed`:**
  - Example:
    ```bash
    sed -n '/^pattern/p' file.txt
    ```
    The function of this command is to print only the lines that match the regular expression `^pattern` (lines starting with "pattern") from `file.txt`. The `-n` argument suppresses automatic printing, and `p` indicates `sed` to print only the matching lines.


## Week 5: Scripting and Configuration Files

- **Learned how to write simple scripts:**
  - Example:
    ```bash
    #!/bin/bash
    echo "Hello, World!"
    ```
    This script, saved in a file, e.g. with format like `hello.sh`, prints "Hello, World!" to the terminal. The function of the `#!/bin/bash` part in the beginning is to specify that the script should be executed with the Bash shell.

- **Learned how to access command-line parameters in scripts:**
  - Example:
    ```bash
    #!/bin/bash
    echo "First parameter: $1"
    echo "Second parameter: $2"
    ```
    In this script, `$1` and `$2` indicate the first and second command-line arguments passed to the script. For example, running `./script.sh arg1 arg2` would print `arg1` and `arg2` as the parameters.

- **Learned how to use the `if` statement:**
  - Example:
    ```bash
    #!/bin/bash
    if [ -f "$1" ]; then
      echo "File exists."
    else
      echo "File does not exist."
    fi
    ```
    The function of this script is to check if a file (passed as the first argument) exists. If it does, it prints "File exists." Otherwise, it prints "File does not exist." The function of the `if` statement here is to make decisions based on the file's existence.


## Week 6: Installing and Running Programs

- **Learned how to give commands as the root user, preferably using `sudo`:**
  - Example:
    ```bash
    sudo apt-get update
    ```
    The function of this command is to update the list of available packages on a Debian-based system (e.g., Ubuntu). `sudo` temporarily grants root (administrator) privileges to the user, which is often required for system-level changes.

- **Learned how to install software using `apt-get`:**
  - **Using `apt-get` on Debian-based systems:**
    - Example:
      ```bash
      sudo apt-get install git
      ```
      The function of this command is to install `git` on a Debian-based system (e.g., Ubuntu). The `install` option is used with `apt-get` to add new software.

- **Learned how to install Python packages using `pip`:**
  - Example:
    ```bash
    pip install requests
    ```
    The function of this command is to install the `requests` package, a popular library for making HTTP requests in Python. `pip` is Python’s package installer and is commonly used for adding libraries to Python projects.


## Week 7: Version Control

- **Learned the importance of version control and why we should use it:**
  - As the main benefits, version control helps tracking changes in code, allows collaborative coding, and restores previous versions if needed.

- **Learned how to commit changes to a project to keep track of its development:**
  - Example:
    ```bash
    git commit -m "Initial commit"
    ```
    The function of this command is to save (or "commit") changes to the local repository with a message (`-m`) describing the changes. Here, "Initial commit" is the message, providing context on what this commit represents.

- **Learned how to set up a repository in GitHub:**
  - **Create a new repository locally:**
    - Example:
      ```bash
      git init
      ```
      This command initializes a new Git repository in the current directory. It sets up the stage for all the necessary files and for tracking changes locally.

  - **Push changes to GitHub:**
    - Example:
      ```bash
      git push -u origin master
      ```
      The function of this command is to push the committed changes from the local `master` branch to the `master` branch in the remote GitHub repository. Such possibility can enable others to access and collaborate on the code.


## Week 8: Building Webpages Using GitHub Pages

- **Learned how to install Jekyll:**
  - Example:
    ```bash
    gem install jekyll bundler
    ```
    The function of this command is to installs Jekyll, a static site generator, and Bundler, a Ruby dependency manager. Jekyll is commonly used for creating websites on GitHub Pages.

- **Learned how to use GitHub Pages:**
  - GitHub Pages is a feature provided by GitHub that allows users to host static websites directly from a GitHub repository.

  - **Build and serve the site locally with Jekyll:**
    - Example:
      ```bash
      bundle exec jekyll serve
      ```
      The function of this command is to build the Jekyll site and serves it locally at `http://127.0.0.1:4000`, allowing you to preview changes before pushing to GitHub.


## Summary Table of the Codes

| Week   | Topic                          | Command                                |
|--------|--------------------------------|----------------------------------------|
| 1      | Basic Commands                 | `ls -l`                                |
|        |                                | `cd /path`                             |
|        |                                | `pwd`                                  |
|        |                                | `wget https://example.com/file.txt`     |
| 2      | File Management                | `cp file.txt /path`                    |
|        |                                | `mv file.txt /path`                    |
|        |                                | `rm file.txt`                          |
|        |                                | `cd /`                                 |
|        |                                | `gzip file.txt`                        |
|        |                                | `tar -czvf archive.tar.gz /path`       |
| 3      | Text Processing                | `iconv -f ISO-8859-1 -t UTF-8`         |
|        |                                | `dos2unix file.txt`                    |
|        |                                | `unix2dos file.txt`                    |
| 4      | Advanced Text Processing       | `sed '3d' file.txt`                    |
|        |                                | `sed 's/old/new/g' file.txt`           |
|        |                                | `sed -n '/^pattern/p' file.txt`        |
| 5      | Scripting                      | `#!/bin/bash ... echo "Hello"`         |
|        |                                | `echo $1`                              |
|        |                                | `if [ -f "$1" ]; then ... fi`          |
| 6      | Package Management             | `sudo apt-get update`                  |
|        |                                | `sudo apt-get install git`             |
|        |                                | `brew install git`                     |
|        |                                | `pip install requests`                 |
| 7      | Version Control                | `git commit -m "message"`              |
|        |                                | `git init`                             |
|        |                                | `git remote add origin <url>`          |
|        |                                | `git push -u origin main`              |
| 8      | GitHub Pages & Jekyll          | `gem install jekyll bundler`           |
|        |                                | `bundle exec jekyll serve`             |
|        |                                | `git clone https://github.com/...`      |
|        |                                | `git add .`, `git commit -m "..."`, `git push` |
