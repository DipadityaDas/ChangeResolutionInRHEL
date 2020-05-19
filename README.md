# Change Resolution In RHEL 8.0 Installed in Oracle Virtual Box

First go to yum.repo.d folder

```Shell
cd /etc/yum.repo.d
```

Then download all the repos files required in RHEL 8

```Shell
git clone https://github.com/DipadityaDas/RHELrepos
```

Then remove the unnecessary files.

```Shell
sudo rm -rf .git
sudo rm LICENSE
sudo rm README.md
```

Then check everything running fine without errors.

```Shell
yum repolist
```

Note: Ignore the **subscription-manager** warning.

First, make sure you’ve installed the latest updates using the instructions above. During installation a kernel module will be compiled and installed. There are a few prerequisites. First you should have installed Development Tools during system installation. If not, use:

```Shell
sudo yum groupinstall "Development Tools" -y
```

Next, install kernel development packages so you can build loadable kernel modules:

```Shell
sudo yum install  kernel-devel elfutils-libelf-devel -y
```

Now insert the VirtualBox Guest Additions CD image using the Devices menu entry on the VM’s window. A pop-up will ask you if you want to run the software on the CD image. Click Run.

## VirtualBox Guest Additions

Adding VirtualBox Guest Additions to the RHEL VM improves the usability in a number of ways:

- Enables copy and paste between the host and VM.
- Eliminates the need for the VM to capture the mouse pointer. The integrated mouse pointer is much smoother.
- The VMs screen is dynamically resizable so you can have more space to edit.
- Folders can be easily shared between the host and the VM making it easy to share source code.