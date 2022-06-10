# Processes

### ulimit

### nice
Syntax: `nice [OPTION] [COMMAND [ARG]...] `

- Set and execute process priority: 
`nice -n [nice_value] command`
- Decrease and execute process priority:
`nice -[nice_value] command`
- Increase and execute process priority:
`nice -[-nice_value] command`
### renice
Syntax: `renice [-n] priority [-g|-p|-u] identifier...`

-n, --priority priority
            Specify the scheduling priority to be used for the process, process group, or user.  Use of the option  -n
            or --priority is optional, but when used it must be the first argument.

-g, --pgrp
            Interpret the succeeding arguments as process group IDs.

-p, --pid
            Interpret the succeeding arguments as process IDs (the default).

-u, --user
            Interpret the succeeding arguments as usernames or UIDs.

- Change priority of existing process
`sudo renice -n [nice_value] -p [pid]`
- Change priority of processes of a specific group
`sudo renice -n [nice_value] -g [gid]`
- Change priority of processes of a specific user
`sudo renice -n [nice_value] -u [uid]`