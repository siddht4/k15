# tenda_router

This is how i actually booted up my TENDA AC10 router after a wrong firmware update bricked the router


# FIRMWARE SOURCE

[tenda firmware](https://www.tendacn.com/in/download/default.html)


# FLASH if Router Bricked

|S_no      |STEP       |
|----------|-----------|
|1         |   DOwnload the relevant firmware and the closest to the router model |
|2         | Unzip the file,usually two files are provided.First bin file,which is the firmware, secondly PDF file,which is not required in this case |
|3         | Connect the router WAN port to your system using RJ45/patch cable/cat 5e/cat 6 cable |
|4         | power on the router,change the ip to default or set to automatic.We reach here in windows from Step 1 . Set Network and configuration ,2 . In the interfaces,click on ethernet/LAN/wired, 3. right click on it,open change ip/ipv4, 4. In the IP click on DEtect automatically. |
|5         | check the ip,if the router is in bricked state, the ip will be as 169.X.Y.Z |
|6         | Now re open the ip,from automatic set it to 192.168.1.10 for your system,mask as 255.255.255.0 and gateway to 192.168.1.2 |
|7         | Your router will be in 192.168.1.6 i.e in disaster mode,here you have to tftp the bin file to the router  |
|8         | I had used [Angry ip scanner](https://angryip.org/) to find where the router was, the router was in  192.168.1.6 |
|9         | In case disaster mode is not set,then first hold the reset button of the router for 30 seconds,2.remove the power cable from the router but still press the reset key for 30 seconds,then reconenct the power and still press the reset for 30 more seconds. So you have hold the reset key for 90 seconds. i.e 30 second + 30 seconds (remove plug) + 30 seconds (reconnect plug). Your router will enter disaster mode |
|X         | In windows from additional services and program in the control panel install TFTP client.                                                                     |
| 11       | Disconnect from the internet. Make a folder in C drive as tftp i.e C:\\tftp             | 
|12        | using cmd, go to C:\\tftp,copy paste the bin file which you had find after unzipping the zip file in step 2.For your conveince rename it to AC.bin or alternatively make sure of the name |
|13        | Now disbable firewall from turning off the firewall.This is the reason I had asked you to dissconnect from the internet |
|14        | Now in cmd type the command "tftp -i 192.168.1.6 put AC.bin" , if everything is successful you will receive   “Successful transfer“ otherwise if its fails you will recieve "Timeout " or "Error connecting"   |
|15       | Now your router will reboot itself,now according to s_no 4,again set your ip to automatically configure.If everyhting works out correctly,you will see a network with proper dhcp. |
|16       | SImply open the dashboard by entering the gateway ip,simply configure it back or it will be back to based on the previous settings     |
|17       | Turn back on the firewall   |
|18       | Your router is working back  |
|19       | in case the router has still not booted or no dashbaord is there or the ip is still showing as 169.X.Y.Z  repeat the process with other firmware for closest relative of the router   |
|20      | Example if the router model is AC 10V3(this is my router), then also download firmware for AC 10V3(self),AC 10 V1(closest),AC 10 V2(closest),AC 10 V4 (closest),AC10U (closest+usb)  |
|21      | In my case though the intended firmware didnt work,but the closest one i.e AC10 U worked. Also A21 i.e a WIFI extender also showed up,thogh most of the things were not working but still the router came back to life |
|22      | Check what works and what doesnt.Then list them on excel.One which works most should be the one you should continue to use.After finding whats actually works mostly,its now a elimation of the firmware which are not working  |  
 


# SET IP

IP: 192.168.1.10
Mask: 255.255.255.0
Gateway: 192.168.1.2
NS: 192.168.1.2
DNS2: 192.168.1.3
