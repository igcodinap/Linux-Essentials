# I/O Monitoring

### iostat
Report Central Processing Unit (CPU) statistics and input/output statistics for devices and partitions.

Syntax: `iostat [options] [devices] [interval] [count]`

- List devices io statistics in blocks
`iostat`

- List devices in kb or mb
`iostat [-k | -m]`

- List devices by their names
`iostat -N`

- List extended information
`iostat -x`

### iotop
Displays an interactive table of current I/O usage and updates periodically.

Syntax: `iotop [options]`

### ionice
Sets both the I/O schedulling class and priority for a given process.

Syntax: `ionice [-c class] [-n nice_value] [-p pid | -P pgid | -u uid] [command [ARGS]]`

Class Dict:
- None or unknown(0): default value.
- Real time(1): get first access to the disk, can starve other processes.
- Best effort(2): all programs serviced in round-robin fashion.
- Idle(3): no access to disk I/O unless no other program has asked for it for a defined period.