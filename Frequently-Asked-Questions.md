> [!WARNING]
> This documentation is still a work in progress and will contain many more answers to common questions and issues.
>
> If a question you have is not here yet, you can check the [faq](https://discord.gg/juBGZ5fP7H), [general](https://discord.gg/CyZN9JSA4j), [flipper-noobs](https://discord.gg/xJx824rDd9), [help](https://discord.gg/68jcdsPnSx) or any other channels in the [Discord](https://discord.gg/momentum) for solutions.

## Table of Contents

- [Will I lose data installing a new version?](#will-i-lose-data-installing-a-new-version)
- [Mainline release or dev build?](#mainline-release-or-dev-build)
- [Flipper says "Update failed"?](#flipper-says-Update-failed)
- [Stuck in "infinite loop" after updating](#stuck-in-infinite-loop-after-updating)

## [Will I lose data installing a new version?](#will-i-lose-data-installing-a-new-version)

No, the firmware is installed to the Flipper's internal storage and all your data is external on the SD card. Your data is unaffected by updates.

## [Mainline release or dev build?](#mainline-release-or-dev-build)

Mainline releases normally follow the update schedule of the upstream firmware ([OFW](https://github.com/flipperdevices/flipperzero-firmware)), and encompass all the features and improvements that have been added along the way. While dev builds are for incremental changes and bug fixes leading up to a full release, and give us time to try new things, they are usually just as stable as the Mainline.

If you are unsure, or want to update less often, the [Mainline release](https://github.com/Next-Flip/Momentum-Firmware/releases) will work just fine.

Release pings for both can be found in these Discord channels: [`#mainline-releases`](https://discord.com/channels/1211622338198765599/1213549820271132802) · [`#dev-builds`](https://discord.com/channels/1211622338198765599/1213020009153167390).

## [Flipper says "Update failed"?](#flipper-says-Update-failed)

Most installation errors stem from unsupported, low quality or incorrectly formatted SD cards. If you are formatting on your pc rather than the Flipper, make sure to use either `exFAT` or `FAT32`.

#### Repair in qFlipper

1. Hold `BACK` + `LEFT` for 5 seconds
2. Connect your Flipper to your computer via USB
3. Open [qFlipper](https://github.com/Next-Flip/qFlipper) and click `Repair`
4. Install Momentum again from the [usual sources](https://github.com/Next-Flip/Momentum-Firmware/wiki/Installation#installation-methods)

#### Format your SD card through the Flipper

1. On the Desktop click `UP`
2. Open `Settings > Storage`
3. Click `Format SD card` <sup>1</sup>

## [Stuck in "infinite loop" after updating](#stuck-in-infinite-loop-after-updating)

If your Flipper is stuck in an infinite loop after updating, it may be due to a corrupted SD card or an incompatible files due to a previous installation of another firmware. The bug is still not very well understood at this time, but a simple reformatting should do the trick.

1. Remove the SD card from your Flipper Zero and let it boot
2. Reinsert the SD card
3. Navigate to and run `Settings > Storage > Format SD card` <sup>1</sup>
4. Reinstall Momentum from any of our [installation methods](https://github.com/Next-Flip/Momentum-Firmware/wiki/Installation)

---

<sup>1. *WARNING*: This will delete all the data on the SD card and you'll need to install again. Refer to the [Backup methods](https://github.com/Next-Flip/Momentum-Firmware/wiki/Installation#back-up-your-data) before proceeding.</sup>
