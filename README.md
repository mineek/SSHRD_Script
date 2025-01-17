<h1 align="center">SSH Ramdisk Script</h1>

<p align="center">
  <a href="https://github.com/verygenericname/SSHRD_Script/graphs/contributors" target="_blank">
    <img src="https://img.shields.io/github/contributors/verygenericname/SSHRD_Script.svg" alt="Contributors">
  </a>
  <a href="https://github.com/verygenericname/SSHRD_Script/commits/main" target="_blank">
    <img src="https://img.shields.io/github/commit-activity/w/verygenericname/SSHRD_Script.svg" alt="Commits">
  </a>
</p>

<p align="center">
Create and boot a SSH ramdisk on checkm8 devices
</p>

---

# Prerequsites
1. A computer running macOS/linux
2. A checkm8 device (A7-A11)
3. iOS 12-16 IPSW link
4. libimobiledevice installed on your Mac/Linux
    - [brew](https://brew.sh) or [Procursus](https://github.com/ProcursusTeam/Procursus) is required.
    - brew: `brew install libimobiledevice libirecovery`
    - Procursus: `sudo apt install libimobiledevice-utils libirecovery-utils libusbmuxd-tools`
    - Linux: `sudo apt install libimobiledevice-utils irecovery libusbmuxd-tools`

# Usage
1. Clone and cd into this repository: `git clone https://github.com/verygenericname/SSHRD_Script --recursive && cd SSHRD_Script`
    - If you have cloned this before, run `cd SSHRD_Script && git pull` to pull new changes
2. Run `./sshrd.sh <link to your ipsw>`, **without** the `<>`.
    - you can put your own shsh for the second argument, although optional
3. Place your device into DFU mode
    - A11 users, go to recovery first, then DFU.
4. Run `./sshrd.sh boot` to boot the ramdisk
5. To ssh into the device, open up another terminal window and run `iproxy 2222 22`.
6. In the first terminal window, run `ssh -p2222 root@localhost`
7. Finally, to mount the filesystems, run `mount_filesystems`  
  - /var is mounted to /mnt2 in the ssh session.
8. Have fun!

# Other Stuff
- [Reddit Post](https://www.reddit.com/r/jailbreak/comments/wgiye1/free_release_ssh_ramdisk_creator_for_iphones_ipad/)

You can also reset your iPhone

reset: `./sshrd.sh reset`
