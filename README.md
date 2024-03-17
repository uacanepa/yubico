### yubico notes:
```
/etc/pam.d/sudo
/etc/pam.d/sudo-i

/etc/pam.d/runuser
/etc/pam.d/runuser-l

/etc/pam.d/su
/etc/pam.d/su-l

/etc/pam.d/gdm-password
/etc/pam.d/lightdm

/etc/pam.d/login
```

###### Add the line below after the “@include common-auth” line in the file of the command you want
```
auth       required   pam_u2f.so
```

###### Note: If you have moved the u2f_keys file to /etc/Yubico/u2f_keys as mentioned in section 3, you will need to append authfile and a path to the PAM configuration, as shown below:
```
auth       required   pam_u2f.so authfile=/etc/Yubico/u2f_keys
```
