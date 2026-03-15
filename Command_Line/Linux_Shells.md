CLI (Command Line Interface)

GUI (Graphical User Interface)

Shell

- Facilitator between the user and the OS

Bash (Bourne Again Shell)

- Common default linux shell

Linux Shell Types

- View with ‘echo $SHELL’

View all installed Shells

- ‘cat /etc/shells’

Switch between shells

- Type the shell name requested  
- ex) If ‘/etc/shells’ has ‘/usr/bin/zsh’  
  - Enter ‘zsh’ into shell to switch to it  
  - Can also run command ‘chsh \-s /usr/bin/zsh’

Shell Types

- Bash (Bourne Again Shell)  
  - Default shell for most Linux distributions  
  - Scripting capabilities  
  - Tab completion feature  
  - History file and logs all of your commands (‘history’ command)  
- Fish (Friendly Interactive Shell)  
  - Focuses more on user-friendliness  
- Zsh (Z Shell)  
  - Modern shell that combines the functionalities of some previous shells

Shell script

- Set of commands  
- To execute all commands, you will only execute the script  
- File extension ‘.sh’  
- File shebang ‘\#\!/bin/bash’

Shell Variables

- ‘read \_\_var\_\_’, read takes input for the variable \_\_var\_\_  
- ‘echo "$name"’ to print the var

Run Script

- ‘chmod \+x first\_script.sh’  
- ‘./first\_script.sh’

Loops

- \#\!/bin/bash  
  for i in {1..10};  
  do  
  echo $i  
  done

Conditional Statements

- \#\!/bin/bash  
  read name  
  if \[ "$name" \= "Stewart" \]; then  
          echo "Welcome Stewart\! Here is the secret: THM\_Script"  
  else  
          echo "Sorry\! You are not authorized to access the secret."  
  fi
