## 📂 Task 1: The Directory Generator (Your Project Setup Buddy!)

### Problem Statement with solution :

Ever had to set up 50 folders for a new microservices project ? Or create test directories for each sprint? I feel your pain! Here's a cool script I built that does it in seconds:
```
#!/bin/bash

# Check if exactly 3 arguments are passed, else show usage and exit
if [ $# -ne 3 ]; then
    echo "Usage: $0 <DirectoryName> <StartNumber> <EndNumber>" # Usage message
    exit 1 # Exit with error code 1 if arguments are invalid
fi

BASE_NAME=$1 # The base name for directories (first argument)
START=$2     # Start number for directory creation (second argument)
END=$3       # End number for directory creation (third argument)

# Loop from start to end and create directories
for (( i=$START; i<=$END; i++ )); do
    mkdir "${BASE_NAME}${i}" # Create directory with the base name and current number
    echo "Directory ${BASE_NAME}${i} created!" # Print success message
```
- How it Works:

1. Accepts three arguments: directory name, start number, and end number.

2. Uses a for loop to generate directory names dynamically.

3. Validates input arguments to avoid errors.

- Example Usage:
```
chmod 777 task1.sh  # Permission granted
./task1.sh day 1 50 # Final Run
```
**This command creates directories from day1 to day50.**

- 🎯 Real-World Usage (For Example):
```
# Setting up microservices
./createDirs.sh microservice 1 10

# Creating sprint test folders
./createDirs.sh sprint 22 30

# Setting up deployment environments
./createDirs.sh env 1 4  # Creates env1 (dev), env2 (staging), etc
```


## 💾 Task 2: The Smart Backup System

### Problem Statement with solution :

Picture this: It's Friday afternoon, you're about to deploy to production, and you need a quick backup. Here's your new best friend:
```
#!/bin/bash

# Create a backup directory with the current date and time as part of its name
BACKUP_DIR="/home/rajas_pawar/DevOps/Learning/day5/day2/backup_$(date +%Y%m%d_%H%M%S)" 
mkdir -p "$BACKUP_DIR" # Create the backup directory (if it doesn't exist)

# Copy all files and directories from the current directory to the backup directory
cp -r * "$BACKUP_DIR"

# Print a success message with the path to the backup directory
echo "Backup completed successfully! Files saved in $BACKUP_DIR."
```
### ⏰ Understanding Cron: Your DevOps Time Manager!

Ever wondered how Netflix updates its content library at midnight or how your favorite apps perform daily backups? Enter Cron - your 24/7 automation scheduler! Let me break this down with real examples:

- 🔄 Cron Format Explained
```
# Format:
# * * * * * command
# │ │ │ │ │
# │ │ │ │ └── Day of the week (0-7, where both 0 and 7 represent Sunday)
# │ │ │ └──── Month (1-12)
# │ │ └────── Day of the month (1-31)
# │ └──────── Hour (0-23)
# └────────── Minute (0-59)
```
- 🛠️ Quick Setup Guide:

1. Open your crontab:
```
crontab -e
```
2. Add your schedule:
```
# Example: Daily backup at 2 AM
0 2 * * * /path/to/backup_script.sh
```
3. Verify your cron jobs:
```
crontab -l
```

#### 🚀 DevOps-Specific Examples:

1. CI/CD Pipeline Maintenance
```
# Clean up old Docker images every night at 1 AM
0 1 * * * docker system prune -f

# Refresh staging environment every Monday at 3 AM
0 3 * * 1 /scripts/refresh_staging.sh
```

2. Application Health Checks
```
# Check API health every 2 minutes
*/2 * * * * curl -s http://api-health-check.com/status

# Restart application if memory usage is high (every 15 minutes)
*/15 * * * * /scripts/memory_check.sh
```

## 👥 Task 3: The DevOps Team Manager

Picture this: Your company just onboarded 50 new developers, each needing specific access levels, passwords, and group permissions. Manual setup? That's so 2010! Let's automate this!

👥 The Bulk User Creator (Your HR's Best Friend!
```
#!/bin/bash

echo "Starting bulk user creation..."

# Read usernames from the input file
input="users.txt"
while IFS= read -r username
do
    # Check if the user already exists
    if id "$username" &>/dev/null; then
        echo "User $username already exists!"
        continue
    fi
    
    # Create the user with a home directory and default shell
    sudo useradd -m -s /bin/bash "$username"
    echo "Created user: $username"
    
    # Create default workspace directory and set ownership
    sudo mkdir -p "/home/$username/workspace"
    sudo chown -R "$username:$username" "/home/$username/workspace"
    
done < "$input"

echo "Bulk user creation completed!"
```

- Create users.txt:
```
rajas.pawar
ram.thakur
trisha.mali
```
