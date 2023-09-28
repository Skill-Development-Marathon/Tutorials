# Bash scripting: Making Your Computer Work for You

Bash scripting is a powerful tool that lets you automate tasks on your computer, making it work for you and saving you time. Whether you want to simplify repetitive chores or delve into the world of programming, bash scripts are a fantastic place to start. In this beginner-friendly guide, we'll introduce you to the basics of bash scripting using simple language and examples.

## **What is Bash?**

Bash stands for "Bourne Again Shell." It's a command-line interface, or CLI, that lets you interact with your computer by typing text-based commands. Bash scripts are essentially a series of these commands bundled together into a file.

### **Getting Started**

**1. Creating Your First Bash Script**

Let's begin by creating a basic script that prints "Hello, World!" when run. Open a text editor, like vim or nano, and enter the following:

```bash
#!/bin/bash
# This is a simple bash script

echo "Hello, World!"
```

Save this file with a **`.sh`** extension, for example, **`hello.sh`**. This script starts with a "shebang" (**`#!/bin/bash`**), which tells the system to use the Bash interpreter to run the script.

**2. Making the Script Executable**

To run this script, you need to make it executable. Open your terminal and navigate to the directory where the script is saved. Use the **`chmod`** command:

```bash
chmod +x hello.sh
```

**3. Running the Script**

Now, you can run the script:

```bash
./hello.sh
```

You should see "Hello, World!" printed in your terminal.

## **Variables and User Input**

**1. Variables**

In bash scripting, variables store data. They can be numbers, text, or any other information you want to work with. Here's an example:

```bash
#!/bin/bash

# Declare a variable
name="Alice"

# Use the variable
echo "Hello, $name!"
```

**2. User Input**

You can also take input from the user using the **`read`** command:

```bash
#!/bin/bash

# Ask for the user's name
echo "What's your name?"
read name

# Use the input
echo "Hello, $name!"
```

Run this script, and it will prompt you for your name, then greet you using your input.

## **Conditional Statements**

Conditional statements let you make decisions in your scripts. For instance, you can check if a file exists before performing an action:

```bash
#!/bin/bash

# Check if a file exists
if [ -e file.txt ]; then
    echo "File exists!"
else
    echo "File doesn't exist."
fi
```

In this script, **`-e`** checks if the file **`file.txt`** exists. If it does, it prints "File exists!"; otherwise, it prints "File doesn't exist."

## **Loops**

Loops allow you to repeat actions multiple times. Here's a simple **`for`** loop that counts from 1 to 5:

```bash

#!/bin/bash

# A simple for loop
for number in {1..5}
do
    echo "Number: $number"
done
```

This script prints the numbers from 1 to 5.

## **Putting It All Together**

Let's create a practical example: a script that renames all **`.txt`** files in a directory to have a **`.bak`** extension:

```bash
#!/bin/bash

# Ask for the directory
echo "Enter the directory path:"
read directory

# Check if the directory exists
if [ -d "$directory" ]; then
    # Loop through .txt files in the directory and rename them
    for file in "$directory"/*.txt
    do
        newname="${file%.txt}.bak"
        mv "$file" "$newname"
        echo "Renamed: $file to $newname"
    done
else
    echo "Directory doesn't exist."
fi
```

This script prompts the user for a directory path, checks if it exists, and if it does, renames all **`.txt`** files within that directory.

## **Conclusion**

Bash scripting is a skill that can simplify your life and introduce you to the world of programming. We've just scratched the surface here; bash offers countless possibilities for automation and customization.

As you continue your journey into bash scripting, don't hesitate to explore documentation, tutorials, and forums. With practice and patience, you'll find yourself automating tasks and creating your own custom solutions in no time. Happy scripting!