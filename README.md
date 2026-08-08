# System Stress Test Checklist and Tools
Simple checklist that I use to keep track of tools and steps to stress test a single machine system in Win and Linux.
Hardware currently checked in the routine:
- CPU (load + thermal)
- Memory (load)
- Disk (load + thermal)
- GPU (load + thermal) # more complex testing routine can be useful
- Network Ethernet/WiFi (not tested)

# Linux
## Tools
- htop (cpu)
- btop
- lm-sensors:
    `sudo apt install lm-sensors`, `watch -n 1 sensors`
- nvtop
- nvidia-smi
- stress-ng
- [UNIGINE](https://benchmark.unigine.com/)
- iperf3
For tools that only perfom a single read you can pair the watch command such as `watch -n 1 nvidia-smi`

## Simple test routine
X = value to set according the system
1. `stress-ng --cpu 0 --timeout 120`, fully load all the cpu cores at 100%
2. `stress-ng --vm 1 --vm-bytes XG --timeout 120`, one worker process that allocates XG of memory
3. `stress-ng --hdd 2 --hdd-bytes 25G --temp_path --timeout 120`, runs 2 storage stress workers, each worker writes 25 GB of data

# Windows
## Tools 
TODO:
## Simple test routine

## Debloating tools 
- [Windows AI remover](https://github.com/zoicware/RemoveWindowsAI)
- [Chris Titus Tech's Windows Utility](https://github.com/christitustech/winutil)

# Random bonus
- [markdown syntax](https://www.markdownguide.org/basic-syntax/#links)
- TODO: add github bonus scripts as modules to streamline tests
