# This version is outdated

New version is going to be upstream soon hopefully, and is already in t2 kernels with versions above 6.1.12-2. https://github.com/t2linux/kernel/issues/2 is now the place tracking the status of GMUX on t2 macs.

# apple-gmux T2

Work in progress version of apple-gmux for T2 MacBookPros with both Intel and
AMD graphics (15 and 16 inch models)

## Install

### Enabling the iGPU

Follow [this guide](https://wiki.t2linux.org/guides/hybrid-graphics/).

### Installing the module

#### Arch Based Distros

If you are on an arch based distro and have the
[`Redecorating-t2`](https://github.com/Redecorating/archlinux-t2-packages)
repo, you can install with `sudo pacman -S apple-gmux-t2-dkms-git`.

#### Debian Based Distros

If you are on a Debian or Ubuntu based distro and have the
[adityagarg8.github.io/t2-ubuntu-repo](https://github.com/AdityaGarg8/t2-ubuntu-repo)
repo, you can install with `sudo apt install apple-gmux-t2`.

#### Other Distros

To install with dkms `sudo dkms install .`

Otherwise, you can do:

```sh
make
sudo modprobe -r apple-gmux
sudo modprobe ./apple-gmux.ko
```

## TODO List

- [x] Read and Write to gmux ports
- [x] Backlight control
- [ ] Switching Display between GPUs
	- [x] To preserve state after resume (so you can resume properly when using the igpu!)
	- [ ] At runtime with vga_switcheroo
		- [ ] Make amdgpu register with vga_switcheroo
		- [x] Make intel card register with vga_switcheroo
	- [ ] Get the switched to GPU to output to the display
- [ ] Interrupts
- [ ] Power up/down dGPU
	- [x] Power Down
	- [ ] Power Up
		- [x] mbp15,x
		- [ ] mbp16,x
	- [ ] ACPI PWRD, PWG1
- [ ] Update internal documentation
- [ ] Test on other T2 models once everything should be working
- [ ] Ensure these changes don't cause regressions for pio and indexed models.

## Support Me

If you want to support me see [here](https://github.com/Redecorating#support-me).

