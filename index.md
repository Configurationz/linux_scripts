### Some useful linux commands to understand the shell scripts in better aspect

* Limit the number of characters to be entered by the user
```
read -n1 -p "Do you wish to continue (y/N) ?"
```

* Shell provides an option to hide text when the user enters any sensitive information
```
read -s -p "What's your passcode ?" passcode
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
test 5 -gt 3 && echo "True" || echo "False"
```

* Which can also be explained as 
```
test 5 -gt 3
echo $? # ( && )
```

* OR ( || )
```
test 5 -gt 29
echo $?
```

* Short hand version
```
[ 5 -gt 3 ]
echo $?
```
```
[ 5 -gt 29 ]
echo $?
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
```
test -f ./scripts/script1.sh 
echo $?
```
```
[ -f ./scripts/script2.sh ] && echo "File exists" || echo "File doesnot exists"

```
* OR
```
[ -f ./scripts/script1.sh ] && echo "File Found" || echo "File not Found"
```

_NOTE:_ We can use the output of one command as an input to another command by using backticks