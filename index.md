### Some useful linux commands to understand the shell scripts in better aspect

* Limit the number of characters to be entered by the user
```bash
read -n1 -p "Do you wish to continue (y/N) ?"
```

* Shell provides an option to hide text when the user enters any sensitive information
```bash
read -s -p "What's your passcode ?" passcode
```

* To check the passcode later
```shell
echo $passcode
```

* Check if a particular directory exists or not using a full command
```bash
test -d $HOME
echo $?
```

* Or we can achieve the same using a short hand notation
```bash
[ -d $HOME ]
echo $?
```

* This is known as Extended short hand, basically this command is used if there's any extra spaces between the commands
```bash
[[ -d $HOME ]]
echo $?
```

* Some more examples of `test` command
```bash
test 9 -gt 5 && echo "True" || echo "False"
```

* '-gt' stands for greater than

* Which can be further explained and executed seperately in cli as well

```bash
test 9 -gt 5            # this command will satisfy this statement ( && ) i.e., "True"
echo $?
```

```bash
test 9 -gt 29           # this command will satisfy this statement ( || ) i.e., "False"
echo $?
```

* The test command returns an exit status which is used by shell to determine whether the condition was true or false. In the above cases, if `echo $?` returns the output as '0' means true/success and if the output as '1' then it's false/failure

* However, we can interchange the 'True/False' positions according to our requirements

* Short hand version

```bash
[ 9 -gt 5 ] && echo "True" || echo "False"
```

```bash
[ 9 -gt 29 ] && echo "True" || echo "False"
```

* Same can be achieved for checking if a file exists or not
```bash
test -f ./sample.txt
echo $?
```

* OR a short hand notation
```bash
[ -f ./sample.txt ]
echo $?
```

* Extended short hand example
```bash
[[ -f ./sample.txt ]]
echo $?
```

* Some more examples of `test` command
* This will return 0 if the script is found, otherwise it returns 1
```bash
test -f ./scripts/script1.sh 
echo $?
```

* Instead of using `echo $?` all the time manually, we can use ```&& echo "True" || echo "False"```

```bash
[ -f ./scripts/script2.sh ] && echo "File exists" || echo "File doesnot exists"
```

* OR

```bash
[ -f ./scripts/script1.sh ] && echo "File Found" || echo "File not Found"
```

_NOTES:_

1. Use `:` instead of `/bin/bash` for simple scripting. It is more portable as it doesn’t require bash to be present
2. We can use the output of one command as an input to another command by using backticks ``
3. We can use `-z` to check if string is empty, `-n` to check if string is non-empty
4. `[[]]` is used for arithmetic comparison and also for testing conditions in scripts</s>
5. We can also perform string comparison, file existence checks etc with test command
6. The exit status of any command (including test) is stored in `$?`. If the last executed command was successful then it's value


### References ~

_**[Advanced Bash-Scripting Guide](https://tldp.org/LDP/abs/html/exitcodes.html){:target="_blank"}**_