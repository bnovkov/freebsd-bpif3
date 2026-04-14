This repo contains a `genimage` configuration file that builds a FreeBSD SD card image for the [Banana Pi BPI-F3](https://docs.banana-pi.org/en/BPI-F3/BananaPi_BPI-F3) development board.
The `genimage` tool expects input files in the `input` folder and outputs a flashable image into the `images` folder.

## Usage

1. Fetch the archive containing the prebuilt bootloader binaries from the [vendor's page](https://archive.spacemit.com/image/k1/version/bianbu/) and move them to the `input` folder:
```bash
wget https://archive.spacemit.com/image/k1/version/bianbu/v3.0/bianbu-25.04-minimal-k1-v3.0-release-20250725114639.zip
unzip bianbu-25.04-minimal-k1-v3.0-release-20250725114639.zip
cp fw_dynamic.itb env.bin u-boot.itb factory/FSBL.bin factory/bootinfo_sd.bin input/
```
2. Copy your freshly built `loader_lua.efi` and `k1-bananapi-f3.dtb` files into the `input` folder,
3. Build a FreeBSD rootfs image and move it into the `input` folder,
4. Run `genimage`.
