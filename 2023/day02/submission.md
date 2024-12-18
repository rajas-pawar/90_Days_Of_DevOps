## Linux Command Mastery: Your DevOps Superpower Unlocked! 🐧🚀


Hey Tech Explorers! 👋 Day 2 of my #90DaysOfDevOps journey is all about cracking the Linux command code - your ultimate gateway to DevOps wizardry! 🧙‍♂️

## 🐧 Embracing the Power of Linux as a DevOps Engineer 🐧

As a DevOps engineer, the world of Linux is a place we call home. It's the foundation of our work, and it's where the magic happens. In this blog post, I want to dive into why Linux is so essential in the DevOps world and share some insights into how we make the most of it.

### 🔍 Why Linux Commands are Your New Best Friend

Imagine having a Swiss Army knife for your computer - that's exactly what Linux commands are! They're not just commands; they're your secret weapons for tech domination. 💥

### 🏁 Mission Objectives for Today

1. 📍 Know Your Location: pwd

What? Prints your EXACT location in the file universe

Why? Because getting lost in the Linux filesystem is NOT an option! 🧭

```
rajas_pawar@LAP181:~$ pwd
/home/rajas_pawar
```

Linux Commands Syntax related to above task ,

```
# Move to a specific path
$ cd path_to_directory

# Quick jump to home directory
$ cd ~

# Return to previous working directory
$ cd -

# Move one directory back
$ cd ..

# Move two directories back
$ cd ../..

# View contents two levels above
$ ls ../..
```
2. 🕵️ Reveal the Hidden Secrets: ls -a

Pro Tip: Those dot files? They're like hidden treasure chests of configuration magic!

Insider Move: -a flag = Show ALL files (even the shy ones)

```
rajas_pawar@LAP181:~$ ls -a
.   .bash_history  .bashrc  .docker  .landscape  .local     .motd_shown  
..  .bash_logout   .cache   .kube    .lesshst    .minikube
```
Linux Commands Syntax related to above task ,

```
# List files and directories in current location
$ ls

# List only .sh script files
$ ls *.sh

# Show inode number of files
$ ls -i

# List only directories
$ ls -d */
```

3. 🏗️ Directory Architect: mkdir -p

Challenge: Create entire directory kingdoms in ONE command

Hack: -p flag = Instant nested directory creation

```
rajas_pawar@LAP181:~$ mkdir -p DevOps/Learning/Day2/Challenges
rajas_pawar@LAP181:~$ tree DevOps
DevOps
└── Learning
    └── Day2
        └── Challenges
```
Linux Commands Syntax related to above task ,

```
# Create a single directory
$ mkdir directoryName

# Create a hidden directory
$ mkdir .NewFolder

# Create multiple directories simultaneously
$ mkdir A B C D

# Create directory in specific location
$ mkdir /home/user/Mydirectory

```

💡 DevOps Reality Check

These aren't just commands - they're your first steps into a larger world:

🚀 Automate like a pro

🔧 Manage complex infrastructures

🌈 Transform from a beginner to a Linux ninja!


