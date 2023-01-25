# Week 1 Lab Report: Remote Access

## Setting up the terminal
1. I first installed VSCode from the [VSCode Website](https://code.visualstudio.com/), using the appropriate download link for my OS (Mac, in my case) and unzipping the .zip after it finished downloading.
2. After opening my newly installed VSCode, I then opened the terminal within the application (ctrl+shift+\`) and configured the profile to use bash rather than the default option by using the command pallette to set the default terminal profile.

![Terminal Configuration Screenshot](https://user-images.githubusercontent.com/25190789/211907513-1063ea58-cf3c-471d-93ba-3f2fb7da3670.png)

## Remotely connecting
1. After resetting the password for my course-specific account and waiting for it to update, I remotely connected to it in the terminal with the command `$ ssh cs15lwi23akr@ieng6.ucsd.edu`, answering `yes` and entering my password as prompted. This command connects to the `cs15lwi23akr` user on the `ieng6.ucsd.edu` server via ssh, allowing me to remotely run terminal commands on it.

![Remote Connection Screenshot](https://user-images.githubusercontent.com/25190789/211907800-f0963395-b8b9-40a9-b69e-8823aa721432.png)

## Trying commands
1. I then explored the file structure of the remote connection, experimenting with basic file navigation commands like `cd` (change directory), `ls` (list), and `pwd` (print working directory). In the screenshot below, I printed the current working directory, moved to the home directory, printed the current working directory again, moved to the parent folder, and listed all the files/folders in that directory. I then navigated to the `public/` directory and listed the files/folders there as well.
2. Finally, I logged out of the remote server.
  
![Commands Screenshot](https://user-images.githubusercontent.com/25190789/211908084-bb8a7367-4fe6-4d7b-b601-d74acddb217f.png)
