# TIL
Things I learned

## Set Keyboard Layout
### console-data
```
# sudo apt-get install console-data
sudo dpkg-reconfigure console-data
```

### keyboard-configuration
```
sudo dpkg-reconfigure keyboard-configuration
```

### loadkeys 
```loadkeys us```

### X-Server
```setxkbmap us```

## ACL (Set File access control list)
### Set default permissions for all new create files in a folder (recnursivly):

```setfacl -Rdm u::rwx,g::rwx,o::r <folder>```
- `-R, --recursive`
- `-d, --default`
All operations apply to the Default ACL. Regular ACL entries in the input set are promoted to Default ACL entries. Default ACL entries in the  input  set  are  discarded. (A warning is issued if that happens). (?)
- `-m`
The `-m` (`--modify`) and `-M` (`--modify-file`) options modify the ACL of a file or directory.  ACL entries for this operation must include permissions.  
The options `-m`, and `-x` expect an ACL on the command line. Multiple ACL entries are separated by comma characters (`,')


