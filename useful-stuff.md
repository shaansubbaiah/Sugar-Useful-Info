# Random Useful Snippets

Useful Sugar locations

shell.log `~/.sugar/default/logs/shell.log`

apisocket `/usr/lib/python3.7/dist-packages/jarabe/apisocket.py`

installed activities (olpc 18.04) `/usr/share/sugar/activities/`

---

## Multitail

To use multitail to view latest log.

```bash
multitail -iw "*YOUR_PACKAGE_NAME*" 1 -m 0
```

Multitail config for highlighting:

```log
# Paste the snippet into /etc/multitail.conf
# Or save as .multitailrc in the home directory

# Sugar
colorscheme:sugar
cs_re:green:DEBUG
cs_re:red:^(([a-zA-Z]*Error)|Traceback).*$
cs_re:yellow:^.*(Warning|WARNING).*$
cs_re_s:blue:([0-9]{10,}\.[0-9]{6,})
#
```

```bash
multitail -CS sugar -iw "*YOUR_PACKAGE_NAME*" 1 -m 0

# or from anywhere

cd ~/.sugar/default/logs/ && multitail -CS sugar -iw "*YOUR_PACKAGE_NAME*" 1 -m 0
```

---

## SSH

```bash
# regular SSH

ssh <user>@<domain or ip>

# SSH with X support (activities will open in local pc)

ssh -X <user>@<domain or ip>
```

---

## Debugging

Use GDB to debug a Sugar activity

```bash
# in the activity directory eg. /usr/share/sugar/activities/Browse.activity
gdb python3
run /usr/bin/sugar-activity3
```

Use PDB to debug a Sugar activity

```bash
python3 -m pdb /usr/bin/sugar-activity3 .

#add breakpoint in code using:
import pdb; pdb.set_trace()
```

---

## Git stuff I keep forgetting

```bash
# LIST ALL REMOTES
git remote -v

# ADD A REMOTE
git remote add <SOME_NAME> <REPO_GIT_LINK>
```

```bash
# MERGE 2 COMMITS INTO 1
git rebase --interactive HEAD~2

# change
# pick b76d157 b
# pick a931ac7 c
# to
# pick b76d157 b
# squash a931ac7 c

# edit commit message

# force push
git push -u -f origin master
```

```bash
# ADD YOUR CHANGES OVER A REPO EG. ORIGIN MASTER
git pull --rebase origin master
```

```bash
# MODIFY THE LAST COMMIT
git commit --amend --no-edit

# omit `--no-edit` you dont want to edit the commit message

# force push
```

---

## Setup Sugar Live Build for Use

```bash
su
apt install sudo openssh-server multitail neofetch python3-pip

su
sudo adduser ssbc sudo
```

---

## Clone the master branch of all activities
(Ideally for Sugar Live Build)

```bash
#!/bin/sh

repos="
https://github.com/sugarlabs/browse-activity
https://github.com/sugarlabs/terminal-activity
https://github.com/sugarlabs/calculate-activity
https://github.com/sugarlabs/chat
https://github.com/sugarlabs/imageviewer-activity
https://github.com/sugarlabs/log-activity
https://github.com/sugarlabs/memorize-activity
https://github.com/sugarlabs/Pippy
https://github.com/sugarlabs/read-activity
https://github.com/sugarlabs/write-activity
https://github.com/sugarlabs/jukebox-activity
"

for repo in $repos;
do
    link="${repo}.git"
    folder_name=$(basename $repo)

    git clone $link $folder_name

    cd $folder_name
        python ./setup.py dev
    cd ..
done
echo "--- Finished ---"
```

You may want to also move the preinstalled activities from /usr/share/sugar/ somewhere else

```bash
cp -R /usr/share/sugar/activities /usr/share/sugar/activities-backup
rm -rf /usr/share/sugar/activities
```

---

## Install an .xo bundle from terminal

```
sugar-install-bundle <name of xo file>
```

---

## Install Help Activity

1. `git clone https://github.com/sugarlabs/help-activity.git`
2. install python-sphinx `apt install python-sphinx`
3. run `make html`
4. run `python setup.py dist_xo`
5. install the .xo bundle from the terminal ^^

---

## Other

Add this to application menu to fix virt-manager options in Plasma globalmenu.

`KDE_NO_GLOBAL_MENU=1 virt-manager`

---

Add user with root access Debian, where foo is username.

`sudo adduser foo sudo`

---

View different versions of a package available.

```bash
apt-cache policy <package name>
```

---

Add unstable, sources to Debian

```
# /etc/apt/sources.list
deb http://deb.debian.org/debian testing main contrib
deb-src http://deb.debian.org/debian testing main contrib
deb http://deb.debian.org/debian unstable main contrib
deb-src http://deb.debian.org/debian unstable main contrib
```

---

Check GTK version

```
dpkg-query -W libgtk-3-bin
```

---

Prevent suspend on Debian

`sudo systemctl unmask sleep.target suspend.target hibernate.target hybrid-sleep.target`

---

Debian Live username:password
`user:live`

---

Set a static IP for VMWare Workstation VM's
```
@SEE https://medium.com/shehuawwal/how-to-assign-a-static-ip-address-to-a-vmware-workstation-vm-de7773f9ef19

# TLDR:
# C:\ProgramData\VMware\vmnetdhcp.conf
# VMnet8 is the network it is running in. This can be found out in the network manager.
# Add these to the end of the file
host VMnet8 {
    hardware ethernet 00:0C:29:DB:22:57;
    fixed-address 192.168.244.130;	
}
```

---

Quozl's method to debug Terminal from Terminal :O

>    To debug the Terminal activity, I've had to use the activity
>    itself to launch another instance using pdb and sugar-activity3. At
>    the breakpoint, I've had to switch back to the initial session by
>    going to the F3 menu and then selecting the first instance. I'm not
>    able to launch activities in the remote OS from a console SSH'd to
>    it, 'GDK_IS_SCREEN' error. I have also tried ctrl+alt+F2 to TTY2 but
>    I get the same error. Is there a way to launch an activity in the
>    remote VM OS from a local console SSH'd to the VM? (Just found out
>    about the -X parameter while using SSH which lets me launch the
>    activity on my local system, but it isn't the solution to the above
>    problem)

Two possible solutions;

1.  clone the Terminal activity to a directory ~/DebugTerminal, and
    change the bundle_id, then "./setup.py dev",

2.  read up on how to use the screen(1) program, start Terminal, start
    screen, SSH in from your host, if you SSH as root then become the
    Sugar user with `su - user`, share the screen with `screen -x`.

---

## Useful Links

PyGObject - https://lazka.github.io/pgi-docs/

Sugar Toolkit - https://developer.sugarlabs.org/sugar3/

Sugar Debian Repository - https://salsa.debian.org/pkg-sugar-team/

Rewriting Commit History - https://www.atlassian.com/git/tutorials/rewriting-history
