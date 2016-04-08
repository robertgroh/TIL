# TIL
Things I learned

## Set Keyboard Layout
### console-data
```bash
# sudo apt-get install console-data
sudo dpkg-reconfigure console-data
```
- [ ] works?

### keyboard-configuration
```bash
sudo dpkg-reconfigure keyboard-configuration
```
- [ ] works?

### loadkeys 
```bash
loadkeys us
```
- [x] works on the fly (root permission necessary)
  - tested on ubuntu 14.04 for tty1 in VmWare
- :question: does it survive a reboot? or does it work temporaly?

### X-Server
```bash
setxkbmap us
```
- [ ] works?

## TightVncServer
### Allow sharing of clipboard
On the Server
 - First install autocutsel (`sudo apt-get install autocutsel`)
 - add it (`autocutsel -fork`) to `/USER/.vnc/xstartup`

---
[Source](http://raspberrypi.stackexchange.com/a/4475)


## ACL (Set File access control list)
### Set default permissions for all new create files in a folder (recursively):

```bash
setfacl -Rdm u::rwx,g::rwx,o::r ${FOLDER}
```
- `-R, --recursive`
- `-d, --default`
All operations apply to the Default ACL. Regular ACL entries in the input set are promoted to Default ACL entries. Default ACL entries in the  input  set  are  discarded. (A warning is issued if that happens). (?)
- `-m`
The `-m` (`--modify`) and `-M` (`--modify-file`) options modify the ACL of a file or directory.  ACL entries for this operation must include permissions.  
The options `-m`, and `-x` expect an ACL on the command line. Multiple ACL entries are separated by comma characters (`,')


