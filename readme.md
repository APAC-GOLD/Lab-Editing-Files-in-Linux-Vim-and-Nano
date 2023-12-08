# Lab - Editing Files in Linux. (Vim and Nano)

Editing Files
Note All labs rely on previous courseware and lab information.

## Objectives
Use the vimtutor executable to conduct tasks 1-4
Copy content from the /var/log/secure file, and edit it with nano

Task 1: Use SSH to connect to an Amazon Linux EC2 instance
In this task, you will connect to a Amazon Linux EC2 instance. You will use an SSH utility to perform all of these operations. The following instructions vary slightly depending on whether you are using Windows or Mac/Linux.

 WINDOWS USERS: USING SSH TO CONNECT
 These instructions are specifically for Windows users. If you are using macOS or Linux, skip to the next section.

From the Lab Information pane, select the PPK link and save the file. The file name will be similar to Ec2KeyPair-PPK.ppk. Typically your browser will save it to the Downloads directory.

Make a note of the PublicIP address.

Download PuTTY to SSH into the Amazon EC2 instance. If you do not have PuTTY installed on your computer, download it here .

Open putty.exe

Configure PuTTY timeout to keep the PuTTY session open for a longer period of time.:

Select Connection
Set Seconds between keepalives to 

30
Configure your PuTTY session:
Select Session
Host Name (or IP address): Paste the Public DNS or IPv4 address of the instance you made a note of earlier. Alternatively, return to the EC2 Console and select Instances. Check the box next to the instance you want to connect to and in the Description tab copy the IPv4 Public IP value.
Back in PuTTY, in the Connection list, expand  SSH
Select Auth (don’t expand it)
Select Browse
Browse to and select the ppk file that you downloaded
Select Open to select it
Select Open again.
Select Yes, to trust and connect to the host.

When prompted login as, enter: 

ec2-user
 This will connect you to the EC2 instance.

Windows Users, skip ahead to the next task.

MACOS  AND LINUX  USERS
These instructions are specifically for Mac/Linux users. If you are a Windows user, skip ahead to the next task.

From the Lab Information pane, select the PEM link and save the file. The file name will be similar to Ec2KeyPair-PEM.pem.

Make a note of the PublicIP address.

Open a terminal window, and change directory 

cd
 to the directory where the pem file was downloaded. For example, if the file was saved to your Downloads directory, run this command:


cd ~/Downloads
Change the permissions on the key file to be read-only, by running this command (replace <ssh-key> with the name of the file you downloaded earlier):

chmod 400 <ssh-key>
For example:


chmod 400 Ec2KeyPair-PEM.pem
Note: Your file name may be different from the example.

Run the below command. (replace <ssh-key> with the name of the file you downloaded earlier, and replace <public-ip> with the PublicIP address you copied earlier):

ssh -i <ssh-key> ec2-user@<public-ip>
Type 

yes
 when prompted to allow the first connection to this remote SSH server. Because you are using a key pair for authentication, you will not be prompted for a password.
Task 2: Exercise - run the Vim tutorial
In this exercise, you run the ./vimtutor and follow all directions in the file for tasks 1-4. Vimtutor is an application that teaches you the basics of how to use Vim, which is one of the text editors for Linux.

From your current location in the terminal, enter 

vimtutor
 and press Enter. This step starts the vimtutor session:

vimtutor
Note: You may have to use sudo to conduct this step if you are not root. If vimtutor does not work, you may need to install Vim by entering the following command:


sudo yum install vim
Note: You may have to use sudo to conduct this step if you are not root. If vimtutor does not work, you may need to install Vim using sudo yum install vim.

Complete lessons 1-3 in vimtutor.
The terminal window displays output from the command vimtutor.  The output from this command displays tutorial lesson 1.1: moving the cursor from vimtutor

Figure: Vimtutor consists of tutorials that teaches a user how to use Vim.

Enter 

:q!
 and press Enter to exit vimtutor.
Task 3: Exercise - edit a file in Vim
In this exercise, you use the Vim command-line editor program. Use Vim to create and edit a file using the following steps.

From your current location in the terminal, enter 

vim helloworld
 and press Enter. You are using Vim to create a file called helloworld, and you open this file when you press Enter.
The terminal window displays output from the command vim helloworld. 

Figure: The command vim followed by the file name, in this example the file is named helloworld.

Now that you are in the file that you created called helloworld, use Vim to insert a few lines of text. Enter 

i
 to use insert mode, and enter the following text:

Hello World!
This is my first file in Linux and I am editing it in Vim!
Note: The bottom left of the terminal indicates if you are in insert mode.

Once complete, press ESC to exit insert mode.

Save your changes to the file, and enter the following command to quit:

:wq
Next, type of the following into the command prompt:


vim helloworld
Note: Because the vim helloworld command was the last command that you used, you can use the up arrow to recall the last command and press Enter.

Add the following line to the editor:

I learned how to create a file, edit and save them too!
It should look like the following picture:

The terminal displays a few lines, the first line is text entered in the previously saved vim file. The second line displays the following: I learned how to create a file, edit and save them too!

Figure: The example displays the second line that has been placed in the terminal.

Once complete, press ESC to exit insert mode and use the following command:

:q!
You are back in the main terminal. Use Vim to go back to the helloworld file and analyze what happened. What was the difference?

ADDITIONAL CHALLENGE
Try additional useful commands.

Use the following command to delete the entire line:

dd
Use the following command to undo the last command:

u
Use the following command to save changes without quitting:

:w
Task 4: Exercise - edit a file in nano
In this exercise, you use an alternative command-line editor program called nano. Use nano to create and edit a text file.

Similar to Vim, in the main terminal, enter 

nano cloudworld
 and press Enter. You are using nano to create a file called cloudworld, and pressing Enter opens this file.
The terminal window displays the command nano followed by the word cloudworld.

Figure: The command nano followed by the file name, in this example the file is named cloudworld.

Now that you are in the file that you created called cloudworld, unlike vim, you do not have to enter insert mode. Instead, you can start typing. Enter the following text:

We are using nano this time! We can simply start typing! No insert mode needed.
To save your changes to the file, press CTRL+O. Press Enter to confirm the file name once you save it.

Now that you have saved the file, press CTRL+X to exit the nano editor.

Now that you are at the main terminal, check to make sure our file saved correctly. Enter 

nano cloudworld
 to go back into the file using nano. Confirm that everything is correct as the following image shows, and exit the editor:

The terminal window displays the command CTRL +X which is used to end nano.

Figure: The keys CTRL + X is used to will end the nano editor.

End lab
Follow these steps to close the console and end your lab.

Return to the AWS Management Console.

At the upper-right corner of the page, choose AWSLabsUser, and then choose Sign out.

Choose End lab and then confirm that you want to end your lab.


https://awsrestart.labs.awsevents.com/lab/arn%3Aaws%3Alearningcontent%3Aus-east-1%3A470679935125%3Ablueprintversion%2FCUR-TF-100-RSLINX-3%2F231-lab-LX-editing-files%3A3.0.1-e6315a3a/en-US/46a424b2-440d-424c-b01f-97df9bc7474a::n2ubeeiNZBq1Z8ZvE8XvU9