# System Monitoring

### sar
The  sar command writes to standard output the contents of selected cumulative activity counters in the operating system.

Cronjobs configurable at `/etc/cron.d/sysscat`
Reports are saved by default in `/var/log/sysstat`

Syntax: `sar [ -A ] [ -B ] [ -b ] [ -C ] [ -D ] [ -d ] [ -F [ MOUNT ] ] [ -H ] [
       -h ] [ -p ] [ -r [ ALL ] ] [ -S ] [ -t ] [ -u [ ALL ] ] [ -V ] [ -v ] [
       -W  ] [ -w ] [ -y ] [ -z ] [ --dec={ 0 | 1 | 2 } ] [ --dev=dev_list ] [
       --fs=fs_list ] [ --help ] [ --human ] [ --iface=iface_list ] [ --pretty
       ]  [ --sadc ] [ -I { int_list | SUM | ALL } ] [ -P { cpu_list | ALL } ]
       [ -m { keyword[,...] | ALL } ] [ -n { keyword[,...] | ALL } ]  [  -q  [
       keyword[,...] | ALL ] ] [ -j { SID | ID | LABEL | PATH | UUID | ... } ]
       [ -f [ filename ] | -o [ filename ] | -[0-9]+ ] [ -i interval ] [ -s  [
       hh:mm[:ss] ] ] [ -e [ hh:mm[:ss] ] ] [ interval [ count ] ]
`
Simplified Syntax: `sar [option] [interval] [count]`

- Display CPU utilization
`sar -u [ALL]`

- Display CPU utlization for each N seconds
`sar -u [N]`

- Display memory utilization
`sar -r [ALL]`

- Display I/O and transfer rate
`sar -b`

- Display processor statistics
`sar -P [#processor | ALL]`

- Swap Space utilization
`sar -S`

- Memory Swap statistics
`sar -W`

- Mounted Filesystems statistics
`sar -F`

- Network Statistics
`sar -n [keyword | ALL]`

Possible keywords are: `DEV, EDEV, NFS, NFSD, SOCK, IP, EIP, ICMP, EICMP, TCP, ETCP, UDP, SOCK6, IP6, EIP6, ICMP6, EICMP6 and UDP6.`

- Display block devices
`sar -d`

- Display queue length and load averages
`sar -q`

- Display paging statistics
`sar -B`

Dict:
              pgpgin/s
                     Total number of kilobytes the system paged in from disk per second.

              pgpgout/s
                     Total number of kilobytes the system paged out to disk per second.

              fault/s
                     Number  of  page faults (major + minor) made by the system per second.  This is not a count of page faults that generate I/O,
                     because some page faults can be resolved without I/O.

              majflt/s
                     Number of major faults the system has made per second, those which have required loading a memory page from disk.

              pgfree/s
                     Number of pages placed on the free list by the system per second.

              pgscank/s
                     Number of pages scanned by the kswapd daemon per second.

              pgscand/s
                     Number of pages scanned directly per second.

              pgsteal/s
                     Number of pages the system has reclaimed from cache (pagecache and swapcache) per second to satisfy its memory demands.

              %vmeff Calculated as pgsteal / pgscan, this is a metric of the efficiency of page reclaim. If it is near 100% then almost every page
                     coming  off the tail of the inactive list is being reaped. If it gets too low (e.g. less than 30%) then the virtual memory is
                     having some difficulty.  This field is displayed as zero if no pages have been scanned during the interval of time.

- Extract report from file
`sar -f [dir_file]`

- Task creation and system switching
`sar -w`

Dict:
proc/s - Total number of tasks created per second.

cswch/s - Total number of context switches per second.

- Display all statistics
`sar -A` equivalent to `sar -bBdqrRSuvwWy -I SUM -I XALL -n ALL -u ALL -P ALL`

- Power Management statistics
`sar -m [keyword]`

Keywords: 
`
    CPU - CPU instantaneous clock frequency
    FAN - Fans speed
    FREQ - CPU average clock frequency
    IN - Voltage inputs
    TEMP - Devices temperature
    USB - USB devices plugged into the system
`