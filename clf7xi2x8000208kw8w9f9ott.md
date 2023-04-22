---
title: "Shell, I/O Redirection and Filters"
seoTitle: "shell, I/O redirection and filters"
seoDescription: "shell, I/O redirection and filters. shell scripting .pipelines.bash scripting"
datePublished: Tue Mar 14 2023 07:25:15 GMT+0000 (Coordinated Universal Time)
cuid: clf7xi2x8000208kw8w9f9ott
slug: shell-io-redirection-and-filters
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678778654497/a52e29aa-3e31-4824-ae97-f5ba9b2cfdcb.jpeg
tags: bash, shell, shell-scripting, bash-scripting, bash-shell-script

---

### INPUT /OUTPUT REDIRECTION

I/O redirection is like changing the direction of water in a hose. Normally, water comes out of the hose, but if you attach it to a sprinkler, the water comes out in a different direction. Similarly, when a computer program runs, it sends information to the screen for you to see (like water from a hose). But with I/O redirection, you can tell the program to send the information to a file instead of the screen (like attaching the hose to a sprinkler). This is useful because you can save the information to look at later or use it for something else. We can redirect files, devices and even the input of other commands.

**There are three standard I/O streams in a computer program:**

**Standard Input (stdin)** - the stream that accepts input from the user or another program.

**Standard Output (stdout)** - the stream that displays the output of a program or command to the user.

**Standard Error (stderr)** - the stream that displays error messages and diagnostic information to the user.

I/O redirection allows a user to change where these standard streams are directed. For example, you can use the '&gt;' symbol to redirect the standard output of a command to a file.

<mark>N.B When you use '&gt;' the whole file is overwritten but when you use '&gt;&gt; 'you append the information to the file without overwriting it).</mark>

The command below runs the 'ls' command to list the files in the current directory and then redirects the output to a file called 'file.txt'.

`ls > file.txt`

Similarly, the '&lt;' symbol can be used to redirect the standard input of a command from a file. The below command sorts the contents of the 'file.txt' and displays the sorted output to the user.

`sort < file.txt`

We can also write the sorted files into another file. The below command sorts the files in file.txt and then writes the sorted files to sorted\_files.txt.

`sort < file.txt > sorted_files.txt`

### PIPELINES

Pipelines are a way of connecting multiple commands in a computer operating system to perform a series of operations on data. In a pipeline, the output of one command is fed as input to the next command, and so on, until the final output is produced.

Pipelines are represented by the "|" (pipe) symbol in the command line interface. For example, suppose you want to list all the files in a directory and then search for a specific file among those files. You can use a pipeline to connect the "ls" and "grep" commands like this:

`ls | grep myfile`

The above command first runs the "ls" command to list all the files in the current directory and then pipes the output of "ls" to the "grep" command. The "grep" command searches for the word "myfile" in the output of "ls", and displays only the lines that contain that word.

Another example is where the output of the ls command is redirected into less. By using this "| less" trick, we can make any command have scrolling output(use 'q' to quit less).

`ls -l | less`

The most useful and powerful thing we can do with I/O redirection is to connect multiple commands to form pipelines.

**More Examples:**

1. Displays the 10 newest files in the current directory.
    
    `ls -lt | head`
    

"ls -lt" lists all files in the current directory in a long format, sorted by modification time with the newest files first. The "-l" option displays the files in a long format, while the "-t" option sorts the files by modification time.

The vertical bar or pipe symbol (|) takes the output of the "ls -lt" command and passes it as input to the "head" command."head" displays the first 10 lines of the output from the "ls -lt" command. By default, "head" displays the first 10 lines, but you can specify a different number of lines using the "-n" option followed by the number of lines you want to display. For example, "head -n 5" will display the first 5 lines of the output.

1. Displays a list of directories and how much space they consume, sorted from the largest to the smallest.
    
    `du | sort -nr`
    
    i. "du" stands for "disk usage" and it displays the disk space used by files and directories in the current directory and all its subdirectories.
    
    ii. The vertical bar or pipe symbol (|) takes the output of the "du" command and passes it as input to the "sort" command.
    
    iii. "sort" sorts the input it receives, and the "-n" option tells it to sort the lines numerically.
    
    iv. The "-r" option tells "sort" to sort the lines in reverse order, which means the largest values will be displayed first.
    
    v. So, the whole command "du | sort -nr" displays the disk space used by files and directories in the current directory and all its subdirectories, sorted by size in descending order. This command can be useful when you need to find out which files or directories are taking up the most space on your hard drive.
    
2. Displays the total number of files in the current working directory and all of its subdirectories.
    
    `find . -type f -print | wc -l`
    
    i. "find" searches for files and directories that match certain criteria in the current directory and its subdirectories. In this case, the "." means the current directory.
    
    ii. The "-type f" option tells "find" to only search for files, not directories.
    
    iii. The "-print" option tells "find" to print the full path of each file it finds.
    
    iv. The vertical bar or pipe symbol (|) takes the output of the "find" command and passes it as input to the "wc" command.
    
    v. "wc" stands for "word count" and it counts the number of lines, words, and characters in the input it receives.
    
    vi. The "-l" option tells "wc" to only count the number of lines in the input.
    
    So, the whole command "find . -type f -print | wc -l" searches for all files in the current directory and its subdirectories, and then counts the number of files found and displays that number. In other words, this command tells you how many files are in the current directory and its subdirectories.
    

### FILTERS

Filters take standard input and perform an operation upon it and send the results to standard output. In this way, they can be combined to process information in powerful ways. Here are some of the common programs that can act as filters:

1. **sort** =&gt; Sorts standard input and then outputs the sorted result on standard output.
    
    `>> sort < file.txt`
    
    `>> sort states.txt`
    
    `>> sort -r file.txt`
    
    `>> sort < file.txt > sorted_files.txt`
    
2. **uniq** =&gt; Given a sorted stream of data from standard input, it removes duplicate lines of data (i.e., it makes sure that every line is unique)(-u=&gt; unique, -d=&gt; duplicate,-c =&gt;how many times the words are repeated).
    
    <mark>N/B: To use uniq the file must be sorted first.</mark>
    
    `>> sort states | uniq -u`
    
    `>> sort states | uniq -d`
    
    `>> sort states | uniq -c`
    
3. **grep** =&gt; Examines each line of data it receives from standard input and outputs every line that contains a specified pattern of characters.
    
    To display the line number along with the matching pattern add -n.
    
    To display the number of times the pattern exists add -c.
    
    To display only the patterns with no "no" in them you add the -v flag.
    
    <mark>N/B: to make grep case insensitive add this flag =&gt; -i</mark>
    
    `>> grep root /etc/passwd`
    
    `>> grep "no" states`
    
    `>> grep -n "no" states`
    
    `>> grep -c "no" states`
    
    `>> grep -v "no" states`
    
    `>>grep ^A states` *//all states that start with the letter a*
    
    `>>grep $A states` *//all states that end with a letter*
    
4. **fmt** =&gt;Reads text from standard input, then outputs formatted text on standard output.
    
5. **pr** =&gt;Takes text input from standard input and splits the data into pages with page breaks, headers and footers in preparation for printing.
    
6. **head** =&gt;Outputs the first few (10) lines of its input. Useful for getting the header of a file.
    
    `>> head states.txt`
    
    `>> head -n 5 states.txt`
    
7. **tail** =&gt;Outputs the last few (10) lines of its input. Useful for things like getting the most recent entries from a log file.
    
    `>> tail states.txt`
    
    `>> tail -n 6 states.txt`
    
8. [tr](http://8.tr) =&gt;It is used for text transformation. Can be used to perform tasks such as upper/lowercase conversions or changing line termination characters from one type to another (for example, converting DOS text files into Unix-style text files).
    
    `>> echo 'welcome' | tr e o` *//replaces all the e's in welcome with o's*
    
    `>>echo 'welcome' | tr -d o` *//deletes o from welcome*
    
    `>>echo 'welcome' | tr [:lower:] [:upper:]` *//converts welcome from lowercase to uppercase*
    
9. **sed**\=&gt;Stream editor. Can perform more sophisticated text translations than tr.
    
10. **awk**\=&gt;An entire programming language designed for constructing filters. Extremely powerful.
    
11. **rev**\=&gt; This command prints the content in reverse
    
    `>> echo 'paper' | rev`
    

**PERFORMING TASKS WITH PIPELINES**

Printing from the command line. Linux provides a program called lpr that accepts standard input and sends it to the printer. It is often used with pipes and filters. Here are a couple of examples:

1. Example One:
    
    `cat poorly_formatted_report.txt | fmt | pr | lpr`
    
    We use cat to read the file and output it to standard output, which is piped into the standard input of fmt. fmt formats the text into neat paragraphs and outputs it to standard output, which is piped into the standard input of pr. pr splits the text neatly into pages and outputs it to standard output, which is piped into the standard input of lpr. lpr takes its standard input and sends it to the printer.
    
2. Example Two:
    
    `cat unsorted_list_with_dupes.txt | sort | uniq | pr | lpr`
    
    The example starts with an unsorted list of data with duplicate entries. First, the cat sends the list into sort which sorts it and feeds it into uniq which removes any duplicates. Next pr and lpr are used to paginate and print the list.
    
3. Example Three:
    
    You can use the following command to view the contents of tar files on a Linux system. You can recognize these files by their traditional file extensions, ".tar.gz" or ".tgz".
    
    `tar tzvf name_of_file.tar.gz | less`
    

### SPECIAL CHARACTERS

Some characters are evaluated by Bash to have a non-literal meaning. Instead, these characters carry out a special instruction, or have an alternate meaning; they are called "special characters", or "meta-characters".

Here are some of the more common special characters uses:

1. **" "**: Whitespace — this is a tab, newline, vertical tab, form feed, carriage return, or space. Bash uses whitespace to determine where words begin and end. The first word is the command name and additional words become arguments to that command.
    
2. **$**: Expansion — introduces various types of expansion: parameter expansion (e.g. $var or ${var}), command substitution (e.g. $(command)), or arithmetic expansion (e.g. $((expression))). More on expansions later.
    
3. **''**: Single quotes — protect the text inside them so that it has a literal meaning. With them, generally, any kind of interpretation by Bash is ignored: special characters are passed over and multiple words are prevented from being split.
    
4. **""**: Double quotes — protect the text inside them from being split into multiple words or arguments, yet allow substitutions to occur; the meaning of most other special characters is usually prevented.
    
5. **\\**: Escape — (backslash) prevents the next character from being interpreted as a special character. This works outside of quoting, inside double quotes, and is generally ignored in single quotes.
    
6. **'#'**: Comment — the # character begins a commentary that extends to the end of the line. Comments are notes of explanation and are not processed by the shell.
    
7. **\=** :Assignment -- assign a value to a variable (e.g. logdir=/var/log/myprog). Whitespace is not allowed on either side of the = character.
    
8. **\[\[ \]\]**: Test — an evaluation of a conditional expression to determine whether it is "true" or "false". Tests are used in Bash to compare strings, check the existence of a file, etc. More of this will be covered later.
    
9. **!**: Test — an evaluation of a conditional expression to determine whether it is "true" or "false". Tests are used in Bash to compare strings, check the existence of a file, etc. More of this will be covered later.
    
10. **'&gt;', &gt;&gt;, &lt;**: Redirection — redirect a command's output or input to a file. Redirections will be covered later.
    
11. **|**: Pipe — send the output from one command to the input of another command. This is a method of chaining commands together. Example: echo "Hello beautiful." | grep -o beautiful.
    
12. **;** =&gt; Command separator — used to separate multiple commands that are on the same line.
    
13. **{ }**: Inline group — commands inside the curly braces are treated as if they were one command. It is convenient to use these when Bash syntax requires only one command and a function doesn't feel warranted. 14: ( ): Subshell group — similar to the above but where commands within are executed in a subshell (a new process). Used much like a sandbox, if a command causes side effects (like changing variables), it will not affect the current shell.
    
14. **(( ))**: Arithmetic expression — with an arithmetic expression, characters such as +, -, \*, and / are mathematical operators used for calculations. They can be used for variable assignments like (( a = 1 + 4 )) as well as tests like if (( a &lt; b )). More on this later.
    
15. **$(( ))**: Arithmetic expansion — Comparable to the above, but the expression is replaced with the result of its arithmetic evaluation. Example: echo "The average is $(( (a+b)/2 ))".
    
16. ***'\*', ?****: Globs -- "wildcard" characters which match parts of filenames (e.g. ls* .txt).
    
17. **~**: Home directory — the tilde is a representation of a home directory. When alone or followed by a /, it means the current user's home directory; otherwise, a username must be specified (e.g. ls ~/Documents; cp ~john/.bashrc .).
    
18. **&**: Background -- when used at the end of a command, run the command in the background (do not wait for it to complete).
    

### ERRORS

To redirect the error output to the standard output in a command line interface, you can use the "2&gt;&1" operator.

In most Unix-like operating systems, standard output is represented by the number 1 and standard error is represented by the number 2. The "2&gt;&1" operator tells the shell to redirect the standard error to the same place as the standard output.

Here's an example command that redirects the error output to the standard output:

`mycommand 2>&1`

In this example, "mycommand" is the command you want to run, and "2&gt;&1" tells the shell to redirect any error output from "mycommand" to the same place as the standard output. The result is that both standard output and error output are sent to the same place, which can be useful for capturing all output in a log file or for displaying it in the terminal.

### CONTENT EXAMPLES:

1. Write a script that prints “Hello, World”, followed by a new line to the standard output.
    
    `>> echo "Hello, World"`
    
2. Write a script that displays a confused smiley "(Ôo)'.
    
    `>> echo "\"(Ôo)'"`
    
3. Display the content of the /etc/passwd file.
    
    `>> cat /etc/passwd`
    
4. Display the content of /etc/passwd and /etc/hosts
    
    `>> cat /etc/passwd /etc/hosts`
    
    `>> cat /etc/{passwd,hosts}`
    
5. Display the last 10 lines of /etc/passwd.
    
    `>> tail /etc/passwd`
    
    `>> tail -n 10 /etc/passwd`
    
    The above command will display the last 10 lines of the "/etc/passwd" file.
    
    The "-n" option specifies the number of lines to display, and in this case, it is set to 10.
    
    The "tail" command is used to display the last part of a file and is commonly used for viewing log files and other large text files.
    
6. Display the first 10 lines of /etc/passwd.
    
    `>> head /etc/passwd`
    
    `>> head -n 10 /etc/passwd`
    
    To display the first 10 lines of the "/etc/passwd" file, you can use the "head" command with the "-n" option, which tells it to display the first N lines of a file.
    
7. Write a script that displays the third line of the file iacta. The file iacta will be in the working directory.
    
    `>> head -n 3 iacta | tail -n 1`
    
    The "-n 3" option tells "head" to extract the first 3 lines.
    
    The output of the "head" command is then piped (represented by the "|" symbol) to the "tail" command, which extracts the last line from the output.
    
    The "-n 1" option tells "tail" to extract the last line.
    
8. Write a shell script that creates a file named exactly *\\'"Best School"'\\*$?\*\*\*\*\*:) containing the text Best School ending with a new line.
    
    `echo "Best School" > \*\\"'"Best School"\'"\\*$\?\*\*\*\*\*:)`
    
9. Write a script that writes into the file ls\_cwd\_content the result of the command ls -la. If the file ls\_cwd\_content already exists, it should be overwritten. If the file ls\_cwd\_content does not exist, create it.
    
    `>> ls -la > ls_cwd_content`
    
10. Write a script that duplicates the last line of the file iacta. The file iacta will be in the working directory.
    
    `>> tail -n iacta >> iacta`
    
    The first command, "tail -n 1 iacta", gets the last line of the file "iacta" and then appends the line to the end of the "iacta" file.
    
11. Write a script that deletes all the regular files (not the directories) with a .js extension that is present in the current directory and all its subfolders.
    
    `>> find . -type f -name "*.js" -delete`
    
    The "find" command is used to locate files in the current directory (.) and its subfolders (-type f) with a ".js" extension (-name "\*.js").
    
    The "-delete" option is used to delete all the files found by the "find" command.
    
12. Write a script that counts the number of directories and sub-directories in the current directory.
    
    Requirements:
    
    i. The current and parent directories should not be taken into account.
    
    ii. Hidden directories should be [counted.](http://counted.It)
    
    `>> find . -mindepth 1 -type d | wc -l`
    
    The above command uses the find command to recursively search the current directory (.) for all directories (-type d) at a minimum depth of 1 (-mindepth 1), excluding the current directory and the parent directory.
    
    It pipes the output of find to the wc command, which counts the number of lines (-l) in the output.
    
13. Create a script that displays the 10 newest files in the current directory.
    
    Requirements:
    
    i. Sorted from the newest to the oldest.
    
    ii. The solution uses the ls command to list all files in the current directory
    
    `>> ls -t | head`
    
    The above command sorted the list by modification time (newest first) using the -t option.
    
    It then piped the output of ls to the head command, which selects the first 10 lines of the output.
    
14. Create a script that takes a list of words as input and prints only words that appear exactly once.
    
    `>> sort | uniq -u`
    
15. Display lines containing the pattern “root” from the file /etc/passwd.
    
    `>> grep "root" /etc/passwd`
    
    The solution uses the grep command to search for lines containing the pattern "root" in the file /etc/passwd. The output is the lines from /etc/passwd that contain the pattern "root".
    
16. Display the number of lines that contain the pattern “bin” in the file /etc/passwd.
    
    `>>grep "bin" /etc/passwd | wc -l`
    
17. Display lines containing the pattern “root” and 3 lines after them in the file /etc/passwd.
    
    `>> grep -A 3 "root" /etc/passwd`
    
    The solution uses the grep command with the -A option to display not only the matching line but also the three lines that follow it. The pattern "root" is searched in the file /etc/passwd.
    
18. Display all the lines in the file /etc/passwd that do not contain the pattern “bin”.
    
    `>> grep -v "bin" /etc/passwd`
    
    The solution uses the grep command with the -v option to invert the match, which means that it will display all lines that do not contain the pattern "bin".The pattern "bin" is searched in the file /etc/passwd.
    
19. Display all lines of the file /etc/ssh/sshd\_config starting with a letter.
    
    `>> grep "^[[:alpha:]]" /etc/ssh/sshd_config`
    
    The solution uses the grep command with a regular expression pattern to search for lines that start with a letter. The regular expression pattern ^\[\[:alpha:\]\] matches any line that starts with a lowercase or uppercase letter. The search is performed in the file /etc/ssh/sshd\_config.
    
20. Replace all characters A and c from input to Z and e respectively.
    
    `>> tr Ac Ze`
    
21. Create a script that removes all letters c and C from the [input.](http://input.It)
    
    `>> tr -d 'cC'`
    
    The above command uses the tr command with the -d option to delete characters from the input. The first argument to tr specifies the set of characters to be deleted, which in this case are "c" and "C".
    
22. Write a script that reverses its input.
    
    `>> rev`
    
23. Write a script that displays all users and their home directories, sorted by users
    
    `>> cut -d":" --fields=1,6 /etc/passwd | sort`
    
    `cut -d":" --fields=1,6 /etc/passwd`: This command uses the `cut` utility to extract two fields from each line of the `/etc/passwd` file. The `-d":"` option specifies that the fields are separated by colons and the `--fields=1,6` option specifies that only the first and sixth fields should be extracted. The first field is the username, and the sixth field is the user's home directory.
    
    `sort`: This command sorts the output in ascending order (based on the first field, which is the username).
    
24. Write a command that finds all empty files and directories in the current directory and all sub-directories.
    
    Requirements:
    
    i.Only the names of the files and directories should be displayed (not the entire path).
    
    ii. Hidden files should be listed
    
    iii. One file name per line.
    
    iv. The listing should end with a new line.
    
    v. You are not allowed to use basename, grep, egrep, fgrep or rgrep.
    
    `>> find . -empty -printf "%f\n"`
    
    `find . -empty`: This command uses the `find` utility to search for all files with zero size in the current directory and its subdirectories. The `-empty` option specifies that only files with zero size should be considered.
    
    `-printf "%f\n"`: This command specifies that only the filenames (not the full paths) of the matching files should be printed, followed by a newline character.
    
25. Write a script that lists all the files with a .gif extension in the current directory and all its sub-directories.
    
    Requirements:
    
    i. Hidden files should be listed
    
    ii. Only regular files (not directories) should be listed.
    
    iii. The names of the files should be displayed without their extensions.
    
    iv. The files should be sorted by byte values, but case-insensitive (file aaa should be listed before file bbb, file .b should be listed before file a, and file Rona should be listed after file jay).
    
    v. You are not allowed to use basename, grep, egrep, fgrep or rgrep.
    
    `>> find . -type f -name "*.gif" -printf "%f\n"| rev | cut -d '.' -f2- | rev | LC_ALL=C sort -f`
    
    `find . -type f -name "*.gif" -printf "%f\n"`: This command uses the `find` utility to search for all files with a ".gif" extension in the current directory and its subdirectories. The `-type f` option specifies that only regular files should be considered. The `-name "*.gif"` option specifies that only files with a ".gif" extension should be considered. The `-printf "%f\n"` option specifies that only the filenames (not the full paths) of the matching files should be printed, followed by a newline character.
    
    `rev`: This command reverses the order of the characters in each line of the output.
    
    `cut -d '.' -f2-`: This command extracts all characters after the first dot (".") in each line of the output. This effectively removes the ".gif" extension from the filenames.
    
    `rev`: This command reverses the order of the characters in each line of the output again so that the filenames are in their original order.
    
    `LC_ALL=C sort -f`: This command sorts the filenames in alphabetical order, ignoring case. The `LC_ALL=C` option sets the locale to "C", which ensures that the sorting is performed based on the ASCII values of the characters in the filenames, rather than using any locale-specific rules.
    
26. An acrostic is a poem (or other forms of writing) in which the first letter (or syllable, or word) of each line (or paragraph, or other recurring feature in the text) spells out a word, message or the alphabet. The word comes from the French acrostiche from post-classical Latin acrostichis). As a form of constrained writing, an acrostic can be used as a mnemonic device to aid memory retrieval. Create a script that decodes acrostics that use the first letter of each line.
    
    Requirements:
    
    i. The ‘decoded’ message has to end with a new line.
    
    ii. You are not allowed to use grep, egrep, fgrep or rgrep.
    
    `>>echo -ne $(cut -c-1 | tr -d '\n')'\n'`
    
    `cut -c-1`: This command extracts the first character of each line of the input.
    
    `tr -d '\n'`: This command removes all newline characters from the input.
    
    `$(cut -c-1 | tr -d '\n')`: This command is used to generate a string that consists of the first character of each line of the input, concatenated together.
    
    `echo -ne`: This command prints the output string to the console, without adding a newline character at the end.
    
    `'\n'`: This command adds a new line character to the end of the output string so that the next console output starts on a new line.
    
27. Write a script that parses web server logs in TSV format as input and displays the 11 hosts or IP addresses which did the most requests.
    
    i.Order by the number of requests.
    
    ii. The most active host or IP should be at the top.
    
    iii. You are not allowed to use grep, egrep, fgrep or rgrep.
    
    `>> tail -n +2 | cut -f1 | sort | uniq -c | sort -nr | head -11 | tr -s ' ' | cut -d' ' -f3`
    
    `tail -n +2`: This command skips the first line of the input (assuming it's a file), which is typically a header row, and starts reading from the second line.
    
    `cut -f1`: This command extracts the first column (field) from each line of the input. The columns are assumed to be separated by a tab character by default.
    
    `sort`: This command sorts the lines of the input in alphabetical order.
    
    `uniq -c`: This command counts the number of occurrences of each unique line in the input.
    
    `sort -nr`: This command sorts the lines of the input in descending order based on the count obtained in the previous step.
    
    `head -11`: This command selects the first 11 lines of the sorted output.
    
    `tr -s ' '`: This command squeezes consecutive spaces into a single space. This is done to ensure that the output has consistent spacing between the count, the column value, and any extra spaces.
    
    `cut -d' ' -f3`: This command extracts the third column (field) from each line of the output, assuming that the columns are separated by a space character.
    

<iframe height="1" width="1" style="border:none;box-sizing:border-box;--tw-border-spacing-x:0;--tw-border-spacing-y:0;--tw-translate-x:0;--tw-translate-y:0;--tw-rotate:0;--tw-skew-x:0;--tw-skew-y:0;--tw-scale-x:1;--tw-scale-y:1;--tw-pan-x: ;--tw-pan-y: ;--tw-pinch-zoom: ;--tw-scroll-snap-strictness:proximity;--tw-ordinal: ;--tw-slashed-zero: ;--tw-numeric-figure: ;--tw-numeric-spacing: ;--tw-numeric-fraction: ;--tw-ring-inset: ;--tw-ring-offset-width:0px;--tw-ring-offset-color:#fff;--tw-ring-color:rgba(59,130,246,0.5);--tw-ring-offset-shadow:0 0 transparent;--tw-ring-shadow:0 0 transparent;--tw-shadow:0 0 transparent;--tw-shadow-colored:0 0 transparent;--tw-blur: ;--tw-brightness: ;--tw-contrast: ;--tw-grayscale: ;--tw-hue-rotate: ;--tw-invert: ;--tw-saturate: ;--tw-sepia: ;--tw-drop-shadow: ;--tw-backdrop-blur: ;--tw-backdrop-brightness: ;--tw-backdrop-contrast: ;--tw-backdrop-grayscale: ;--tw-backdrop-hue-rotate: ;--tw-backdrop-invert: ;--tw-backdrop-opacity: ;--tw-backdrop-saturate: ;--tw-backdrop-sepia: ;display:block;vertical-align:middle;color:rgb(255, 255, 255);font-family:Söhne, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, Ubuntu, Cantarell, "Noto Sans", sans-serif, "Helvetica Neue", Arial, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";font-size:medium;font-style:normal;font-variant-ligatures:normal;font-variant-caps:normal;font-weight:400;letter-spacing:normal;orphans:2;text-align:start;text-indent:0px;text-transform:none;white-space:normal;widows:2;word-spacing:0px;-webkit-text-stroke-width:0px;text-decoration-thickness:initial;text-decoration-style:initial;text-decoration-color:initial;position:absolute;top:0px;left:0px;visibility:hidden"></iframe>