The Main Menu settings allow you to customize the appearance and functionality of your Flipper Zero's main menu. These settings can be found by pressing `UP` on the Desktop and navigating to `MNTM > Interface > Mainmenu`.

<sup>Default Option: `*`</sup>

## [Menu Style](Mainmenu#Menu-Style)

Main menus are custom made interfaces that are used for launching apps or files, and potentially showing useful info like time, battery, or the flipper's device name.

Momentum Firmware comes with 9 different styles to choose from, but anyone can design their own and create a [PR](https://github.com/momentum-firmware/firmware/pulls) to have it included in the firmware!

<table>
<tr>
    <th>Style</th>
    <th>Info</th>
    <th>Preview</th>
</tr>
<tr>
    <td><b>List</b><br>Traditional list view with simple navigation</td>
    <td align="center">&#10007;</td>
    <td><img src="../img/Menu-List.png" width="200"/></td>
</tr>
<tr>
    <td><b>Wii</b><br>Nintendo Wii inspired horizontal menu</td>
    <td align="center">&#10007;</td>
    <td><img src="../img/Menu-Wii.png" width="200"/></td>
</tr>
<tr>
    <td><b>DSi<sup>*</sup></b><br>Nintendo DSi inspired grid layout</td>
    <td align="center">&#10007;</td>
    <td><img src="../img/Menu-DSi.png" width="200"/></td>
</tr>
<tr>
    <td><b>PS4</b><br>PlayStation 4 inspired horizontal menu</td>
    <td align="center">&#10003;</td>
    <td><img src="../img/Menu-PS4.png" width="200"/></td>
</tr>
<tr>
    <td><b>Vertical</b><br>The only vertical scrolling menu</td>
    <td align="center">&#10007;</td>
    <td><img src="../img/Menu-Vertical.png" width="200"/></td>
</tr>
<tr>
    <td><b>C64</b><br>Commodore 64 retro inspired menu</td>
    <td align="center">&#10003;</td>
    <td><img src="../img/Menu-C64.png" width="200"/></td>
</tr>
<tr>
    <td><b>Compact</b><br>Minimal compact style with tiny text</td>
    <td align="center">&#10007;</td>
    <td><img src="../img/Menu-Compact.png" width="200"/></td>
</tr>
<tr>
    <td><b>MNTM</b><br>The MNTM style menu (made by <a href="https://github.com/HaxSam">HaxSam</a>)</td>
    <td align="center">&#10003;</td>
    <td><img src="../img/Menu-MNTM.png" width="200"/></td>
</tr>
<tr>
    <td><b>CoverFlow</b><br>Horizontal CoverFlow style (made by <a href="https://github.com/Next-Flip/Momentum-Firmware/pull/314">CodyTolene</a>)</td>
    <td align="center">&#10007;</td>
    <td><img src="../img/Menu-CoverFlow.png" width="200"/></td>
</tr>
</table>

## [Reset Menu](Mainmenu#Reset-Menu)

Restores the main menu to it's default set of apps.

## App Management

Add, remove, and rearrange the content of your main menu (apps/files/folders). There are 8 apps by default: `SubGHz`, `RFID`, `NFC`, `Infrared`, `GPIO`, `iButton`, `Bad KB`, `U2F`.

### [Add App](Mainmenu#Add-App)

Add new items to your menu:

- `Main App`: System applications
- `External App`: Apps from SD card that you install yourself

### [Move App](Mainmenu#Move-App)

Rearrange the order of apps in your menu:

- Select app to move (1/8)
- Use `LEFT/RIGHT` to position

### [Remove App](Mainmenu#Remove-App)

Delete apps from your menu:

- Select app to remove (1/8)
- Confirm removal by pressing `OK`
