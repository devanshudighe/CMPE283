# CMPE283 Assignment 1:


## Division of Work:

###   1. Devanshu Dighe : (Email : devanshu.dighe@sjsu.edu, Student ID: 014608347
      Modified and added code for VM Entry Controls and VM Exit Controls. 
      Steps: 1) Loaded the Linux OS from Dual Boot mode.
             2) Searched the VM Entry Control Fields/VM Exit Control Fields from SDM 24.8.1 and 24.7.1 respectively and added the fields to the code
             3) Performed the steps required to run and execute the cmpe281-1.c file (make, insmod, dmesg)
             4) Copied the Output from the terminal to the Readme file.

###   2. Sumeet Deshpande (Email: sumeetsuhas.deshpande@sjsu.edu, Student Id: 014608334)
   Researched and worked on writing the code for executing the Primary VM Based Controls and Secondary VM Based Controls for the Assignment. 
   Added the corresponding code implementations and their outputs in the cmpe283-1.c and README.md file respectively
   
          Steps: 
   
          1) I used the Linux OS on a dual booted machine to perform the assignment.
   
          2) Due to some reason, the Secure Boot feature of my machine was enabled. Hence, I was not able to execute the INSMOD command as despite using the super user via sudo, I was getting the message: Operation not permitted. Researched on the issue and disabled the Secure Boot feature by going to the Boot Menu.
          
          3) Wrote code for the Primary VM Based Controls and Secondary VM Based Controls by referring to Professor's boilerplate code and SDM modules.
          
          4) Ran the required commands (make, insmod, dmesg) and committed the required output in the ReadMe.md file.


## Output of all the VM controls:

### Output for IA32_VMX_ENTRY_CTLS

[16137.288529] Entry Controls MSR: 0x3ffff000011ff
[16137.288530]   Load Debug Controls: Can set=Yes, Can clear=No
[16137.288531]   IA-32e mode guest: Can set=Yes, Can clear=Yes
[16137.288532]   Entry to SMM: Can set=Yes, Can clear=Yes
[16137.288532]   Deactivate dual-monitor treatment: Can set=Yes, Can clear=Yes
[16137.288533]   Load IA32_PERF_GLOBAL_CTRL: Can set=Yes, Can clear=Yes
[16137.288533]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[16137.288534]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[16137.288535]   Load IA32_BNDCFGS: Can set=Yes, Can clear=Yes
[16137.288536]   Conceal VMX from PT: Can set=Yes, Can clear=Yes
[16137.288536]   Load IA32_RTIT_CTL: Can set=No, Can clear=Yes
[16137.288537]   Load CET state: Can set=No, Can clear=Yes
[16137.288537]   Load PKRS: Can set=No, Can clear=Yes

________________________________________________________________________________

### Output for IA32_VMX_EXIT_CTLS

[16137.288538] Exit Controls MSR: 0x1ffffff00036dff
[16137.288539]   Save debug controls: Can set=Yes, Can clear=No
[16137.288539]   Host address-space size: Can set=Yes, Can clear=Yes
[16137.288540]   Load IA32_PERF_GLOBAL_CTRL: Can set=Yes, Can clear=Yes
[16137.288540]   Acknowledge interrupt on exit: Can set=Yes, Can clear=Yes
[16137.288541]   Save IA32_PAT: Can set=Yes, Can clear=Yes
[16137.288541]   Load IA32_PAT: Can set=Yes, Can clear=Yes
[16137.288542]   Save IA32_EFER: Can set=Yes, Can clear=Yes
[16137.288543]   Load IA32_EFER: Can set=Yes, Can clear=Yes
[16137.288543]   Save VMX-preemption timer value: Can set=Yes, Can clear=Yes
[16137.288544]   Clear IA32_BNDCFGS: Can set=Yes, Can clear=Yes
[16137.288545]   Conceal VMX from PT: Can set=Yes, Can clear=Yes
[16137.288546]   Clear IA32_RTIT_CTL: Can set=No, Can clear=Yes
[16137.288546]   Load CET state: Can set=No, Can clear=Yes

________________________________________________________________________________

### Output for IA32_VMX_PRIMARY_PROCBASED_CTLS

[ 5059.847140] Primary Processor based Controls MSR: 0xfff9fffe0401e172
[ 5059.847141]   Interrupt-window exiting: Can set=Yes, Can clear=Yes
[ 5059.847141]   Use TSC offsetting: Can set=Yes, Can clear=Yes
[ 5059.847142]   HLT exiting: Can set=Yes, Can clear=Yes
[ 5059.847143]   INVLPG exiting: Can set=Yes, Can clear=Yes
[ 5059.847143]   MWAIT exiting: Can set=Yes, Can clear=Yes
[ 5059.847144]   RDPMC exiting: Can set=Yes, Can clear=Yes
[ 5059.847145]   RDTSC exiting: Can set=Yes, Can clear=Yes
[ 5059.847145]   CR-3-load exiting: Can set=Yes, Can clear=No
[ 5059.847146]   CR-3-store exiting: Can set=Yes, Can clear=No
[ 5059.847147]   CR8-load exiting: Can set=Yes, Can clear=Yes
[ 5059.847148]   CR8-store exiting: Can set=Yes, Can clear=Yes
[ 5059.847148]   Use TPR shadow: Can set=Yes, Can clear=Yes
[ 5059.847149]   NMI-window exiting: Can set=Yes, Can clear=Yes
[ 5059.847150]   MOV-DR exiting: Can set=Yes, Can clear=Yes
[ 5059.847150]   Unconditional I/O exiting: Can set=Yes, Can clear=Yes
[ 5059.847151]   Use I/O bitmaps: Can set=Yes, Can clear=Yes
[ 5059.847152]   Monitor trap flag: Can set=Yes, Can clear=Yes
[ 5059.847152]   Use MSR bitmaps: Can set=Yes, Can clear=Yes
[ 5059.847153]   MONITOR exiting: Can set=Yes, Can clear=Yes
[ 5059.847154]   PAUSE exiting: Can set=Yes, Can clear=Yes
[ 5059.847154]   Activate secondary controls: Can set=Yes, Can clear=Yes

_______________________________________________________________________________

### Output for IA32_VMX_SECONDARY_PROCBASED_CTLS

[ 5059.847155] Secondary Processor based Controls MSR: 0x3cff00000000
[ 5059.847156]   Virtualize APIC accesses: Can set=Yes, Can clear=Yes
[ 5059.847157]   Enable EPT: Can set=Yes, Can clear=Yes
[ 5059.847157]   Descriptor-table exiting: Can set=Yes, Can clear=Yes
[ 5059.847158]   Enable RDTSCP: Can set=Yes, Can clear=Yes
[ 5059.847159]   Virtualize x2APIC mode: Can set=Yes, Can clear=Yes
[ 5059.847159]   Enable VPID: Can set=Yes, Can clear=Yes
[ 5059.847160]   WBINVD exiting: Can set=Yes, Can clear=Yes
[ 5059.847161]   Unrestricted guest: Can set=Yes, Can clear=Yes
[ 5059.847161]   APIC-register virtualization: Can set=No, Can clear=Yes
[ 5059.847162]   Virtual-interrupt delivery: Can set=No, Can clear=Yes
[ 5059.847163]   PAUSE-loop exiting: Can set=Yes, Can clear=Yes
[ 5059.847164]   RDRAND exiting: Can set=Yes, Can clear=Yes
[ 5059.847164]   Enable INVPCID: Can set=Yes, Can clear=Yes
[ 5059.847165]   Enable VM functions: Can set=Yes, Can clear=Yes
[ 5059.847166]   VMCS shadowing: Can set=No, Can clear=Yes
[ 5059.847166]   Enable ENCLS exiting: Can set=No, Can clear=Yes
[ 5059.847167]   RDSEED exiting: Can set=No, Can clear=Yes
[ 5059.847168]   Enable PML: Can set=No, Can clear=Yes
[ 5059.847169]   EPT-violation #VE: Can set=No, Can clear=Yes
[ 5059.847169]   Conceal VMX from PT: Can set=No, Can clear=Yes
[ 5059.847170]   Enable XSAVES/XRSTORS: Can set=No, Can clear=Yes
[ 5059.847171]   Mode-based execute control for EPT: Can set=No, Can clear=Yes
[ 5059.847172]   Sub-page write permissions for EPT: Can set=No, Can clear=Yes
[ 5059.847172]   Intel PT uses guest physical addresses: Can set=No, Can clear=Yes
[ 5059.847173]   Use TSC scaling: Can set=No, Can clear=Yes
[ 5059.847174]   Enable user wait and pause: Can set=No, Can clear=Yes
[ 5059.847174]   Enable ENCLV exiting: Can set=No, Can clear=Yes
