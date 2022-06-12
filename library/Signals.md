# Signals

### kill
A PID of -1 is special; it indicates all processes except the kill process itself and init.

Syntax: `kill [options] <pid> [...]`

       <pid> [...]
              Send signal to every <pid> listed.

       -<signal>
       -s <signal>
       --signal <signal>
              Specify the signal to be sent.  The signal can be specified by using name or number.  The behavior of signals is explained in signal(7) manual page.

       -l, --list [signal]
              List signal names.  This option has optional argument, which will convert signal number to signal name, or other way round.

       -L, --table
              List signal names in a nice table.


- List all signals
`kill -l or kill -L`
!(kill_-l)[https://github.com/igcodinap/Linux-Essentials/blob/master/public/img/signals/kill_-l.png]
- Kill a process
`kill [pid]`
!(kill_pid)[https://github.com/igcodinap/Linux-Essentials/blob/master/public/img/signals/kill_pid.png]