# Day 7 : Understanding package manager and systemctl

### What's a Package Manager (In Human Terms)? 📦

Think of a package manager as the App Store for Linux. But instead of clicking shiny buttons, we use command-line tools like apt (for Ubuntu) or yum/dnf (for CentOS). It's like having a personal assistant who:

- Knows where to find the software you need
- Handles all the installation details
- Makes sure everything plays nicely together
- Keeps track of updates

### ✨ Different kinds of package managers

There are various types of package managers used in different Linux distributions:

— apt (for Debian-based systems like Ubuntu):
```
    sudo apt update
    sudo apt install package_name
    sudo apt remove package_name
```
— yum (for Red Hat-based systems like CentOS):
```
    sudo yum install package_name
    sudo yum remove package_name
```
— dpkg (low-level for Debian-based systems):
```
    sudo dpkg -i package.deb
    sudo dpkg -r package_name
```
— RPM (for Red Hat-based systems):
```
    sudo rpm -ivh package.rpm
    sudo rpm -e package_name
```
These package managers facilitate the installation, removal, and management of software packages on Linux distributions, catering to the specific needs and package formats of each distribution family.


### Real-World Scenario: Setting Up a DevOps Workstation 🖥️

Let's say you're starting a new job as a DevOps engineer, and you need to set up your development environment. Your task list includes installing Docker for containerization and Jenkins for CI/CD. Here's how we tackle this in the real world.

#### Installing Docker: The Ubuntu Way 🐋
- Update packages:
```
  sudo apt update
  sudo apt-get install docker.io
```
- Check Docker status:
```
  sudo service docker status
```
- Enable Docker on boot: (Ensures Docker starts automatically whenever the system boots, making it ready to use without manual intervention.)
```
  sudo systemctl enable docker
```

#### Jenkins Installation: Because CI/CD is Life 🔄
- Update packages:
```
    sudo apt update
```
- Install Java:
```
    sudo apt install -y openjdk-11-jdk
```
- Add Jenkins repository and install:
```
    wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
    sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
    sudo apt update
    sudo apt install -y jenkins
```
- Start and enable Jenkins:
```
    sudo systemctl start jenkins
    sudo systemctl enable jenkins
```
- Check Jenkins status:
```
    sudo systemctl status jenkins
```
## Hands-on Time: Let's Break Things (Safely)! 🛠️

### Task 1: Investigating Docker Service 🐋

First, let's see what our Docker service is up to:

# Check Docker service status
sudo systemctl status docker

You'll see something like this:
```
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: active (running) since Wed 2024-01-05 10:30:15 UTC; 2h 15min ago
       Docs: https://docs.docker.com
   Main PID: 1234 (dockerd)
      Tasks: 8
     Memory: 45.6M
        CPU: 890ms
```
💡 Pro Tip: Look for the "Active" line - if it says "active (running)", you're golden!

### Task 2: Playing Start/Stop with Jenkins 🎮

Let's have some fun stopping and starting Jenkins (don't worry, we can fix it!):

# First, let's check the current status
```
sudo systemctl status jenkins
```
# Time to stop Jenkins
```
sudo systemctl stop jenkins
```
# Check status again - notice the difference?
```
sudo systemctl status jenkins
```
Before stopping:
```
● jenkins.service - Jenkins Continuous Integration Server
 ```    Active: active (running) since Wed 2024-01-05 09:00:00 UTC; 3h 45min ago

After stopping:
```
● jenkins.service - Jenkins Continuous Integration Server
     Active: inactive (dead) since Wed 2024-01-05 12:45:15 UTC; 5s ago
```
