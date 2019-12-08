# Desktop-Launcher-Updater (DLU)

Its primary intention is to run, and update linux desktop launchers (.desktop) files.
For example, you want to have a visibility on desktop if some PID is running, some file
does exist, etc.  

**DLU** is however more than mere updater state keeper, it can run arbitrary commands,
it's not particularly oriented  to .desktop files, even though it was the first idea.

## Quick howto (eh, there is nothing much more to say, anyway)

1. copy **DLU** dir somewhere to your convenient path. For me it's ~/bin/updaters/
2. create .desktop file on your desktop (ie. ~/Desktop)
3. set the .desktop file to launch **DLU**, with working directory of **DLU** where you copied it.
4. edit **DLU** to your liking. First ~30 lines of it are suitable for user modification.

> Basically what it does:
> * if you click it, it will start the monitoring loop and changes the icon according to the output of configured
>  command. It will also send notify messages.
> * If you click it later, it will run on_click() function.


 It's very simple script which I created to have a visual control for somehing what was 
 supposed to run.
 

 ### more technicall description
        
* runs in INTERVAL loop, executing COMMAND, which output is considered to be STATE. 
* if STATE changes, .desktop file LANCHERFILE icon is set to ICONS[STATE] 
* if STATE is unknown, ICONS[default] state is loaded
* lupdater is smart enough to not start multiple instances
* lupdater takes optional argument:
       * "exit" - terminates current lupdater instance

