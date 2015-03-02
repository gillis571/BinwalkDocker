**Introduction**

Binwalk is a firmware analysis tool designed for analyzing, reverse engineering and extracting data contained in firmware images.

Written primarily in Python, it is fully scriptable and easily extendable via custom signatures and plugins.

If you want to hack firmware, binwalk can help.

**Pulling the  Binwalk Image**

    docker pull gillis57/binwalk

**Running the Binwalk Program**

    docker run --rm -v gillis57/binwalk [binwalk variables] [Target Filepath]
    


***Important Note Regarding Target File Locations***

The -v variable should be set to allow for the container to access the host machine file paths. This will allow for binwalk to scan firmware images which are being stored on the host machine, and prevent the user from having to access the container directly to `wget` firmware images directly to the machine itself. 

**If you do *NOT* set the -V variable**

In order to execute scans of images without the V variable set in your run command, you must access the container directly utilizing the interactive terminal. The following command will allow you to connect

    d run --rm -ti --entrypoint bash binwalk 
    
After connecting to the container, you can the `wget` the  file that you want. And run binwalk on it from the interactive shell.
*Note: The container will delete any information you pull into the container after you exit, due to the prescence of the `--rm` flag. 
