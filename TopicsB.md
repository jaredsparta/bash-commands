**Wildcards**
- These are used to define some pattern for searching or matching text/string
- Wildcards inclue: `*`, `?` and `[]`
    1. `*` is used to search for certain characters that occur  0 or more times
    2. `?` is used to search for a fixed numer of characters, each `?` indicates each character
    3. `[]` is used to match the characters of a defined range or group of characters

- Examples:
    - `ls *.md` - shows all files that have the extension `.md`
    - `ls *_file.*` - shows all files that contain `_file` in it's name

    - `ls ???.md` - shows all files that have a name 3 characters long and ends with `.md`
    - `ls *.??` - returns any file whose extension is 2 characters long (e.g. `.md`)


**GREP**
- It's used to search for strings/text from a file or from the output of another command
- It returns the lines where it finds a match
- We can also use grep to return the lines where it doesn't match, using `grep -v`

- Examples:
    - `grep "Jared" text.txt` - returns every line that contains `Jared` in the file `text.txt`

    - `grep -i "hello" text.txt` - returns every line that contains `hello` in whatever combination of upper or lowercase letters (e.g. "hellO", "hElLO", "HELLO")

**Streams**
- Every program that runs on the command line automatically has three data streams connected to it
1. `STDIN` - this is the data fed into the program
2. `STDOUT` - data printed by program, will default to terminal
3. `STDERR` - data printed in case of error, will default to terminal

![](images\streams.png)

**Piping**
- Using the character `|` we can feed the the output from the left program as input to the right program

- You can pipe as many times as needed and it follows intuitively

- Examples:
    - `ls | head -n 3` - will output just the first 3 files/directories from the `ls` command (the order will follow the order `ls` lists them)
    - `ls | head -n 3| tail -n 1` - it will output the last item in the list from above

**ps aux**
- `ps` - shows only the processes running under the logged in user from current terminal

- `ps -a` - shows the processes from all users
- `ps -u` - shows the processes alongside the users 
- `ps -x` - shows the processes not attached to the current terminal

**ps aux and grep**
- We can combine these two commands to look for processes that have a specific string/text

- Examples:
    - `ps aux | grep "vagrant"` - returns all the processes that contain `vagrant` in the columns (so will return all processes that have vagrant as a user or vagrant in command)
    - `ps aux | grep 21:00` - returns all processes that contain this time, useful if you want to see processes started at a certain time

**Starting processes and sending to background**
- Usually foreground processes interact with terminal, so when they are executing it stops us from using the command line

- We can solve this by sending processes to the background.
    1. We can make a process to run in the background initially by adding `&` to the end of it
    2. We can stop a process that is running with `<CTRL> + Z` and then type `bg` (background) to start it again but this time in the background

**Finding processes**
- When there are processes being executed in the background, we can type `jobs` in the command line to list all the processes happening in the background

- To find the process id and it's name, we can use `pgrep <text-to-match>`. This will return a list of process id's and the corresponding names that were matched

**Stopping processes**
- To stop a background process from executing, we can use the `kill` command. Type in `jobs` to list all processes with their `jobid` and then type in `kill %<jobid>`

- The `kill` command in general will stop the process given it's process id.

- We can stop processes in general with `pkill` which kills processes based on it's name



- Example:
    - `kill %1` - this will kill the first background process 

