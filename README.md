# Boot-on-Power-Android
This repo provides a step by step instructions on how to set up a samsung phone for auto boot when powered up.

***Disclamer**
I am not responsible for bricked devices, dead SD cards or the current economic crisis caused by you following these directions. YOU are choosing to make these modificiations, and if you point your finger at me for messing up your device I will LMAO at you.

**How to boot a samsung phone using the LPM file method.**

Test Device: 
Samsung s9+

Requirement: 
Rooted Phone with Magisk 

Windows Apps needed
	1. Notepad++

Android Apps needed
	1. F-Droid
	2. Termux

Step 1
Createting a new .sh file or you can use mine from the repo
	1. Open notepad ++
	2. create a new file
	3. Paste the code below
	4. 	
    
    #!/system/bin/sh
		su -c "echo 1 > /proc/sys/kernel/sysrq"
		echo b > /proc/sysrq-trigger
	
  5. select all CTRL + A
	6. Find and replace CTRL + H
	7. In "Find What:" \r\n
	8. In "Replace with:" \n
	9. Under "Search mode" select Extended
	10. click Replace All
	11. Save the file as rebootoncharge.sh
	12. Now copy the file to the root of sd card
	
Step 2 Installing apps
	1. Install F-Droid
	2. Open F-Droid and Install Termux ( do not install from Play Store)


After installing above
Open Termux and type in the commands

su

mount -o remount,rw /system

cp lpm lpm.orig

echo /sdcard/reboot_on_charge.sh > /system/bin/lpm

exit

exit

Once you have rechecked that you have followed the above process, shutdown the phone and plug in the charge cable and wait for the magic to happen in 30sec 

