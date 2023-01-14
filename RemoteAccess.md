# Remotely Connecting

Written By: Nathan Dowd

---
  In this tutorial, we're going to be going over how you can log into your CSE 15L account on ieng6. To start, you're going to need to look up your [CSE 15L account](https://sdacs.ucsd.edu/~icc/index.php). Log in with the first part of your ucsd email (Ex: ndowd@ucsd.edu --> ndowd), and your PID starting with an A or U. Once in take note of the three letters follwing cse15lwi23. Should look like this.

`cse15lwi23xxx`

Then follow the instructions to change your password. Make sure you remember what you changed it to. The change may take up to 15 minutes to take affect, which will come into play in a bit. Now that you have your information set up, you need to download [VS Code](https://code.visualstudio.com/). Follow the instructions to download VS Code to your computer. Once it is installed, open it up, and it should look something like this.
![Image](https://i.paste.pics/e87c5124b78cff605baba7e748fda477.png)

If you're on Windows, you need to dowload [Git](https://gitforwindows.org/), then follow these [instructions](https://stackoverflow.com/a/50527994) to set your terminal to use Git Bash. Now open a new termial, and type the command below to remotely connect to the server on your account. Replace the xxx with your account letters. (The $ is already in your terminal, don't put another in)

```
$ ssh cs15lwi23xxx@ieng6.ucsd.edu
```

Assuming this is your first time connecting to the server, you will get a message like this.

```
⤇ ssh cs15lwi23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

This is normal, type yes to allow the connection. Then type in your password and press enter. When you type, nothing will show onscreen, but it is being typed in. If it doesn't work, make sure you have typed it in correctly. If it still doesn't work, your password change might not have gone through, so just wait a few minutes and try again. Once you are in, your screen should look similar to this one.

![Image](https://i.paste.pics/49fe3a78a92b90c08cc4053cde0faf4c.png)

Now try to run a few commands to experiment with the different outputs. Here's a list of some basic ones to try.

- cd ~
- cd
- ls -lat
- ls -a
- ls <directory> where <directory> is /home/linux/ieng6/cs15lwi23/cs15lwi23abc, where the abc is one of the other group members’ username
- cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/
- cat /home/linux/ieng6/cs15lwi23/public/hello.txt
  
Here's what that last command should output for you.

![Image](https://i.paste.pics/b139a0a9c426bb18cb2d3e1c377e8729.png)
  
To disconnect from the server, you can use Ctrl-D or type the command exit.

Thanks for following along, I hope it worked well for you.
