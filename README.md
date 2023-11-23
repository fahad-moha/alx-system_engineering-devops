# What we will cover
1. What shell is.
2. Shell navigation.
3. Looking around
4. File manipulation
5. Working with commands
6. Reading man pages


# Loops, conditions and parsing
1. How to create SSH keys:
To create SSH keys, you can follow these steps:
- Open a terminal or command prompt.
- Use the `ssh-keygen` command with appropriate options to generate the keys. For example:
  ````
  ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  ```
  This command generates an RSA key pair with a key size of 4096 bits and associates an email with the key.
- You will be prompted to choose a location to save the keys. Press Enter to accept the default location.
- You will also be prompted to enter a passphrase. Setting a passphrase is optional but recommended for added security.
- After completing the steps, your SSH key pair (a public key and a private key) will be generated and saved in the specified location.

2. Advantage of using `#!/usr/bin/env bash` over `#!/bin/bash`:
Using `#!/usr/bin/env bash` as the shebang line in a script has the advantage of being more portable. It allows the operating system to search for the `bash` interpreter in the directories listed in the `PATH` environment variable. This ensures that the script can find the appropriate `bash` interpreter regardless of its location on different systems.

On the other hand, using `#!/bin/bash` explicitly specifies the absolute path to the `bash` interpreter. This assumes that `bash` is installed in the specified location, which may not be the case on all systems. Therefore, using `#!/usr/bin/env bash` is generally considered more flexible and preferred.

3. How to use while, until, and for loops:
- **while loop**: It repeatedly executes a block of code as long as a specified condition is true.
  ````bash
  while condition
  do
    # Code to be executed
  done
  ```

- **until loop**: It repeatedly executes a block of code until a specified condition becomes true.
  ````bash
  until condition
  do
    # Code to be executed
  done
  ```

- **for loop**: It iterates over a sequence of values and executes a block of code for each value.
  ````bash
  for variable in sequence
  do
    # Code to be executed
  done
  ```

4. How to use if, else, elif, and case condition statements:
- **if statement**: It executes a block of code if a specified condition is true.
  ````bash
  if condition
  then
    # Code to be executed if condition is true
  fi
  ```

- **if-else statement**: It executes one block of code if a condition is true and another block of code if the condition is false.
  ````bash
  if condition
  then
    # Code to be executed if condition is true
  else
    # Code to be executed if condition is false
  fi
  ```

- **if-elif-else statement**: It allows for multiple conditions to be checked and different blocks of code to be executed based on the first condition that evaluates to true.
  ````bash
  if condition1
  then
    # Code to be executed if condition1 is true
  elif condition2
  then
    # Code to be executed if condition2 is true
  else
    # Code to be executed if all conditions are false
  fi
  ```

- **case statement**: It provides a way to perform different actions based on the value of a variable or expression.
  ````bash
  case expression in
    pattern1)
      # Code to be executed if expression matches pattern1
      ;;
    pattern2)
      # Code to be executed if expression matches pattern2
      ;;
    pattern3)
      # Code to be executed if expression matches pattern3
      ;;
    *)
      # Code to be executed if expression doesn't match any pattern
      ;;
  esac
  ```

5. How to use the `cut` command:
The `cut` command is used to extract specific sections or columns from lines of input. Here's the basic syntax:
```bash
cut OPTIONS FILE
```
Some commonly used options for the `cut` command include:
- `-c N-M`: Select a range of characters from N to M.
- `-f N`: Select the Nth field (column) using a delimiter (default delimiter is tab).
- `-d DELIMITER`: Specify a custom delimiter to separate fields.

Examples:
- Extract characters 3 to 7 from each line of a file:
  ````bash
  cut -c 3-7 file.txt
  ```

- Extract the first field (column) from a file using a comma as the delimiter:
  ````bash
  cut -f 1 -d ',' file.csv
  ```

6. File and other comparison operators, and how to use them:
File comparison operators are used to compare files or check their properties. Some commonlyused file comparison operators in Bash include:

- `-e FILE`: Checks if FILE exists.
- `-f FILE`: Checks if FILE exists and is a regular file.
- `-d FILE`: Checks if FILE exists and is a directory.
- `-r FILE`: Checks if FILE exists and is readable.
- `-w FILE`: Checks if FILE exists and is writable.
- `-x FILE`: Checks if FILE exists and is executable.

Other comparison operators used in Bash include:

- `-eq`: Equal to.
- `-ne`: Not equal to.
- `-lt`: Less than.
- `-gt`: Greater than.
- `-le`: Less than or equal to.
- `-ge`: Greater than or equal to.

Here's an example of how to use these operators in an `if` statement:

```bash
filename="myfile.txt"

if [ -e "$filename" ]; then
  echo "File exists."
else
  echo "File does not exist."
fi
```

In this example, the `-e` operator is used to check if the file `"myfile.txt"` exists. The result is then used in the `if` statement to perform different actions based on the condition.

# Shellcheck
Shellcheck
Shellcheck is a tool that will help you write proper Bash scripts. It will make recommendations on your syntax and semantics and provide advice on edge cases that you might not have thought about. Shellcheck is your friend! All your Bash scripts must pass Shellcheck without any error or you will not get any points on the task.

Shellcheck is available on the school’s computers. If you want to use it on your own computer, here is how to install it.

Examples:

Not passing Shellcheck:



Passing Shellcheck:



For every feedback, Shellcheck will provide a code that you can use to get more information about the issue, for example for code SC2034, you can browse https://github.com/koalaman/shellcheck/wiki/SC2034.
