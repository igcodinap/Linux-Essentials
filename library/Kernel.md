# Kernel

### sysctl
Configure kernel parameters at runtime. The parameters are those listed under /proc/sys

### lsmod
List loaded modules

### insmod
Directly load modules

### rmmod
Directly remove modules

### modprobe
Load or unload modules using a pre-built module database with dependency and location
/lib/modules/$(uname -r)/modules.dep

### depmod
Rebuild the module dependency database

### modinfo
Display information about a module