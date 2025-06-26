## What are Asset Packs?

Asset Packs allow you to cusomize your flipper with custom animations, icons and fonts. This guide explains how to install and create your own Asset Packs.

> [!NOTE]
> Asset Packs impact the performance of your Flipper Zero, especially if they contain custom fonts. You can expect more crashes then usual if you use one.

## How to Install Asset Packs

Installing an Asset Pack is a straightforward process. If your browser supports it, you can download the pack directly to your Flipper Zero by connecting it via USB (remember to close qFlipper first). Alternatively, you can download the zip file and transfer it manually.

1.  Open [qFlipper](https://github.com/qFlipper/qFlipper/releases) and connect to your Flipper Zero.
3.  Navigate to the `SD Card` tab and open the `asset_packs` folder. If this folder does not exist, you can create it manually or [reinstall the firmware](Installation#Reinstalling-the-Firmware).
4.  Unzip your downloaded Asset Pack and drag and drop the pack's folder into `SD/asset_packs`. The final structure should look like this: `SD/asset_packs/AssetPackName/<Anims, Icons or Fonts folder(s)>`

To activate the Asset Pack:

1.  On your Flipper, navigate to `Settings` > `Momentum` > `Asset Pack` and select the pack you just installed.
2.  Back out of the menu and the Flipper will restart and apply the new assets.

## Creating Your Own Asset Packs

This section guides you through creating your own asset packs. The process will involve preparing your source images (`.png` files with black and white pixels) and metadata files, then use a script to "pack" them into the format the Flipper uses.

### Prerequisites

Before you begin, you will need to install Python, [the asset packer tool](https://github.com/notnotnescap/mntm-asset-packer), and some required libraries.

1.  Install [Python](https://www.python.org/) (3.10 or newer is recommended).
2.  Open a terminal or command prompt and run this command:
```sh
pip3 install mntm-asset-packer Pillow heatshrink2
```
This will install the `mntm-asset-packer` tool, and some required libraries. If you use [uv](https://docs.astral.sh/uv/) (which will automatically install all dependencies), you can install with:
```sh
uv tool install mntm-asset-packer
```

You can test if the installation was successful by running:
```sh
mntm-asset-packer help
```

### Step 1: Prepare Your Source Files

First, create a main folder to hold all your asset packs. For example, `Desktop/MyAssetPacks`.

Navigate to this folder in your terminal and create a template for your asset pack with the following command:
```sh
mntm-asset-packer create MyCoolPack
```
Your asset pack name can contain spaces, but it's recommended to avoid them to not complicate things.

You can then type `y` and press `Enter` to create examples for `meta.txt` and `manifest.txt` files. This will create a folder with the required structure for your asset pack. You can delete any files or folders you don't need and you will need to modify the `meta.txt` and `manifest.txt` files to suit your assets.

This is an example of an asset pack structure:
![Asset Pack Example Structure](https://user-images.githubusercontent.com/49810075/218661220-cdc750bf-1eee-488e-a194-47371529112c.png)

#### Animations

1.  If there isn't one, create an `Anims` folder inside your pack folder.
2.  Inside `Anims`, create a subfolder for each individual animation (e.g., `MyAnim`).
3.  Place your animation frames, saved as `.png` files, inside the animation's folder (e.g., `.../MyAnim/frame_0.png`, `.../MyAnim/frame_1.png`).
4.  Each animation folder must contain a `meta.txt` file, which defines properties like width, height, and frame rate.
5.  The `Anims` folder must contain a `manifest.txt` file. This file tells the firmware when to display each animation based on the dolphin's level and mood. Note that Momentum Firmware supports levels up to 30.

#### Icons

1.  Create an `Icons` folder inside your pack folder: `.../MyCoolPack/Icons/`.
2.  Organize your icons into subfolders that match the firmware's asset structure (e.g., `Passport`, `RFID`). You can find the complete structure in the firmware source code at [`assets/icons`](https://github.com/Next-Flip/Momentum-Firmware/tree/dev/assets/icons).
3.  **Static Icons**: Save your static icons as `.png` files. No extra configuration is needed.
4.  **Animated Icons**:
    *   Create a subfolder for the animated icon (e.g., `Animations/Levelup_128x64/`).
    *   Place the frames as `.png` files inside this folder.
    *   Add a file named `frame_rate` (no extension) containing a single number for the animation's frame rate.

### Step 2: Pack Your Assets

You can pack your asset pack with:
```sh
mntm-asset-packer pack MyCoolPack
```

If you have multiple asset packs, you can pack them all with:
```sh
mntm-asset-packer pack all
```
You will need to confim by pressing `Enter`.

This will create an `asset_packs` folder in the current directory, containing all packed asset packs. You can then copy this folder to your Flipper Zero's SD card following the instructions in the [Installing Asset Packs](#how-to-install-asset-packs) section.


## Asset Pack Technical Details

This section provides a deeper look at the compiled file formats and structure used by the firmware.

### Compiled Animation Structure

Animations are converted from `.png` sequences into individual `.bm` files, which are bitmaps.

```
SD/asset_packs/
    |-PackName/
        |-Anims/
            |-ExampleAnim/
                |-frame_0.bm
                |-frame_1.bm
                |...
                |-meta.txt
            |...
            |-manifest.txt
```

*   **`meta.txt`**: Contains metadata for each animation (width, height, frame rate, duration).
*   **`manifest.txt`**: Defines the rules for when animations are displayed.

### Compiled Icon Structure

Icons are loaded dynamically. To achieve this, they use special formats and follow the original firmware's naming scheme. This system supports all internal assets.

```
SD/asset_packs/
    |-PackName/
        |-Icons/
            |-Animations/
                |-Levelup_128x64/
                    |-frame_0.bm
                    |...
                    |-meta
            |-Passport/
                |-passport_happy_46x49.bmx
            |...
```

#### Static Icons (`.bmx`)

Since the standard `.bm` format does not store image dimensions, static icons are converted to a custom `.bmx` format. This format prepends the width and height to the pixel data: `[ int32 width ] + [ int32 height ] + [ .bm pixel data ]`.

#### Animated Icons (`.bm` + `meta`)

Animated icons are stored as a sequence of `.bm` frames. Their dimensions and frame rate are stored in a separate binary `meta` file (no extension): `[ int32 width ] + [ int32 height ] + [ int32 frame_rate ] + [ int32 frame_count ]`.

#### Naming and Compatibility Notes

*   The folder structure and icon names should match those in the firmware's [`assets/icons`](https://github.com/Next-Flip/Momentum-Firmware/tree/dev/assets/icons) directory for compatibility.
*   Pixel dimensions in filenames (e.g., `_46x49`) are ignored by the system but are kept for consistency with the original assets and as a sizing hint.
*   Level-specific icons from the original firmware are simplified. For example, `passport_happy1_46x49` becomes `passport_happy_46x49`.

### Other Resources

*   **Flipper Zero Graphics Repo**: A useful resource for graphics development.
