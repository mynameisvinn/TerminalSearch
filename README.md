# terminal search

## what is this? 
google web search from terminal.

## get the script

```
#!/bin/bash
echo "Searching for : $@"
for term in $@ ; do
    echo "$term"
    search="$search%20$term"
done
    open "http://www.google.com/search?q=$search"
```
for more information, go to [bash script for terminal search](https://stackoverflow.com/questions/35741161/google-search-from-terminal)

## set r/w/e permissions
we need to give shell permission to execute script. 
```
$ chmod 755 goog
```
755 gives r/w/e permission. 700 gives r/e permission. heres a helpful tutorial on permissioning: [writing shell scripts](http://linuxcommand.org/wss0010.php)

## updating path

### what is path?
when you type in the name of a command, bash does not search the entire computer to find the program. how does bash know where to look? it knows because it maintains a list of directories where executables are kept, and just searches the directories in that list. if it does not find the program after searching each directory in the list, it will issue the famous command not found error message.

you can find this mythical list of directories with `echo $PATH`.

### how do i add directories to path?
one way to update path is `export PATH=$PATH:directory`, where directory is the name of the directory to be searched.

you could also update .bash_profile with the above command.

best practices is to create a "bin" folder (typically as a subdirectory in home directory) for scripts/programs he personally uses. 