### Some useful linux commands to understand the shell scripts in better aspect

* Limit the number of characters to be entered by the user
```
read -n1 -p "Do you wish to continue (y/N) ?"
```

* Shell provides an option to hide text when the user enters any sensitive information
```
read -s -p "What's your passcode ?" passcode
```

* To check the passcode later
```
echo $passcode
```

* Check if a particular directory exists or not using a full command
```
test -d $HOME
echo $?
```

* Or we can use the same command as a short hand notation
```
[ -d $HOME ]
echo $?
```

* This is known as Extended short hand, basically this command is used if there's any extra spaces between the commands
```
[[ -d $HOME ]]
echo $?
```

* Some more examples of `test` command
```
test 9 -gt 5 && echo "True" || echo "False"
```

* The test command returns an exit status which is used by shell to determine whether the condition was true or false. In the above cases, if `echo $?` returns the output as 0 means true/success and if the output as 1 then it's false/failure

* Which can be further explained and executed seperately in cli as well 
```
test 9 -gt 5
echo $?             # this means ( && ) i.e., True
```

```
test 9 -gt 29
echo $?             # this means ( || ) i.e., False
```

* However, we can interchange the 'True/False' positions as well which will also change the result check it out for yourself

* Short hand version
```
[ 9 -gt 5 ] && echo "True" || echo "False"
```

```
[ 9 -gt 29 ] && echo "True" || echo "False"
```

* Same can be achieved for checking if a file exists or not
```
test -f ./sample.txt
echo $?
```

* OR a short hand notation
```
[ -f ./sample.txt ]
echo $?
```

* Extended short hand example
```
[[ -f ./sample.txt ]]
echo $?
```

* Some more examples of `test` command
* This will return 0 if the script is found, otherwise it returns 1
```
test -f ./scripts/script1.sh 
echo $?
```

* Instead of using `echo $?` all the time manually, we can use ```&& echo "True" || echo "False"```

```
[ -f ./scripts/script2.sh ] && echo "File exists" || echo "File doesnot exists"

```
* OR
```
[ -f ./scripts/script1.sh ] && echo "File Found" || echo "File not Found"
```

_NOTES_

1. Use `:` instead of `/bin/bash` for simple scripting. It is more portable as it doesn’t require bash to
2. We can use the output of one command as an input to another command by using backticks
3. We can use `-z` to check if string is empty, `-n` to check if string is non-empty
4. `[[]]` is used for arithmetic comparison and also for testing conditions in scripts</s>
5. We can also perform string comparison, file existence checks etc with test command
