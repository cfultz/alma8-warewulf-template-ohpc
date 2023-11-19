# AlmaLinux 8 Warewulf Template for OpenHPC

I'm in the process of converting my current OpenHPC cluster to AlmaLinux from Rocky. The instructions provided by OpenHPC have the defaults of Ubuntu, Debian, CentOS, OpenSuse, SLES, and Rocky. But what if you want AlmaLinux? Use this template! 

#### Please Note
Your master node will already need to have AlmaLinux 8.8 installed. To convert your CentOS 8 or Rocky 8 system in place, use [almalinux-deploy](https://github.com/AlmaLinux/almalinux-deploy) so you can save the hassel of reinstallation.

## How to use

Copy the contents of ``alma-8.tmpl`` into a new file in ``/usr/libexec/warewulf/wwmkchroot`` or you can clone it if you have ``git`` installed on your master server:

As root:
```
git clone https://github.com/cfultz/alma8-warewulf-template-ohpc/
chmod 644 alma-8.tmpl
##Setup chroot
export CHROOT=/opt/ohpc/admin/images/alma8
##Build the initial image
wwmkchroot -v alma-8 $CHROOT
```

Then continue following the guide as normal. You're simply swapping out the ``rocky-8`` for ``alma-8``.

This *should* work just fine (as it seems to be during my testing), but if there is anything I need to change, put in a pull request.
