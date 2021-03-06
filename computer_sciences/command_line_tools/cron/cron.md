# cron and crontab
Cron is a daemon program that executes schedure commands. 
Crontab is a program that allows you to edit tables of
scheduled programs that will be lauched by cron.
In order to schedule a new program you need to run
`crontab -e` and edit the table. It is possible to specify 
the user with the option `crontab -u`. To see the actual table
you can use `crontab -l`. Using such comand should output a result like this one:

`#min hour day_month month day_week command
0 11 * * * /Users/peigniersergio/anaconda2/bin/rawdog -wu` 

## Vim and crontab issues
After trying to setup a new schedule for cron, I struggled with the 
following problem: 

+ I first edit the crontab using `crontab -e` 
+ I tried to seed the crontab with `crontab -l` 
+ To my surprise no crontab existed!

In order to solve the problem I needed to:
+ Set up my default editor: modifying the `.bash_profile` and adding `export EDITOR=vim` However I was still getting an error: `crontab: temp file must be edited in place`
+ I also needed to add: `alias crontab="VIM_CRONTAB=true crontab"` : With this command we first create a new variable `VIM_CRONTAB` and set it to `true`and then lauch the `crontab` program.
+ Finnaly I needed to modify the `.vimrc` file:
`if $VIM_CRONTAB == "true"
    set nobackup
    set nowritebackup
endif`
Therefore if this variable exists and is set to true, then no backup of the crantab file is made.

This was explained in [this post](http://drawohara.com/post/6344279/crontab-temp-file-must-be-edited-in-place)

To kill crontab you can use crontab -r
