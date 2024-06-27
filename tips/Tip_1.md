# TIP 1
_This is a script designed to add, commit, push and pull from a repository_
*You can follow the steps provided here and you will add your scripts to run without long processes*
_Sincerely I owe my thanks to ALX_

# Steps: #
- Open a text editor and create a new file with any name of your choice i used 'gitpush.sh'
- Add this script to the file
```
#!/bin/bash

# Check if a commit or push message is provided
if [ -z "$1" ]; then
    echo "No commit or push message provided. Pulling from repository..."
    
    # Pull from the repository
    git pull
    
    # Check if there were changes pulled
    if [ $? -eq 0 ]; then
        echo "Pull successful."
    else
        echo "You are funny."
    fi
else
    # Add all changes
    git add .
    
    # Commit with the provided message
    git commit -m "$1"
    
    # Push to the repository
    git push
    
    # Check if the push was successful
    if [ $? -eq 0 ]; then
        echo "Push successful."
    else
        echo "Push failed."
    fi
fi
```

- Make it executable with
```chmod +x <filename>```


