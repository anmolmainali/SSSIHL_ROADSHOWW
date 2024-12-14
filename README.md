# SSSIHL_Roadshow
This repository documents my experience in RISC-V and VLSI Chip Design Roadshow   &amp; Upskilling Workshop at SSSIHL

# Workshop Overview
In this one day workshop me and my fellow Physics enthusiast we were introduced to VLSI and RISC-V and got to understand the process of making a chip. This workshop also helped us understand about various kinds of chips and microprocessors, this workshop was very useful as it helped us to delve more into the field of VLSI and chip designing with more career options in the future.

# Process 
We first installed all the softwares as shown below

![Screenshot 2024-12-14 094402](https://github.com/user-attachments/assets/bf5f1750-9096-48b0-a24a-40817bcfc72d)

* Slack is platform where we recieved our codes and where we could share our personal progress with other designers in the channel and also interact with them.

* Oracle virtual box helped us use and external OS where we worked our code for designing.(The OS used was  Ubuntu 18.04 LTS(Bionic Beaver)

* vsd squadron was exported to the virtual box where we used to open the OS.

# The follow up steps

Now after setting up our necessary tools required we processed to open the Virtual Box and we were encountered with a preface of this kind

![Screenshot 2024-12-13 100427](https://github.com/user-attachments/assets/bf79f6ec-f9d8-42f1-93e0-e1d75e039661)


* After opening Virtual Box we opened a new terminal where we wrote our new commands to install gedit

* We use the command ### Example Commands to clone a Git repository and install gedit:

  ` sudo apt install gedit`

  * The password provided by the host was used to install gedit
 
    

![image](https://github.com/user-attachments/assets/71b143fe-f6fa-4af0-9dfa-ccf4a05caf32)

* The new white interface was used to write our code and save it.

  ### Code ###

  `#include<stdio.h>
int main(){
    int sum = 0, i, n;
    printf("Enter the value of n = ");
    scanf("%d",&n);
    for(i = 1;i <= n;i++){
       sum = sum + i;
    }
    printf("The Sum of numbers from 1 to %d is %d\n",n,sum);
    return 0;
}
`


