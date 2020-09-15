---
layout: post
title:  "Anaconda & The Command Line"
date:   2020-09-15 07:00:00 -0700
categories: "intro"
week: "1"
---

### Materials
#### MacOS
* Laptop
* Terminal

#### Windows 10
* Laptop
* Anaconda Powershell


### Installation
#### MacOS
1. Click [here](https://repo.anaconda.com/archive/Anaconda3-2020.07-MacOSX-x86_64.pkg) to download the latest version of `Anaconda Navigator` for `MacOS`
2. Once the download has finished run the installer

#### Windows 10
1. Click [here](https://repo.anaconda.com/archive/Anaconda3-2020.07-Windows-x86_64.exe) to download the latest version of `Anaconda Navigator` for `Windows 10`
2. Once the download has finished run the installer


### Getting to the Command Line
#### MacOS
1. Navigate to Finder > Applications > Utilities > Terminal
2. Run the `Terminal`, you should see something that looks like this:

![]({{site.url}}/assets/mac_os_anaconda_terminal.png)

#### Windows 10
1. Navigate to `Anaconda Powershell` (it should be in the `Start` menu)
2. Run the Anaconda Powershell

Note: who would like to take a screenshot of the Anaconda Powershell and send it to me? Thx!

### Command Prompt
#### MacOs
`$`

#### Windows 10
`>`

The command prompt, illustrated above per operating system, indicates to a user where they can enter commands (type things)


### Moving Around
* `pwd`: or print working directory, shows the directory you are currently in
* `ls`: lists all contents of a directory (folder)
* `cd`: or change directories, use this to move to a different part of your computer


#### Demo
1. check the current working directory (where you are on your computer): `pwd`

    **note** you should be in the `home` directory
2. list the contents of the `home` directory: `ls`
3. choose a FOLDER to open, or change the `working directory`, with `cd`: `cd FOLDER`

    **for example** `cd Downloads`

    **note** the command line has autocomplete, hit TAB as you type characters to try to use it!

4. hit ENTER to run the command
5. check the command prompt, notice anything different?

    **my command prompt (for example)**
    * before step 4 `(base) 95-mdpmclapca:~ cta$`
    * after step 4 `(base) 95-mdpmclapca:Downloads cta$`
6. confirm that the `present working directory` has changed: `pwd`
7. list the contents of the FOLDER directory (`Downloads` in my example): `ls`
8. return to the `home` directory with this SUPER FUN SHORTCUT: `cd ~`
9. confirm that the `present working directory` is now the `home` directory: `pwd`
10. note that the command prompt has returned to its default state

    **my command prompt (for example)** `(base) 95-mdpmclapca:~ cta$`


### File Input / Output

* `mkdir`: make and name a new directory
* `touch`: make and name a new file
* `echo`: outputs the strings being passed as arguments
* `>`: overwrite data in a file (if the file exists)
* `>>` : append data to a file (if the file exists)
* `cat`: reads data from a file and outputs the data
* `nano`: or GNU nano, a text editor


#### Demo
1. make a new FOLDER with `mkdir`: `mkdir DATA`
2. change directories into `DATA`: `cd DATA`
3. confirm that the `present working directory` has changed: `pwd`
4. make a new `.txt` file with `touch`: `touch data.txt`
5. confirm that `data.txt` is present in `DATA`: `ls`
6. we can print messages at the command line with `echo`: `echo "Hello World"`
7. we can also use `echo` to pass information into a `file` with `>`: `echo 'data1' > data.txt`
8. confirm the contents of our file with `cat`: `cat data.txt`
9. let's say we have 2 data points, try adding `data2` to our file with the following: `echo 'data2' > data.txt`
10. confirm the contents of our file with `cat`, see any issues here?: `cat data.txt`
11. `cat` reveals that the command in step 9 has overwritten `data1` with `data2`
12. let's repeat our procedure and overwrite `data2` with `data1`: `echo 'data1' > data.txt`
13. here we use `>>` to **append** `data2` to `data.txt`: `echo 'data2' >> data.txt`
14. confirm the contents of our file with `cat`: `cat data.txt`

    you should see both `data1` and `data2`
15. another way to explore files via the command line is with `nano`, the command to launch teh GNU nano text editor. Open `data.txt` in nano: `nano data.txt`
16. you can navigate through `data.txt` with the arrow keys and will notice a rather old-fashioned User Interface at the bottom of the window. Ctl-X to exit

