## Control Shortcuts

- `ctrl + a`
  - move cursor to the beginning of the line
- `ctrl + e`
  - move cursor to the end of the line
- `ctrl + u`
  - delete (yank) everything before the cursor
- `ctrl + k`
  - delete (yank) everything after the cursor
- `ctrl + y`
  - paste the last thing you deleted from (yank) buffer
- `ctrl + l`
  - clear the terminal
- `ctrl + r`
  - reverse search through history of commands

## Signals

- `ctrl + c`
  - send a SIGINT signal to the current process
  - SIGINT is short for **SIGnal INTerrupt**
  - SIGINT is the signal sent to a process when you press `ctrl + c`
  - `ctrl + c` is the most common way to kill a process
- `ctrl + d`
  - send a SIGQUIT signal to the current process
  - SIGQUIT is short for **SIGnal QUIT**
  - SIGQUIT is the signal sent to a process when you press `ctrl + d`
  - `ctrl + d` is the second most common way to kill a process
  - if you are in a shell, `ctrl + d` will end the shell
- SIGTERM
  - your computer sends this signal to a process to tell it to stop running since it is shutting down
- SIGKILL
  - program assasination (shut down a process immediately)
  - `kill =signalcode= =processcode=`
  - `kill -l`
    - list all the signals
