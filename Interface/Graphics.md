The Graphics settings allow you to customize the visual appearance of your Flipper Zero through Asset Packs and animation behaviors. These settings can be found by pressing `UP` on the Desktop and navigating to `MNTM > Interface > Graphics`.

<sup>Default Option: `*`</sup>

## [Asset Pack](Graphics#Asset-Pack)

Asset Packs are a feature exclusive to Momentum Firmware that allows you to load custom Animations, Icons and Fonts without recompiling the firmware. They function as complete theme packages that can change your Flipper's appearance.

- Navigate to `Asset Pack` to select from any [pre-installed](https://github.com/momentum-firmware/asset-packs) or [community-made](https://momentum-fw.dev/asset-packs) packs.
- Packs are loaded externally from the [SD Card](../File-Browser#SD-Card) at `/ext/asset_packs/*`
- Each pack can contain:
    - Custom Animations (stored in `Anims/`)
    - Custom Icons (stored in `Icons/`)
    - Custom Fonts (stored in `Fonts/`, optional)

## [Size Warning](Graphics#Size-Warning)

When selecting an Asset Pack, you *may* see a size warning. This indicates that:

- The pack contains Fonts & Icons that remain loaded in memory
- Large packs may impact available RAM
- The warning provides detailed size information for fonts and icons to help you make an informed decision

<div style="display: flex; align-items: center;">
    <img src="../img/Warning.png" width="320" style="margin-right: 20px;"/>
    <img src="../img/Files.png" width="320"/>
</div>

<sup>Example size warning for the [Pirates Asset Pack](https://github.com/Next-Flip/Momentum-Firmware/wiki/Community-Asset-Packs#pirates)</sup>

## [Anim Speed](Graphics#Anim-Speed)

Controls the playback speed of all animations:

- Default: 100%
- Range: 25% to 300%
- Adjustable in 25% increments
- Affects all animations system-wide

## [Cycle Anims](Graphics#Cycle-Anims)

Determines how often animations change:

- `OFF`: Disable animation cycling
- `Meta.txt`<sup>*</sup>: Use pack's defined timing (if available)
- Time intervals:
    - Short: 15S, 30S
    - Medium: 1M, 2M, 5M, 10M, 15M, 30M
    - Long: 1H, 2H, 6H, 12H, 24H

## [Unlock Anims](Graphics#Unlock-Anims)

Toggle special animations when unlocking the device:

- `OFF`<sup>*</sup>: Disable unlock animations
- `ON`: Enable unlock animations (if pack includes them)

> This page is only a brief overview of the individual Graphics settings. For more detailed information about installing or creating your own Asset Packs, see our [Asset Pack Page](Assets/Asset-Packs).
