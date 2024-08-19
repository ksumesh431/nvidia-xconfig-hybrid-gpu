# Dual GPU X11 Configuration

This repository contains the X11 configuration file for a system with dual GPUs: NVIDIA GeForce RTX 4060 Max-Q / Mobile and AMD Phoenix1.

## Configuration Details

The `xorg.conf` file in this repository is set up for a dual-monitor configuration:

- Primary GPU: NVIDIA GeForce RTX 4060 Max-Q / Mobile
- Secondary GPU: AMD Phoenix1
- Primary Screen: External display with 3840x2160 resolution
- Secondary Screen: Internal laptop display with 2560x1600 resolution

## Important Notes

1. **Display Resolutions**: The current configuration assumes specific resolutions for each display. You may need to adjust these in the `xorg.conf` file to match your actual display resolutions.

2. **GPU Drivers**: Ensure that you have the appropriate drivers installed for both GPUs:
   - NVIDIA GPU: Uses the `nvidia` driver
   - AMD GPU: Uses the `amdgpu` driver

3. **BusID**: The configuration uses the following BusIDs:
   - NVIDIA GPU: PCI:1:0:0
   - AMD GPU: PCI:6:0:0

   These should match your system's hardware configuration. You can verify these using the `lspci` command.

4. **Mouse Configuration**: The mouse is configured to use `/dev/input/mice`. This is standard for most modern systems but may need adjustment for some setups.

## Usage

To use this configuration:

1. Back up your existing X11 configuration if you have one.
2. Copy the `xorg.conf` file to `/etc/X11/xorg.conf`.
3. Reboot your system or restart your X server.

## Troubleshooting

If you encounter issues:

1. Check your system logs (typically in `/var/log/Xorg.0.log`) for any error messages.
2. Verify that the BusIDs in the configuration match your hardware.
3. Ensure that you have the correct drivers installed for both GPUs.
