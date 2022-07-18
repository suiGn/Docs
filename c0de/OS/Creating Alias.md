## Creating a Temporary Alias

To create a temporary alias that is valid for the current Terminal session, you will use the following command:

```C
alias your_shorthand=" actual command to be performed"
```

Any command can be associated with an alias. 

The following command will let you **SSH to an IP address** merely by typing in ssh_ip:

```c
alias ssh_ip="ssh root@127.0.0.1"
```

## Creating a Permanent Alias

To edit your .bash_profile file, use the following command:

```c
nano ~/.zshrc
```

This will open **nano command-line text editor**. 

Type in the aliases (one per line) that you wish to save, just as you did when creating a temporary alias.

For example:

```c
alias code="cd ~/Desktop/code"
alias init0="cd ~/Desktop/code/init0"
alias cleaker="cd ~/Desktop/code/apps/cleaker"
alias nstart="npx react-native start"
alias ios="npx react-native run-ios"
```

Save the file and restart your terminal.

Type alias directly into the command line prompt for execution.