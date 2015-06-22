# Installing composer on the Synology NAS
First you need the following things:

- Successful login via SSH, could either be via root or a standard user. [Find out how](../../System/SSH/Gaining_access_via_ssh.md)
- Access to the Synology DSM interface.

## Downloading Composer
Log in to your NAS by running ```ssh yourUserName@NAS_IP_OR_DOMAIN```, and fill in your password if you don't have a
public key authentication. Next run ```curl -s https://getcomposer.org/installer | php```.

## Installing Composer
Now you have Composer downloaded, but you can only run it by using the full path. To make it global run 
```mv composer.phar /usr/bin/composer```, this will move composer.phar to /usr/bin and rename it to composer.
Make sure you do this as a privileged user, like root for example.

You can now use composer by running ```composer --help```.

## Troubleshooting
> I get PHP Warning:  Unknown: open_basedir restriction in effect. File(/usr/bin/composer) is not within the allowed path(s)  

This means PHP isn't allowed to run from your /usr/bin file, go to your DSM interface > Control Panel > Web Services > 
PHP Settings (tab) and check Customize PHP open_basedir. Add ```:/usr/bin/composer``` at the end of the line to allow
composer to be run. You can also add ```:/usr/bin``` to the line but this will allow PHP to execute ALL of your binary
files, this is unsafe, but you can do it if you want to.