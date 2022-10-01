# apple-gmux T2

Work in progress version of apple-gmux for T2 MacBookPros with both Intel and AMD graphics (15 and 16 inch models)

## Install

To install with dkms `sudo dkms install .`

Otherwise, you can do:

```sh
make
sudo rmmod apple-gmux
sudo insmod ./apple-gmux.ko
```

If you see `apple_gmux: No GPE found for gmux` in the kernel log, that's expected and because the ACPI interrupt code is disabled for now.

If you are on a model other than MacBookPro16,1 and this works for you then I'd like to know.

## TODO List

- [x] Read and Write to gmux ports
- [x] Backlight control
- [ ] Switching Display between GPUs
	- [x] To preserve state after resume (so you can resume properly when using the igpu!)
	- [ ] At runtime with vga_switcheroo
		- [ ] Make amdgpu register with vga_switcheroo
		- [x] Make intel card register with vga_switcheroo
- [ ] Interrupts
- [ ] Power up/down dGPU (PWRD+PWG1 acpi methods)
- [ ] Update internal documentation
- [ ] Test on other T2 models once everything should be working
- [ ] Ensure these changes don't cause regressions for pio and indexed models.

## Support Me

If you want to support me see [here](https://github.com/Redecorating#support-me).

