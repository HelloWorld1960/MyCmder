# MyCmder

Cmder notes

## Cmder Context (Right-Click) Menu for Windows 7, 8 & 10

Create ContextCmder-Disable.reg and execute as an administrator.

```bash
Windows Registry Editor Version 5.00

[-HKEY_CLASSES_ROOT\Directory\Background\shell\Cmder]
[-HKEY_CLASSES_ROOT\Directory\shell\Cmder]
```

Create ContextCmder-Enable.reg and execute as an administrator.

```bash
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\Directory\Background\shell\Cmder]
@="Open Cmder Here"
"Icon"="C:\\tools\\cmder\\Cmder.exe,0"

[HKEY_CLASSES_ROOT\Directory\Background\shell\Cmder\command]
@="\"C:\\tools\\cmder\\Cmder.exe\" \"%V\""

[HKEY_CLASSES_ROOT\Directory\shell\Cmder]
@="Open Cmder Here"
"Icon"="C:\\tools\\cmder\\Cmder.exe,0"

[HKEY_CLASSES_ROOT\Directory\shell\Cmder\command]
@="\"C:\\tools\\cmder\\Cmder.exe\" \"%1\""
```


## Open Cmder in a chosen folder

1. In Settings -> Startup -> Tasks, select your default Task (probably ```cmd::Cmder``` - check or change in Settings -> Startup)
2. It will look something like this ```cmd /k ""%ConEmuDir%\..\init.bat"" -new_console:d:%USERPROFILE%```
3. Remove the portion ```:d:%USERPROFILE%``` <- Note the colon before ```d```
4. Result should be: ```cmd /k ""%ConEmuDir%\..\init.bat"" -new_console```
5. This will stop new tasks/command tabs from defaulting to your home directory.
