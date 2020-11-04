
# CMPE283 Assignment 2:


## Division of Work:

###   1. Devanshu Dighe : (Email : devanshu.dighe@sjsu.edu, Student ID: 014608347)
Collaboratively completed the functionality and code changes in the vmx.c and cpuid.c emulation functions. I worked mainly on the vmx.c file to calculate the number of exits and cycle times of the exits. 

__Steps__: 
1) Installed VMware Workstation on my Windows machine and set up an outer VM with Linux OS.
2) Performed the required steps and commands required to build and update the kernel from the Linux Master branch.
3) After building the kernel to its latest version, I referred the video lecture 5 to understand where to update the emulation code.
4) In the vmx.c file under the function vmx_handle_exit, to calculate the cycle time, I looked under SDM and figured out that it can be calculated by using the RDTSC function. So I took 2 variables and declared one at the start of the function from which we will know the start time when the exit happened. We are interested in how many cycles are spent by the cpu when an exit has occured. So we put a time stamp counter after the vmx_handle_exit returns from the cpuid emulation code. That is when we want to end our timer and that is our total time spent for the required exit type.
5) This was performed considering a single CPU. To make it thread safe and concurrent on multiple CPU's I added the atomic variables that helps in achieving concurrent values of cycle times on multiple CPUs. 
6) Tested the program on an inner VM which was also VMware Workstation. Installed a package called CPUID that helps us testing the functionality using the command **cpuid -l 0x4FFFFFFF**
             

###   2. Sumeet Deshpande (Email: sumeetsuhas.deshpande@sjsu.edu, Student Id: 014608334)
Worked in tandem with my team member to implement the features required by the assignment. Worked primarily on the cpuid.c and vmx.c to enable the system to respond with the number of exits and cycle times of the exits when the cpuid leaf function is called.
__Steps__:
1) Worked on a dual booted machine with Ubuntu 18.04 installed in it.
2) Referred the assignment to follow the steps required for building the Kernel to the latest version.
3) Understood where to make code changes required for the assignment from Video 5.
4) Made changes in the vmx_handle_exit function of the vmx.c file to calculate the number of exits by using the atomic_inc function. Atomic variables were used to make the system concurrent. The atomic variable was initialized in cpuid.c and exported in vmx.c using the export_symbol function. 
5) Added the leaf function in the cpuid.c file in the kvm_emulate_cpuid function. Stored the number of exits in eax, high 32 bits in ebx and low32 bits in ecx as required by the assignment.
6) Tested the program by using an inner VM using the virt-manager and qemu. Installed the cpuid package to test the functionality with the command mentioned in the assignment.


## Questions
1) Comments on the frequency of exits:
  - The number of exits do increase after subsequent runs of the CPUID leaf function and at a stable rate.
2) How many exits?
  - There are approximately 2.4 million exits in a full VM boot.
  
## Link to linux repo:
The code was submitted into a forked linux repository as well. Here's a link to the same : https://github.com/devanshudighe/linux
