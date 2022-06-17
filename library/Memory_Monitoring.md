# Memory Monitoring

### vmstat
Report information about processes, paging, block IO, traps and CPU activity. 
Files related: `/proc/meminfo, /proc/stat, /proc/*/stat`

Dict:

1. procs

    r: The number of processes waiting for run time.
    b: The number of processes in uninterruptible sleep.

 
2. memory

    swpd: the amount of virtual memory used.
    free: the amount of idle memory.
    buff: the amount of memory used as buffers.
    cache: the amount of memory used as cache.
    inact: the amount of inactive memory. (-a option)
    active: the amount of active memory. (-a option)

 
3. swap

    si: Amount of memory swapped in from disk (/s).
    so: Amount of memory swapped to disk (/s).

 
4. io

    bi: Blocks received from a block device (blocks/s).
    bo: Blocks sent to a block device (blocks/s).

 
5. system

    in: The number of interrupts per second, including the clock.
    cs: The number of context switches per second.

 
6. cpu

These are percentages of total CPU time.

    us: Time spent running non-kernel code. (user time, including nice time)
    sy: Time spent running kernel code. (system time)
    id: Time spent idle. Prior to Linux 2.5.41, this includes IO-wait time.
    wa: Time spent waiting for IO.
    st: Time stolen from a virtual machine.

Options:

    -a, --active : active/inactive memory
    -f, --forks : number of forks since boot
    -m, --slabs : slabinfo
    -s, --stats : event counter statistics
    -d, --disk : disk statistics
    -t, --timestamp: timestamp


Syntax: `vmstat [options] [delay [count]]`

- Display active and inactive memory
`vmstat -a`

- Display number of forks since boot
`vmstat -f`

- Display slabs unformation
`vmstat -m`

- Display disk statistics
`vmstat -d`

Dict:
Reads

    total: Total reads completed successfully
    merged: grouped reads (resulting in one I/O)
    sectors: Sectors read successfully
    ms: milliseconds spent reading

 

Writes

    total: Total writes completed successfully
    merged: grouped writes (resulting in one I/O)
    sectors: Sectors written successfully
    ms: milliseconds spent writing

 

IO

    cur: I/O in progress
    s: seconds spent for I/O


- Summarize disk statistics
`vmstat -D`

- Display event counter statistics
`vmstat -s`

- Display information of a specific partition
`vmstat -p [partition]`
To list partitions: `lsblk`

- Display wide output
`vmstat -w`


### pmap
Report memory map of a process

Syntax: `pmap [options] [PID...]`

Options:

 -x, --extended              show details
 -X                          show even more details
            WARNING: format changes according to /proc/PID/smaps
 -XX                         show everything the kernel provides
 -c, --read-rc               read the default rc
 -C, --read-rc-from=<file>   read the rc from file
 -n, --create-rc             create new default rc
 -N, --create-rc-to=<file>   create new rc to file
            NOTE: pid arguments are not allowed with -n, -N
 -d, --device                show the device format
 -q, --quiet                 do not display header and footer
 -p, --show-path             show path in the mapping
 -A, --range=<low>[,<high>]  limit results to the given range

 -h, --help     display this help and exit
 -V, --version  output version information and exit

- Show map of a process
`pmap -x [PID]`

### free
Display amount of free and used memory in the system.

Files: `/proc/meminfo`

Syntax: `free [options]`

Dict:

       total:  Total installed memory (MemTotal and SwapTotal in /proc/meminfo)

       used:   Used memory (calculated as total - free - buffers - cache)

       free:   Unused memory (MemFree and SwapFree in /proc/meminfo)

       shared: Memory used (mostly) by tmpfs (Shmem in /proc/meminfo)

       buffers:
              Memory used by kernel buffers (Buffers in /proc/meminfo)

       cache:  Memory used by the page cache and slabs (Cached and SReclaimable in /proc/meminfo)

       buff/cache:
              Sum of buffers and cache

       available:
              Estimation  of  how much memory is available for starting new applications, without swapping. Unlike
              the data provided by the cache or free fields, this field takes into account  page  cache  and  also
              that  not  all reclaimable memory slabs will be reclaimed due to items being in use (MemAvailable in
              /proc/meminfo, available on kernels 3.14, emulated on kernels 2.6.27+, otherwise the same as free)


Options: 

 -b, --bytes         show output in bytes
     --kilo          show output in kilobytes
     --mega          show output in megabytes
     --giga          show output in gigabytes
     --tera          show output in terabytes
     --peta          show output in petabytes
 -k, --kibi          show output in kibibytes
 -m, --mebi          show output in mebibytes
 -g, --gibi          show output in gibibytes
     --tebi          show output in tebibytes
     --pebi          show output in pebibytes
 -h, --human         show human-readable output
     --si            use powers of 1000 not 1024
 -l, --lohi          show detailed low and high memory statistics
 -t, --total         show total for RAM + swap
 -s N, --seconds N   repeat printing every N seconds
 -c N, --count N     repeat printing N times, then exit
 -w, --wide          wide output
