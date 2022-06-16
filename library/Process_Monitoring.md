# Process Monitoring

### ps
Report a snapshot of the current processes

Syntax: `ps [options]`

### pstree
Display a tree of processes

Syntax: `       pstree [-a, --arguments] [-c, --compact-not] [-C, --color attr]
       [-g, --show-pgids] [-h, --highlight-all, -H pid, --high‐
       light-pid pid] [-l, --long] [-n, --numeric-sort]
       [-N, --ns-sort ns] [-p, --show-pids] [-s, --show-parents]
       [-S, --ns-changes] [-t, --thread-names] [-T, --hide-threads]
       [-u, --uid-changes] [-Z, --security-context]
       [-A, --ascii, -G, --vt100, -U, --unicode] [pid, user]
       pstree -V, --version
`

### top
Display Linux processes in real time with an interactive output

Syntax: `top  -hv|-bcEeHiOSs1 -d secs -n max -u|U user -p pids -o field -w [cols]`

Dict:

    PID: It is the task's unique process ID.
    USER: It shows the owner of the tasks.
    PR: It is the priority of a task.
    NI: The nice value of a task. A negative value means higher priority, whereas a positive value means lower priority.
    VIRT: The total amount of virtual memory used by the task.
    RES: The non-swapped physical memory used by a task.
    SHR: The amount of shared memory used by a task.
    S: The process status of a task:
        D = uninterruptible sleep
        I = idle
        R = running
        S = sleeping
        T = stopped by job control signal
        t = stopped by debugger during trace
        Z = zombie
    %CPU: The percentage of CPU usage of a task.
    %MEM: The percentage of memory used by a task.
    TIME+: Total CPU time the task has used since it started.
    COMMAND: The command line which is used to start a task.


- To list processes
`top`

- List processes in non-interactive way
`top -b`

- Set update time
`top -d [#seconds]`

- Set iterations
`top -n [#iteration]`

- Monitor specific processes
`top -p [PID]`

- Processes of a specific user
`top -u [userid | username]`

#### While running commands

- Change bytes representation for Memory and Swap
`
k - kibibytes  -> top shows default in KB
m - mebibytes -> Press E one time
g - gibibytes -> Press E two time
t - tebibytes -> Press E three time
p - pebibytes -> Press E four time
e - exbibytes -> Press E five time
`
- Change memory unit type in task windows --> `e`

- Sort list by memory usage --> `M`

- Sort list by CPU usage --> `P`

- Manage files in output --> `f`

- Supress value 0 --> `0`

- Toggle ALternate Display --> `A`

- Change delay time --> `d`

- List only active tasks --> `i`


### mpstat
Display processor statistics

Syntax: `       mpstat [ -A ] [ --dec={ 0 | 1 | 2 } ] [ -n ] [ -u ] [ -T ] [ -V ] [ -I { keyword[,...] |
       ALL } ] [ -N { node_list | ALL } ] [ -o JSON ] [ -P { cpu_list | ALL } ]  [  interval  [
       count ] ]
` 

- Display processor statistics
`mpstat`

- Display all processors statistics
`mpstat -P [ALL | #of the processor]` 

- Display with time interval N for M iterations
`mpstat [N] [M]`

- Display JSON output
`mpstat -o JSON`