

# CMPE283 Assignment 4:


## Division of Work:

###   1. Devanshu Dighe : (Email : devanshu.dighe@sjsu.edu, Student ID: 014608347)
I researched the behaviour of exits that were happening when EPT was not 0. 
             

###   2. Sumeet Deshpande (Email: sumeetsuhas.deshpande@sjsu.edu, Student Id: 014608334)
I researched the behaviour of exits that were happening when EPT was set to 0. 

### Steps: (Same as assignment 3)


## Questions
1) Include a sample of your print of exit count output from dmesg from “with ept” and “without ept”.
  - With EPT
  ![alt text](https://github.com/devanshudighe/CMPE283/blob/main/Assignment-4/With_EPT.png "With ept")

  - Without EPT
  ![alt text](https://github.com/devanshudighe/CMPE283/blob/main/Assignment-4/Without_EPT.png "without ept")


2) What did you learn from the count of exits? Was the count what you expected? If not, why not?
3) What changed between the two runs (ept vs no-ept)?
    > As you can see, the number of exits increases by about 200,000 when EPT is set to 0. The count was expected to increase by a significant amount and it did increase as per the results. The reasons why the count was expected to increase can be stated as follows:
    When EPT is set to zero, we follow the shadow paging approach instead of the nested paging approach followed when the EPT is not set to zero. Now, during shadow paging approach, there are 3 kinds of exits which are enabled and occur due to which the exit count increases. These 3 types are : CR3 exits, Page Fault Exits and TLB Flush exits. These 3 types of exits occur in addition to the EPT violation exit that occurs usually in the Nested paging approach. Hence, the number of exits are more in this approach and the difference can hence be explained.
  
  
## Link to linux repo:
The code was submitted into a forked linux repository as well. Here's a link to the same : https://github.com/devanshudighe/linux
