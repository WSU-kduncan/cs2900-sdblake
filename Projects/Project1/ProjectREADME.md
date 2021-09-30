## Project 1 - Sam Davis 

---

### Part 1 - Buidling VMs

---
- Operating System: Linux (Version: Ubuntu)
- Disk Space: I selected a Fixed Space of 15GB because I wanted to control how much was being taken from my host machine. If I had selected "Dynamically Allocated", the VM would
take what it would needed. With this I can organize my storage more and know what can and can't be installed. 
- Memory/Ram Allocation: I allocated 4000mb of space for ram, to allow plenty of extra space for storage if needed. Rather than filling it up and causing possible errors. 
- Tip: When creating your VM, it may not assume the Disk file you would like to use. When starting the machine a Optical Disk Selector Window may appear, click Add then point
it to the Ubuntu Desktop Iso file. 
- 3D Acceleration: This basically means you are giving your VM a virtual GPU, it can help with storage and from keeping your host machine from getting overhwelmed. 
- Guest Additions:  Guest Additions are basically devices that are desinged to create a closer relationship between the host and guest OS. While they increase system performance, they can also put your system at higher risk due to it being more connected to the host OS, which allows more attack vectors. 
   - In order to install Guest additions all you need to do is click Devices -> Insert Guest Additions CD Image -> Reset your machine -> Hit view and click full screen -> then Click on auto resize guest display and it will display in full screen. You can check if your guest addition is working by typing the following command, "lsmod | grep -i vbox" and it should come out with a vboxguest,vboxvideo and a few other results. 

### Part 2 - Exploring Virtualization
---
- Host Files: I was not able to access guest files at first, but if you go to your VirtualBox manager, go to settings and then shared folders. You can create a folder on your host OS that shares and connects with your VM. After creationg the shared folder on the Manager, it pops up on the guest machine buit I cannot access it due to not having the correct permission, running this line will give you permission to access it, "sudo gpasswd -a cs2900 vboxsf"
 ![image](https://user-images.githubusercontent.com/59904812/134061168-1124bbc4-26d5-4f3b-91fb-50555dbe3d84.png)
 
 - Tempplate Space: Right clickikng on the machine allows you to create a "clone" of your machine which basically copies the state of the machine and all disk files and folders, etc.  The Virtual Disk Image hols 8,769,536 KB
 - Snapshot Space: 662,884 KB Basically a copy of the virtual machines disk file
 - Network Layout: This is the layout for the actualy ubuntu machine 
![image](https://user-images.githubusercontent.com/59904812/134065460-202c3b09-bd6c-4297-a49b-17f12877f011.png)
- This is the layout of the hypervisor that allows the machine to communicate to the outside world
![image](https://user-images.githubusercontent.com/59904812/134065846-d538bf37-9ec0-45e6-95a9-93b715c3298b.png)

### Part 3 - Networking With Style
---
1. Shut off Machine
2. Right click machine in virtual manager
3. Go to netowrk settings and select the second adapter, select bridged adapter in the drop down and then select the name of your network.
4. Launch Machine
5. Open a terminal and type "ip a" to list the active connections
6. Then, ping your host ip that virtual box has given you and look for successful pings. 
![image](https://user-images.githubusercontent.com/59904812/134069249-9c2e854c-95c1-4a69-a7bf-5577a2b85e4b.png)

