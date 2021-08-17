
# Installing ROS onto Linux

## Concepts To Understand
### Terminals 

When you press **Ctrl+Alt+T** a window appears which looks similar to the command prompt used in Windows - this is called a **terminal**. It's purpose is to act as a visual interface whereby you type in the commands into the terminal and see the output through that terminal. The **shell** is the software behind the terminal that interprets the commands and executes them into the operating system services. Bash is a particular type of shell which is referred to in some tutorials - another one is zsh . For the purpose of these tutorials, we will stick to the default bash. 

### ROS "Distributions" 

The different versions of ROS are called **distributions**. The rule is that each successive version of ROS is given a different name and the first letter of that name changes alphabetically with each new distribution (version).  

For more information you can  read up on the different distributions  by following this link: 
http://wiki.ros.org/Distributions

The distribution we are using is **ROS Melodic** as this is the one most commonly used here in Manchester and it is one of the most stable. 

## Installing ROS Melodic onto Linux
Now that you Linux up and running, you need to download ROS. The link below will take you to the official tutorial for downloading ROS Melodic. 


http://wiki.ros.org/melodic/Installation/Ubuntu

**Few things to bear in mind:**
* You will be asked to enter your password -  when typing your password, it will appear as if you are not typing anything into the terminal but, in fact, it is taking in the input of your keys. Carefully put in your password and click Enter.
* When instructed to enter code, open up the terminal (by pressing Ctrl+Alt+T) and typing out the commands.
 * * You can copy commands and paste them in the terminal using Ctrl+Shift+V
* **Section 1.4** talks about the different ways you can install ROS but make sure to stick to the **Desktop-Full Install: (Recommended)** 
* In reference to **Section 1.5**, in order to use ROS commands, you need to make sure that the shell knows where to find the ROS commands are (imagine it like inserting a library at the beginning of writing your code). 
```
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

* Be aware that that if you mistype this command, you may have some unintentional outocmes:

* * The >> here means that it will append to (add to) the .bashrc file. Only using > is incorrect.
* *  The .bashrc file is the file that the shell automatically refers to when searching for the commands that you type into the terminal
* * Missing the dot in the .bashrc part will simply lead to you creating a new text file called bashrc in your home folder. This is not what you are intending for.

## Checking that you have ROS installed correctly

 *  You can check that you have completed section 1.5 correctly by typing the following into a new command terminal:
```
echo $PATH 
```
* * If set up correctly then the outcome should be something similar to: 

![echoPATH](echoPATH.png)




* Completing all the sections up to **Section 1.6** means that now you should have ROS downloaded. You can check this by typing out the following command in a new terminal:
```
roscore
```
* * The outcome of this should be as follows:
![roscore](roscore.png)

* Another thing to check is that the environment variables are correctly installed. To do this, type the following into a new command terminal:
```
printenv | grep ROS
```
* * The outcome of which should be:

![greprOS](grepROS.png)


## Installing some dependencies
 
 At this pouint, the last stage is to download some final dependencies that will allow you to some important ROS tools. 

 In a new terminal, type in the following commands:

 ```
 sudo apt install python-rosdep
 ```
 then type the following:
 ```
 sudo rosdep init
 ```
 then type the following:
 ```
 rosdep update
 ```

 The output of which should be the following:
 ![rosUpdate](rosUpdate.png)

 