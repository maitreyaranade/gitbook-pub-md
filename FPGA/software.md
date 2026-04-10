# FPGA development process overview

# Vivado

# Petalinux

PetaLinux is a free Xilinx tool which offers everything necessary to
customize, build and deploy Embedded Linux solutions on Xilinx
processing systems. It enables developers to configure, build and deploy
essential open source and systems software to Xilinx silicon, including:

-   FSBL

-   U-Boot

-   ARM Trusted Firmware

-   Linux

-   Libraries and applications

With this tool developers can customize the boot loader, Linux kernel,
or Linux applications. They can add new kernels, device drivers,
applications, libraries, and boot & test software stacks on the included
full system simulator (QEMU) or on physical hardware via network or
JTAG. Some features of Petalinux include:

1.  **Custom BSP Generation Tools** PetaLinux tools will automatically
    generate a custom, Linux Board Support Package including device
    drivers for Xilinx embedded processing IP cores, kernel and boot
    loader configurations.

2.  **Linux Configuration Tools** PetaLinux includes tools to customize
    the boot loader, Linux kernel, file system, libraries and system
    parameters.

3.  **Software Development Tools** PetaLinux tools integrate development
    templates that allow software teams to create custom device drivers,
    applications, libraries and BSP configurations.

4.  **Reference Linux Distribution** PetaLinux provides a complete,
    reference Linux distribution that has been integrated and tested for
    Xilinx devices. The reference Linux distribution includes both
    binary and source Linux packages including:

    -   Boot loader

    -   CPU optimized kernel

    -   Linux applications & libraries

    -   C & C++ application development

    -   Debug

    -   Thread and FPU support

    -   Integrated web server for easy remote management of network and
        firmware configurations

There are seven independent tools that make up the PetaLinux design
flow.

1.  **petalinux-create** tool either creates a new PetaLinux project
    directory structure or a component within the specified project.

2.  **petalinux-config** tool allows you to customize the specified
    project. Either a project is initialized or updated to reflect the
    specified hardware configuration or a specified component is
    customized using a menuconfig interface.

3.  **petalinux-build** tool builds either the entire embedded Linux
    system or a specified component of the Linux system. This tool uses
    the Yocto Project underneath. Whenever petalinux-build is invoked,
    it internally calls bitbake.

4.  **petalinux-boot** command boots MicroBlaze CPU, Zynq and Zynq
    UltraScale devices with PetaLinux images through JTAG/QEMU. With
    JTAG, images are downloaded and booted on a physical board using a
    JTAG cable connection. With QEMU, images are loaded and booted using
    QEMU, the software emulator.

5.  **petalinux-package** tool packages a PetaLinux project into a
    format suitable for deployment. Based on the target package format,
    the supported formats/workflows are boot(.BIN or .MCS), bsp, and
    pre-built.

6.  **petalinux-util** tool provides various support services to the
    other PetaLinux workflows.

7.  **petalinux-upgrade** PetaLinux tool has system software components
    (embedded SW, ATF, Linux, U-Boot, OpenAMP, and Yocto framework) and
    host tool components (Vivado Design Suite, Xilinx Software
    Development Kit (SDK), HSI, and more). To upgrade to the latest
    system software components, you must install the corresponding host
    tools (Vivado design tools). The petalinux-upgrade command resolves
    this issue by upgrading the system software components without
    changing the host tool components.

## Petalinux Design Flow

1.  **Hardware platform creation** Vivado Design Suite

2.  **Create PetaLinux project** petalinux-create -t project

3.  **Initialize PetaLinux project** petalinux-config
    --get-hw-description

4.  **Configure system-level options** petalinux-config

5.  **Create user components** petalinux-create -t COMPONENT

6.  **Configure the Linux kernel** petalinux-config -c kernel

7.  **Configure the root file system** petalinux-config -c rootfs

8.  **Build the system** petalinux-build

9.  **Test the system on qemu** petalinux-boot --qemu

10. **Deploy the system** petalinux-package --boot

11. **Update the PetaLinux tool system software components**
    petalinux-upgrade --url/--file

## QEMU

QEMU (Quick EMUlator) is an open source, cross-platform, system
emulator. It is an executable that runs on an x86 Linux or Windows
operating systems. QEMU can emulate a full system (commonly referred to
as the guest), such as a Xilinx development boards. The emulation
includes the processors, peripherals, and other hardware on the
development board; allowing one to launch an operating system or other
applications on the virtualized hardware. These applications can be
developed using the exact same toolchain that would be used on physical
hardware. QEMU can also interact with the host machine through
interfaces, such as CAN, Ethernet and USB; allowing real-world data from
the host to be used in the guest machine in real time.

Reasons why QEMU is used as an emulator and testing tool:

-   Remote Development

-   Easier Debugging

-   Easier Testing

-   Developing and Running an OS

-   Hardware Modeling and Verification

-   Safety and Security

QEMU works by using dynamic translation. Instructions are translated
from the guest's instruction set to the equivalent host machine
instructions. The equivalent host instructions are then executed on the
host, and the results of those instructions are then pushed back into
the guest machine.


![QEMU Functionality](images/QEMU.png)


# Version Control: Git, Bitbucket

-   **git config**\
    Utility : To set your user name and email in the main configuration
    file.\
    How to : To check your name and email type in git config --global
    user.name and git config --global user.email. And to set your new
    email or name git config --global user.name = Maitreya Ranade" and
    git config --global user.email = maitreya.ranade@gmail.com"

-   **git init**\
    Utility : To initialise a git repository for a new or existing
    project.\
    How to : git init in the root of your project directory.

-   **git clone**\
    Utility : To copy a git repository from remote source, also sets the
    remote to original source so that you can pull again.\
    How to : git clone \<:clone git url:\>

-   **git status**\
    Utility : To check the status of files you've changed in your
    working directory, i.e, what all has changed since your last
    commit.\
    How to : git status in your working directory. lists out all the
    files that have been changed.

-   **git add**\
    Utility : adds changes to stage/index in your working directory.\
    How to : git add .

-   **git commit**\
    Utility : commits your changes and sets it to new commit object for
    your remote.\
    How to : git commit -m "sweet little commit message"

-   **git push/git pull**\
    Utility : Push or Pull your changes to remote. If you have added and
    committed your changes and you want to push them. Or if your remote
    has updated and you want those latest changes.\
    How to : git pull \<:remote:\> \<:branch:\> and git push
    \<:remote:\> \<:branch:\>

-   **git branch**\
    Utility : Lists out all the branches.\
    How to : git branch or git branch -a to list all the remote branches
    as well.

-   **git checkout**\
    Utility : Switch to different branches.\
    How to : git checkout \<:branch:\> or \*

-   **git stash**\
    Utility : Save changes that you don't want to commit immediately.\
    How to : git stash in your working directory. git stash apply if you
    want to bring your saved changes back.

-   **git merge**\
    Utility : Merge two branches you were working on.\
    How to : Switch to branch you want to merge everything in. git merge
    \<:branch_you_want_to_merge:\>

-   **git reset**\
    Utility : You know when you commit changes that are not complete,
    this sets your index to the latest commit that you want to work on
    with.\
    How to : git reset \<:mode:\> \<:COMMIT:\>

-   **git remote**\
    Utility : To check what remote/source you have or add a new remote.\
    How to : git remote to check and list. And git remote add
    \<:remote_url:\> \*\_git checkout -b \<:branch:\> if you want to
    create and switch to a new branch.

# Scripting

## Shell

Scripts are interpreted, and it's important that the very first two
characters in your script file be the \"#!\" Hash or pound sign and the
exclamation point, sometimes known as bangs, so pound bang should be the
very first two characters. (Eg. #! /bin/bash). Change execute permission
of script file by chmod u+x scriptFile

### Time commands and set variables

Bash has builtin commands.

-   **time** With the time command, you can say time and then another
    command. When that command finishes, bash will report how long it
    took to execute the command. The ouptput of the time command has 3
    values real, user and sys. The real line is how long it took in real
    time like if you had timed it with a stop watch. User and sys are
    CPU times. So how much time the program was actually processing, not
    sleeping, say, or getting preempted by other processes. And user was
    time or instructions in the program itself, and sys was time or
    instructions in the operating system, in the kernel doing something
    for that process.

-   **sleep** With sleep command and for a duration. CPU sleeps for the
    particular duration.

-   **export** Export puts the variable into the environment.

-   **enable** To take a look at the builtin.

-   **compgen minus k** list out the keywords.

Variables:\
Variables in Bash, you assign a value with equal sign. One of the
important things with Bash is no spaces before or after the equal sign.
If the value you want to assign to the variable has any special
characters in it like a space, then make sure you quote it.\
To remove the variable, then you can use the unset Bash command.\
To get the value of a variable, normally, you have to put the dollar
sign in front of it. So echo myvar is \$myvar\
It's important to realize that your shell keeps variables in two
different areas. The area called your environment, or exported
variables, are copied to new processes that you run or, say, new shells
that you run, including a shell script program. So if you want to assign
a variable and then run a shell program to get a value from that
variable, then you need to export it. So in Bash, it's most common just
to use the keyword export. So if you say export mynewvar, then the shell
puts mynewvar in your shell's environment, the set of exported
variables. And whenever it starts a new process, like by running a shell
program, then that new process gets a copy of those variables. They're
not shared. It gets a copy.\
When you create a variable, you can export it at the same time. for eg.
export var=0\
So one of the nice features of a function is that when you change a
variable in a function, it changes the corresponding variable in the
shell. Functions don't get a copy of the variables. They share the
variables.

### Bash startup

When Bash gets started Bash reads some startup files to, say, initialize
some variables. And there's a couple of those in home directory that one
can use to customize settings in Bash. One of them is .bash_profile,
that's read just when Bash is started when you log in. And the file
.bashrc is executed every time a new shell is started.

### Sourcing and aliasing with bash

Another way to execute a shell script is to source it, and one can use
the source command to source a script, or one can use dot space to
source a script. What's different is when you source a script, your
current shell just interprets the commands inside the source script as
if they were done themself. When a script is sourced and the script does
things like assigns a value to a variable, then that's happening in the
calling script itself.For example, sourcing is used to import variable
assignments or definitions of functions. So one can have a script that
defines some functions, and you could just source it, and then you can
call those functions from your script. Another handy thing to do with
Bash is to define alternative, oftentimes shorter alternatives to
commands \"Alias\". To unset an alias, unalias command is used for it.

### echo command

The echo command is how you print a message. There're a few options to
echo:

-   -n : don't print usual trailing newline.

-   -e : tells echo to interpret some special characters.

-   backslash n : is print a newline

-   backslash t : means print a tab character.

-   -E : disables special characters in case you want to see the
    backslash and the n instead of a newline.

Echo is particularly helpful when you want to do file globbing to expand
out the names of things. ls \* shows the contents of the directory
whereas echo \* shows the names of things. Echo is also used for saving
files with the usual file redirection techniques. for eg. \>&2 means
send standard output to the same place as file number two, which is
standard error. This is the technique you use with echo to print error
messages.

### The typeset and declare commands for variables

Local variable is a variable that is private inside of a function. And
when it's changed in the function, it doesn't affect a variable outside
of the function.

This is important because if you write a fairly complicated shell
script, you may have variables you use in the script that you overlook,
and you assign to a variable the same name in a function and you change
the global one. That could be pretty confusing and a tricky bug. So if
you have variables in a function that you only need in the function,
then it's good practice to declare them to be local. And you could do
that by declaring them with the typeset command. If the variable's only
going to have integer values then you can say typeset -i. And that makes
the arithmetic faster. In fact, a little benchmark I did, it was like 10
times faster. Also, if you declare a variable to be an integer then bash
lets you use some integer operations with them.

### Debugging

-   bash prog : run prog don't need execution

-   bash -x prog : echo commands after processing can also do set +/- x
    inside a script to choose which commands to echo.

-   bash -n prog : do not execute commands, check syntax.

-   bash -u : reports usage of unset, variable gives error.

-   lots of echo statements for debugging

-   tee command : redirects to output. eg. cmd \| tee log.file \| \...

-   trap command : similar to breakpoint.

Two more important commands are eval and getopt. For more information
and syntax for any of the commands, please connect to the internet.

## TCL

# CMake

# Linux Commands

## File Commands

-   **ls** Directory listing

-   **ls -al** Formatted listing with hidden files

-   **ls -lt** Sorting the Formatted listing by time modification

-   **cd dir** Change directory to dir

-   **cd** Change to home directory

-   **pwd** Show current working directory

-   **mkdir** dir Creating a directory dir

-   **cat \>file** Places the standard input into the file

-   **more file** Output the contents of the file

-   **head file** Output the first 10 lines of the file

-   **tail file** Output the last 10 lines of the file

-   **tail -f file** Output the contents of file as it grows,starting
    with the last 10 lines

-   **touch file** Create or update file

-   **rm file** Deleting the file

-   **rm -r dir** Deleting the directory

-   **rm -f file** Force to remove the file

-   **rm -rf dir** Force to remove the directory dir

-   **cp file1 file2** Copy the contents of file1 to file2

-   **cp -r dir1 dir2** Copy dir1 to dir2;create dir2 if not present

-   **mv file1 file2** Rename or move file1 to file2,if file2 is an
    existing directory

-   **ln -s file link** Create symbolic link link to file

## Process management

-   **ps** To display the currently working processes

-   **top** Display all running process

-   **kill pid** Kill the process with given pid

-   **killall proc** Kill all the process named proc

-   **pkill pattern** Will kill all processes matching the pattern

-   **bg** List stopped or background jobs,resume a stopped job in the
    background

-   **fg** Brings the most recent job to foreground

-   **fg** n Brings job n to the foreground

## File permission

-   **chmod octal file** Change the permission of file to octal,which
    can be found separately for user,group,world by adding, 4-read(r)
    2-write(w) 1-execute(x). The digits you can use and what they
    represent are: 0: No permission, 1: Execute permission, 2: Write
    permission, 3: Write and execute permissions, 4: Read permission, 5:
    Read and execute permissions, 6: Read and write permissions, 7:
    Read, write and execute permissions.

-   **sudo chown owner:group file** Allows you to change the owner and
    group owner of a file.

## Searching

-   **grep pattern file** Search for pattern in file

-   **grep -r pattern dir** Search recursively for pattern in dir

-   **command \| grep pattern** Search pattern in the output of a
    command

-   **locate file** Find all instances of file

-   **find . -name filename** Searches in the current directory
    (represented by a period) and below it, for files and directories
    with names starting with filename

-   **pgrep pattern** Searches for all the named processes , that
    matches with the pattern and, by default, returns their ID

## System Info

-   **date** Show the current date and time

-   **cal** Show this month's calender

-   **uptime** Show current uptime

-   **w** Display who is on line

-   **whoami** Who you are logged in as Unix/Linux Command Reference

-   **finger user** Display information about user

-   **uname -a** Show kernel information

-   **cat /proc/cpuinfo** Cpu information

-   **cat proc/meminfo** Memory information

-   **man command** Show the manual for command

-   **df** Show the disk usage

-   **du** Show directory space usage

-   **free** Show memory and swap usage

-   **whereis app** Show possible locations of app

-   **which app** Show which applications will be run by default

## Compression

-   **tar cf file.tar** file Create tar named file.tar containing file

-   **tar xf file.tar** Extract the files from file.tar

-   **tar czf file.tar.gz** files Create a tar with Gzip compression

-   **tar xzf file.tar.gz** Extract a tar using Gzip

-   **tar cjf file.tar.bz2** Create tar with Bzip2 compression

-   **tar xjf file.tar.bz2** Extract a tar using Bzip2

-   **gzip file** Compresses file and renames it to file.gz

-   **gzip -d file.gz** Decompresses file.gz back to file

## Network

-   **ping host** Ping host and output results

-   **whois domain** Get whois information for domains

-   **dig domain** Get DNS information for domain

-   **dig -x host** Reverse lookup host

-   **wget file** Download file

-   **wget -c file** Continue a stopped download

## Shortcuts

-   **ctrl+c** Halts the current command

-   **ctrl+z** Stops the current command, resume with fg in the
    foreground or bg in the background

-   **ctrl+d** Logout the current session, similar to exit

-   **ctrl+w** Erases one word in the current line

-   **ctrl+u** Erases the whole line

-   **ctrl+r** Type to bring up a recent command

-   **!!** Repeats the last command

-   **exit** Logout the current session

## Miscellaneous

-   **alias** Give your own name to a command or sequence of commands
