# Change Home Directory in Ubuntu
## To set the home directory to /data/home when creating a new user in Ubuntu 22.04, you can modify the user creation process or update the default configuration. Here's how you can achieve this:
1. Modifying User Creation Process:
   When creating a new user manually using the adduser command, you can specify the home directory using the --home option. Here's how you can do it:
   ```
   sudo adduser --home /data/home username
   ```
   Replace username with the desired username for the new user. This command will create the user with the specified home directory /data/home.
2. Updating Default Configuration:
   To make /data/home the default home directory for new users created using system tools or graphical interfaces, you can update the default configuration.

Edit the /etc/default/useradd file using a text editor such as nano or vim:
```
sudo nano /etc/default/useradd
```
Find the line that starts with HOME= and modify it to set the default home directory:
```
HOME=/data/home
```
Save the changes and exit the text editor. Now, whenever a new user is created using system tools or graphical interfaces, the home directory will default to /data/home.

After making these changes, you can create new users, and their home directories will be set to /data/home automatically.
