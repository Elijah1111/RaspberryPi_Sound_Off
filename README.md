# Raspberry Pi Sound Off

This handy bash script will email the ip of the Raspberry Pi to your email with crontab, ssmtp, and mailutils

## Prerequisites
Install ssmtp and mailutils
* [SSMTP](https://wiki.archlinux.org/index.php/SSMTP) - Sends Mail to The Mail Host
* [Mailutils](https://mailutils.org/) - The Mailing Service Used

Create a gmail account to use to send emails.
## Installing
Download the bash script
### Configuring
edit /etc/ssmtp/ssmtp.conf to contain

```
root=username@gmail.com 
mailhub=smtp.gmail.com:587 
rewriteDomain=gmail.com
hostname=localhost
UseSTARTTLS=YES 
AuthUser=username 
AuthPass=password 
FromLineOverride=YES
```

open crontab with
```
crontab -e
```
and add the line
```
@reboot sleep 30 && /DIR_TO_SENDIP
```
## Authors
* **Elijah Mt. Castle** *Initial work* - [Elijah1111](https://github.com/Elijah1111)
* **Ben Wagley** - *Idea and Assistance* - [Website](http://bwagley.com/)
