#### Permission Manipulation
chmod: Change Mode
change permission to file to owner, group and other

### permission with numeric mode
- readable = 4
- writeable = 2
- executeable = 1

> using the incremental method to combine permission

#### Example:
```
4 : readable
4 + 2 = 6 : readable + writeable
4 + 1 = 5 : readable + executable
```

- 0 = ---
- 1 = --x
- 2 = -w-
- 3 = -wx
- 4 = r--
- 5 = r-x
- 6 = rw-
- 7 = rwx
##

> change file or directory mode

- first number is for owner
- second number is for group
- third number is for other

#### Example sommand:
```bash
chmod 750 filename
```
that command will change file/directory mode to owner with full privilege, group member can only read and execute without write file, and prohibit other from accessing file

---

### permission with symbolic mode
- r = readable
- w = writeable
- x = executeable

#### Increase and Decrease permission
you can increase and decrease permission with (+ and -), but it apply to all member
Example:
```bash
chmod +x filename
```
will give all member or (owner, group, and other) permission to execute that file
if you only want specific member for set permission, you can add using alias in front of operator 

- u = owner
- g = group
- o = other
- a = all
  
#### Example
```bash
chmod u+x,g+x filename
```
it will increase execute permission only to owner and group

if the owner and group have same permission, you can combine it
```bash
chmod ug+x filename
```

---

you can also set permission persis
#### Example
```bash
chmod u=rwx,g=rx,o= filename
```
> it will give owner the full privilege and group can only read and execute file

##

### Sticky Bit
Sticky Bit functions to limit the right to delete or change file names in a directory.
if some folder have sticky bit, the one can change name and delete the file is owner of that directory, owner of file and super user.
to add sticky bit to the folder is using (+t)

#### Example
```bash
chmod +t filename
chmod +t,o-x filename # to make other can't execute file
```

---

### Default permission filte

Umask,the simple thing of umask is you set a forbidden permission for every file or folder you create after you run umask for that session, 
the file permission is will decrease with your umask value

#### Example

```bash
umask 027
```
if you create some new directory, 
the permission of that folder is will be ```rwxr-x---``` and ```rw-r-----``` for file, 
because you set it so that there are no rules for owners, the group is not allowed to write, 
and other people are not allowed to do anything.

default directory mask value is ```777```
and default file mask value is ```666```

---

### SetFacl
is a much more **modern and flexible** permissions system than traditional `chmod`.

