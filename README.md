# Show git branch in at the prompt
Show the name of the branch you are in at the prompt

1. Open your terminal

2. Edit the .bashrc file

```
user@mypc:~$ vim ~/.bashrc
```

3. At the end of the file add the following lines:

```
show_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
export PS1="\u@\h:\[\033[32m\]\w\[\033[36m\]\$(show_git_branch)\[\033[00m\]$ "
```


4. Save the file

5. Redirect to a directory where you have a repository and you will see the changes

```
user@mypc:~$ cd apps/show_git_branch
user@mypc:~/apps/show_git_branch (main)$ 
```
