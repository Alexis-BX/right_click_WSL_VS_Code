# Adding the open in VS Code with WSL in the right click menu

Merge the `.reg` file to add the following options:

- Right click on a folder to open it in VS Code in WSL mode along with a seperate WSL terminal
- Right click on a folder background to open the folder in VS Code in WSL mode along with a seperate WSL terminal
- Right click on a file to open it in VS Code in WSL mode.

### Changing the `Open Linux shell here` right click option

Every step followed will have to be repeated for both of these keys:
```
HKEY_CLASSES_ROOT/Directory/Background/shell/WSL
HKEY_CLASSES_ROOT/Directory/shell/WSL
```

#### Gaining write priveleges on the WSL key

Open `Registry Editor` as an adminstrator.

Right click the `WSL` key and select `Permissions`.

Select `Advanced` and then `Change` owner.

Enter `[COMPUTER_NAME]\Administrators` 

`Apply` and `OK`

Select `Replace owner on subcontainers and objects` and `Replace all child object permssion entries with inheritable permission entries from this object`

`Apply` and `OK`

Select group `Administrators` then tick `Full Control` to `Allow`

`Apply` and `OK`

Now you are free to modify the setings for the WSL keys.

#### Possible changes

- Always present:

Go to `WSL` and rename `Extended` to `-Extended`.

- Add a logo: 

`WSL` -> `New > String Value` -> `Icon`

Right click `Icon` -> `Modify...`

For a Ubuntu logo: download the attached logo and set the value to `C:\Path\to\icon\ubuntu.ico`

For a Linux logo: `C:\Windows\System32\wsl.exe`
