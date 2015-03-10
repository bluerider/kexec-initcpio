# kexec-initcpio
Initcpio scripts to kexec into a new kernel.
One particular use case is using a stable LTS kernel on a separate boot partition to boot into a btrfs volume which manages kernel versions. In other words, use a kernel to boot into a version controlled kernel.

Add {hook,install}/kexec to /usr/lib/initcpio/
Add kexex to hooks in /etc/mkinitcpio.conf
Run mkinitcpio -p linux

** Note you should build two kernels, one that doesn't have the kexec hook and one that does. Use the one that does to boot into the one that doesn't or else you'll  have a booting kexec loop.