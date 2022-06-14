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

Dict:

              tps    Total number of transfers per second that were issued to physical devices.  A transfer is an I/O request to  a  physical  de‐
                     vice.  Multiple  logical  requests  can  be combined into a single I/O request to the device.  A transfer is of indeterminate
                     size.

              rtps   Total number of read requests per second issued to physical devices.

              wtps   Total number of write requests per second issued to physical devices.

              dtps   Total number of discard requests per second issued to physical devices.

              bread/s
                     Total amount of data read from the devices in blocks per second.  Blocks are equivalent to sectors and therefore have a  size
                     of 512 bytes.

              bwrtn/s
                     Total amount of data written to devices in blocks per second.

              bdscd/s
                     Total amount of data discarded for devices in blocks per second.


- Display processor statistics
`sar -P [#processor | ALL]`

- Swap Space utilization
`sar -S`

Dict:

              kbswpfree
                     Amount of free swap space in kilobytes.

              kbswpused
                     Amount of used swap space in kilobytes.

              %swpused
                     Percentage of used swap space.

              kbswpcad
                     Amount of cached swap memory in kilobytes.  This is memory that once was swapped out, is swapped back in but still also is in
                     the swap area (if memory is needed it doesn't need to be swapped out again because it is already in the swap area. This saves
                     I/O).

              %swpcad
                     Percentage of cached swap memory in relation to the amount of used swap space.


- Memory Swap statistics
`sar -W`

- Mounted Filesystems statistics
`sar -F`
Dict:

              MBfsfree
                     Total amount of free space in megabytes (including space available only to privileged user).

              MBfsused
                     Total amount of space used in megabytes.

              %fsused
                     Percentage of filesystem space used, as seen by a privileged user.

              %ufsused
                     Percentage of filesystem space used, as seen by an unprivileged user.

              Ifree  Total number of free file nodes in filesystem.

              Iused  Total number of file nodes used in filesystem.

              %Iused Percentage of file nodes used in filesystem.


- Network Statistics
`sar -n [keyword | ALL]`

Possible keywords are: `DEV, EDEV, NFS, NFSD, SOCK, IP, EIP, ICMP, EICMP, TCP, ETCP, UDP, SOCK6, IP6, EIP6, ICMP6, EICMP6 and UDP6.`

Dict for DEV:

              IFACE  Name of the network interface for which statistics are reported.

              rxpck/s
                     Total number of packets received per second.

              txpck/s
                     Total number of packets transmitted per second.

              rxkB/s Total number of kilobytes received per second.

              txkB/s Total number of kilobytes transmitted per second.

              rxcmp/s
                     Number of compressed packets received per second (for cslip etc.).

              txcmp/s
                     Number of compressed packets transmitted per second.

              rxmcst/s
                     Number of multicast packets received per second.

              %ifutil
                     Utilization percentage of the network interface. For half-duplex interfaces, utilization  is  calculated  using  the  sum  of
                     rxkB/s and txkB/s as a percentage of the interface speed. For full-duplex, this is the greater of rxkB/S or txkB/s.


- Display block devices
`sar -d`
Dict:

              tps    Total number of transfers per second that were issued to physical devices.  A transfer is an I/O request to  a  physical  de‐
                     vice.  Multiple  logical  requests  can  be combined into a single I/O request to the device.  A transfer is of indeterminate
                     size.

              rkB/s  Number of kilobytes read from the device per second.

              wkB/s  Number of kilobytes written to the device per second.

              dkB/s  Number of kilobytes discarded for the device per second.

              areq-sz
                     The average size (in kilobytes) of the I/O requests that were issued to the device.
                     Note: In previous versions, this field was known as avgrq-sz and was expressed in sectors.

              aqu-sz The average queue length of the requests that were issued to the device.
                     Note: In previous versions, this field was known as avgqu-sz.

              await  The average time (in milliseconds) for I/O requests issued to the device to be served. This includes the time  spent  by  the
                     requests in queue and the time spent servicing them.

              %util  Percentage of elapsed time during which I/O requests were issued to the device (bandwidth utilization for the device). Device
                     saturation occurs when this value is close to 100% for devices serving requests serially. But for devices serving requests in
                     parallel, such as RAID arrays and modern SSDs, this number does not reflect their performance limits.


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