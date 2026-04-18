# DataCenter MelonLoader Patcher

Fixes MelonLoader compatibility after the Unity 6000.3 → 6000.4 update broke mod loading in Data Center.

## Known Issue

When MelonLoader runs it will check to see if assembly generation is needed, if it does, it will look like this:
``` [13:16:32.706] [Il2CppAssemblyGenerator] Checking GameAssembly... ```
``` [13:16:33.116] [Il2CppAssemblyGenerator] Assembly Generation Needed! ```

In the event assemblies are generated, you will need to either run the patcher again or replace the newly generated assembly (UnityEngine.CoreModule.dll) with the patched version found in this repo.

## The Problem

The Unity 6000.4 update shipped a changed `UnityEngine.CoreModule.dll` that MelonLoader cannot load against. All mods stop working after this patch.

## What This Script Does

1. Locates your Data Center installation automatically via the Steam registry
2. Backs up the original `UnityEngine.CoreModule.dll` as `.bak`
3. Downloads and installs the patched DLL

Your original file is never deleted, the backup is always there if you need to roll back.

## How To Use

1. [Download DCMelonPatcher.ps1](https://github.com/MaximumLeet/DataCenter-MelonLoader-Patcher/releases/download/v1.0.0/DCMelonPatcher.ps1)
2. Right-click it → **Run with PowerShell**
3. Launch the game as normal

OR - You can simply download the DLL directly and install it where it goes. Up to you!

That's it.

## Requirements

- Windows
- Data Center installed via Steam
- (Optional if downloading the DLL directly) PowerShell (included with Windows)

## Credits

Patched DLL by Bloody on the Waseku Discord - Thanks man!
