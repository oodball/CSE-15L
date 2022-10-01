# Lab Report 1
In order to set up remote connection for CSE 15L, it is important that we need to know how to connect to the three computers that we will be using, labeled as ieng6.

This is the tutorial for how to remote in 6 Steps:
- Installing VScode
- learning how to Remotely Connect
- Simple Commands
- Moving Files with ```scp```
- Setting up SSH (Windows OS)
- Optimizing Remote Running

# Step 1: VS Code:
[Visual Studio Code](https://code.visualstudio.com/download) is an IDE that will become very helpful in editing code. You can download it in the link above for Windows, Mac, and Linux and read the descriptions to download it to your computer. 

![VS Download Page](https://media.discordapp.net/attachments/1023749314587140137/1025589586895835156/unknown.png)

After downloading, you will be able to see this startup page:

![VS Startup IMG:](https://media.discordapp.net/attachments/1023749314587140137/1025550595190435900/unknown.png?width=898&height=671)

Open the terminal using the command ```Ctrl + Shift + ~ ```, or starting a new terminal in the command bar above using ```Terminal > New Terminal```.

# Step 2: Remotely Connecting:
Before going further on the terminal, you need to first find your CSE 15L account. You can do this by going to the [CSE 15L Account Lookup](https://sdacs.ucsd.edu/~icc/index.php) and inputting your UCSD SSO credentials. Then, click on the button that says ```cs15lfa22xx```(the xx is replaced by your custom username, mine is ni) and click reset your password. You can use the same password as your SSO. 

![Account Lookup Image](https://media.discordapp.net/attachments/1023749314587140137/1025589691300458506/unknown.png?width=1337&height=671)

Wait around 15-20 minutes and then go back to the VS Code Terminal.


I operate on Windows, so I had to install Open SSH on my computer. Here are the steps to do that: 

(Note: you must be running on an admin account to do these steps)

- Go to **Settings > Apps >  Optional Features**
    - Scroll through the already added features, and check to see if Open SSH Client is already installed. Personally, I use this feature to remote into other computers for work, so I already had it installed. 

![Windows Setting Optional Feature](https://media.discordapp.net/attachments/1023749314587140137/1025607907049472071/unknown.png?width=777&height=671)
    
- If it isn't, go to ```Add a feature``` and search for Open SSH Client. Click **install**. Return to the VS Code terminal.


 In terminal, type ``` ssh cs15lfa22ni@ieng6.ucsd.edu```. For Windows, it will look slightly different than Mac OS, but it's possible to use Powershell to operate now. 

 When prompted for the fingerprint, type ```yes``` and input your password that you set earlier. Your screen should look something like this if successful:

 ![remote login successful](https://media.discordapp.net/attachments/1023749314587140137/1025612193758195773/unknown.png)

# Step 3: Simple Commands

Good job getting here! 

For the purposes of this tutorial, only ```ls```, ```dir```, ```cat```, ```who``` and ```cd``` will be used as simple commands. 
- ```ls``` and ```dir``` lists out the files in the current directory
- ```cat``` prints out the contents of a file 
- ```who``` gives information about who else is connected to the remote server
- ```cd``` changes the directory
    - Using cd will give you the ability to open files, while ```cd ..``` brings you back to the previous directory. 

Run these commands to see how they work.

![Running Commands](https://media.discordapp.net/attachments/1023749314587140137/1025612339657048154/unknown.png)

Log out of the remote computer using the command ```exit```.

# Step 4: Moving files with ```scp```
With the ```scp``` command, you can copy files from your local computer to the server. 

1. Create a java file. For this, I create a file called ```WhereAmI.java``` with code that was provided from the course. You could create one as simple as a file that only prints out ```"Hello World!"```.

2. Save it

3. In terminal, type ```scp "fileName" directory```. For instance, since I am transferring over WhereAmI.java, I would be typing ```scp WhereAmI.java cs15lfa22ni@ieng6.ucsd.edu:~/``` to transfer to your remote server. 

4. Input your password and press **enter**

![scp input](https://media.discordapp.net/attachments/1023749314587140137/1025615401113104434/unknown.png)

Note: You have to be in the directory that the file is in, or else you won't be able to find the file, like I did above

# Step 5: Generating an SSH Key
To save time, generating an SSH Key is easier so you don't have to keep inputting passwords and waiting for longer than you have to to transfer and copy files. 

In local terminal, type ```ssh-keygen```, which will generate a public and private RSA key pair. There are different types, but for this, I used the default, which is RSA. 

You will be prompted to input a file to save the keypair to, and then input a passcode. For both, I just pressed **Enter**, which will save it to the default, and then set an empty passcode, so I won't have to input a passcode. 

![sshkeygen](https://media.discordapp.net/attachments/1023749314587140137/1025617650312826942/unknown.png)

For Windows, there is an extra step. I was told to follow the ```ssh-add``` function on the Microsoft website, but it didn't work for me, so I did it without going through command prompt and finding it. 

[Here are the directions to the command prompt directions.](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

If that also doesn't work for you, I went into Services through finding the **Windows Start menu > Services**. Find **Open SSH Authentication Agent** and click on Properties. By default, Windows has this feature disabled. 

![Open SSH image](https://media.discordapp.net/attachments/1023749314587140137/1025619310137331742/unknown.png)

Afterwards, toggle the Startup type to **Automatic**. Click **Start** and then **apply**. 

![openssh start menu](https://media.discordapp.net/attachments/1023749314587140137/1025619381033631874/unknown.png)

Finally, go back to vscode and type ```ssh-add```. You should get an output that looks like this. 

![sshadd](https://media.discordapp.net/attachments/1023749314587140137/1025620512476495912/unknown.png)

Go back to VS Code terminal, then type ```ssh cs15lfa22zz@ieng6.ucsd.edu``` and enter your password. Then, on the server, type ```mkdir .ssh```, which will make a directory called .ssh. 

Logout of the server. Then, locally, type ```scp /Users/audre/.ssh/id_rsa.pub cs15lfa22ni@ieng6.ucsd.edu:~/.ssh/authorized_keys```. Change around the type to fit your credentials. Enter your password. 

Congrats, you are now able to get into the remote server quicker!

# Step 6: Optimizing Remote Running
To make things easier for myself, I tried out running things now that I don't have to put in a password. Every command I did above was able to be recalled using the up arrow on the keyboard. So, I used the up arrow to do several things: 

- copy a file of my WhereAmI.java file to the server
- log in using ssh
- running commands on the server before even logging into the server
- compiling and running the WhereAmI.java file

In total, this saved about 80% of the time it would have usually taken me to do all the steps without the ssh key. 

![savingTime](https://media.discordapp.net/attachments/1023749314587140137/1025624238356439040/unknown.png)

# Step 7: Celebrate

You are now able to efficiently log in remotely!









