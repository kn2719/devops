# Implementing and Executing Bash Scripting

1. pwd Command

The pwd command is used to display the location of the current working directory.

Syntax:

pwd  

2. mkdir Command

The mkdir command is used to create a new directory under any directory.

Syntax:

mkdir <directory name>  

3. rmdir Command

The rmdir command is used to delete a directory.

Syntax:

rmdir <directory name>  

4. ls Command

The ls command is used to display a list of content of a directory.

Syntax:

ls  

5. cd Command

The cd command is used to change the current directory.

Syntax:

cd <directory name>  

6. touch Command

The touch command is used to create empty files. We can create multiple empty files by executing it once.

Syntax:

touch <file name>  

7. cat Command

The cat command is a multi-purpose utility in the Linux system. It can be used to create a file, display content of the file, copy the content of one file to another file, and more.

Syntax:

cat [OPTION]... [FILE]..  
cat <file name>  

8. rm Command

The rm command is used to remove a file.

Syntax:

rm <file name>

9. cp Command

The cp command is used to copy a file or directory.

Syntax:

To copy in the same directory:

cp <existing file name> <new file name>  

10. mv Command

The mv command is used to move a file or a directory form one location to another location.

Syntax:

mv <file name> <directory path> 

11. rename Command

The rename command is used to rename files. It is useful for renaming a large group of files.

Syntax:

rename 's/old-name/new-name/' files  
For example, to convert all the text files into pdf files, execute the below command:

rename 's/\.txt$/\.pdf/' *.txt  

13. tail Command

The tail command is similar to the head command. The difference between both commands is that it displays the last ten lines of the file content. It is useful for reading the error message.

Syntax:

tail <file name>  

### Program 1: Printing Hello World

```bash

#!/bin/bash
echo "Hello World"

```

### Program 2: Bash script to calculate the factorial of a number

```bash

#!/bin/bash

# Read the number from user input
read -p "Enter a number: " number

# Initialize the factorial variable to 1
factorial=1

# Calculate the factorial
for (( i=1; i<=$number; i++ ))
do
  factorial=$((factorial * i))
done

# Print the result
echo "The factorial of $number is $factorial"

```

### Program 3: Bash script to check if a string is a palindrome

```bash

#!/bin/bash

# Read the string from user input
read -p "Enter a string: " string

# Reverse the string
reverse=$(echo "$string" | rev)

# Compare the original string with the reversed string
if [ "$string" = "$reverse" ]; then
  echo "The string is a palindrome"
else
  echo "The string is not a palindrome"
fi

```

