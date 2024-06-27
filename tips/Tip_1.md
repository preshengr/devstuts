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
```chmod +x gitpush```

- Move the script to a directory that is included in your system's PATH. A common choice is /usr/local/bin
```
sudo mv gitpush.sh /usr/local/bin/gitpush without the extension.sh
```
Be very sure that the /usr/local/bin/ is added to your PATH and the way to check it is :
```
echo $PATH
```

*Some devices may not have the above you can manually add it using this system:
```
sudo nano ~/.bash_profile or ~/.zshrc
```
then copy:
```
export PATH=$PATH:/usr/local/bin
```

- Reload the profile to see the new updates added to it with:
```
source ~/.bashrc
```
_*Wow you can now use the script from any where within a directory in your shell*_

*Oh let me show you an example*
```
gitpush "This is where your Commit meessage is placed" <this will commit and push your updates to the repo>
```
Or 

```
gitpush #This pull the repo if there is any change
```
_Thanks for Reading more tips will come as we progress in the teachings_
