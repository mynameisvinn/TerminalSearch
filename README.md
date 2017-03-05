# terminal search

## what is this? 
google web search from terminal

## get bash script

```
#!/bin/bash
echo "Searching for : $@"
for term in $@ ; do
    echo "$term"
    search="$search%20$term"
done
    open "http://www.google.com/search?q=$search"
```
[bash script for terminal search](https://stackoverflow.com/questions/35741161/google-search-from-terminal)

## set permissions
shell needs permission to execute script. 
```
$ chmod 755 goog
```
755 gives r/w/e permission. 700 gives r/e permission.
[writing shell scripts](http://linuxcommand.org/wss0010.php)

## updating path

### what is path?
When you type in the name of a command, the system does not search the entire computer to find where the program is located. That would take a long time. You have noticed that you don't usually have to specify a complete path name to the program you want to run, the shell just seems to know.

The shell does know. Here's how: the shell maintains a list of directories where executable files (programs) are kept, and just searches the directories in that list. If it does not find the program after searching each directory in the list, it will issue the famous command not found error message.

you can find this mythical list of directories with `echo $PATH`.

### adding to path
one way to update path is `export PATH=$PATH:directory`, where directory is the name of the directory to be searched.

you could also update .bash_profile with the above command.

best practices is to create a "bin" folder (typically as a subdirectory in home directory) for scripts/programs he personally uses. 