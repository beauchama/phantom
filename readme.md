# Phantom

Customize the Windows Terminal and Powershell 7.

## Getting started

You need to install the following software to use this configuration:

### Requirements

1. Install the Windows Terminal from the Microsoft Store (Windows 10 only).
2. Install Fira Code from [Nerd Fonts].
3. Install Powershell 7 using `winget search Microsoft.PowerShell`.

### Oh My Posh

Personalize your prompt with Oh My Posh. Install it using the following command:

```pwsh
winget install JanDeDobbeleer.OhMyPosh -s winget
```

This command install a couple of things:

* oh-my-posh.exe - Windows executable
* themes - The latest Oh My Posh themes

:warning: For the PATH to be reloaded, a restart of your terminal is advised. :warning:

After installing Oh My Posh, you can set the theme for powershell. You can view their [documentation] for more information. Important to note that Oh My Posh is designed to use Nerd Fonts.

## Configure Powershell 7

We will configure the Powershell 7 profile to use Oh My Posh and Phantom theme. Open the profile using the following command:

:warning: Make sure to open a powershell 7 terminal. :warning:

```pwsh
code $PROFILE
```

It will open the profile in Visual Studio Code. Copy profile.ps1 provided in this repository and paste it in the profile. Save the file and reload the prompt using the following command:

```pwsh
. $PROFILE
```

You can read more about [profile.ps1](#profileps1) in the section below.

## Profile.ps1

The profile.ps1 is a script that runs every time you open powershell. The profile provided in this repository is configured to include Oh My Posh and Phantom theme. You can customize the profile to include more modules or themes.

### Modules

The profile includes the following modules which are required for Phantom theme to work properly

#### Posh Git

Posh Git is a PowerShell environment for Git. It provides Git status information and tab completion. You can find more information about Posh Git in their [repository][posh-git]

#### Terminal Icons

Terminal Icons is a PowerShell module that provides icons for files and folders. You can find more information about Terminal Icons in their [repository][terminal-icons]

#### PSReadLine

Module which need to be updated.

### Themes

The profile execute Oh My Posh with the custom theme Phantom by default.

### Optional scripts

The profile some optional scripts that you can use to customize your prompt. Is not required to use them.

#### .NET auto-completion

The script provides auto-completion for .NET commands. You can use it by typing `dotnet` and pressing `TAB`.

#### Winget auto-completion

The script provides auto-completion for winget commands. You can use it by typing `winget` and pressing `TAB`.

#### Github CLI auto-completion

The script provides auto-completion for gh commands. You can use it by typing `gh` and pressing `TAB`.

You need to install the respective software to use the auto-completion.

## Configure Windows Terminal

We will configure the Windows Terminal to add a new profile for Powershell 7. Copy this section in the profiles section of the settings.json file.

```json
{
    "guid": "{574e775e-4f2a-5b96-ac1e-a2962a402336}",
    "name": "Bash",
    "icon": "https://cdn.jsdelivr.net/gh/beauchama/phantom@main/assets/bash.png",
    "source": "Windows.Terminal.PowershellCore",
    "startingDirectory": "Path which you want to start",
    "useAtlasEngine": true,
    "suppressApplicationTitle": true,
    "hidden": false,
    "adjustIndistinguishableColors": "always",
    "colorScheme": "Vintage",
    "cursorShape": "vintage",
    "cursorColor": "#00bdd0",
    "foreground": "#00bdd0",
    "font": 
    {
        "face": "FiraCode Nerd Font",
        "size": 14.0
    }
}
```

[Nerd Fonts]: https://www.nerdfonts.com/
[documentation]: https://ohmyposh.dev/docs
[posh-git]: https://github.com/dahlbyk/posh-git
[terminal-icons]: https://github.com/devblackops/Terminal-Icons
