# TIL
Things I learned

## Set Keyboard Layout
### console-data
```bash
# sudo apt-get install console-data
sudo dpkg-reconfigure console-data
```
- :white_large_square: works?

### keyboard-configuration
```bash
sudo dpkg-reconfigure keyboard-configuration
```
- :white_large_square: works?

### loadkeys 
```bash
loadkeys us
```
- :white_check_mark: works on the fly (root permission necessary)
  - tested on ubuntu 14.04 for tty1 in VmWare
- :question: does it survive a reboot? or does it work temporaly?

### X-Server
```bash
setxkbmap us
```
- :white_large_square: works?

## ACL (Set File access control list)
### Set default permissions for all new create files in a folder (recnursivly):

```bash
setfacl -Rdm u::rwx,g::rwx,o::r <folder>
```
- `-R, --recursive`
- `-d, --default`
All operations apply to the Default ACL. Regular ACL entries in the input set are promoted to Default ACL entries. Default ACL entries in the  input  set  are  discarded. (A warning is issued if that happens). (?)
- `-m`
The `-m` (`--modify`) and `-M` (`--modify-file`) options modify the ACL of a file or directory.  ACL entries for this operation must include permissions.  
The options `-m`, and `-x` expect an ACL on the command line. Multiple ACL entries are separated by comma characters (`,')


