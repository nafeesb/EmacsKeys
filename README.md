# EmacsKeys
This project provides Emacs key bindings for Visual Studio users, through a Visual Studio Extension.

## History ##

This capability was available in [VS2008](https://msdn.microsoft.com/en-us/library/ms165528(VS.90).aspx), but was removed in VS2010 and VS2012.  

Emulation was released as a Visual Studio Extension called the "[Emacs Emulation](https://visualstudiogallery.msdn.microsoft.com/09dc58c4-6f47-413a-9176-742be7463f92 "Emacs Emulation")" extension.

Since the extension has not been supported by the Visual Studio Team since 2010, I was able to make the case for the source code to be made available publicly. 

This is a copy of the original VS2010 extension source code as provided by the Visual Studio Team, and is the initial check-in of this repository.

## Current Plans ##

A current limitation of the original version, is that it requires the copying of a "vsk" file, into the Visual Studio product folder, which requires running the extension installer as administrator.

To solve this, my next check-in will instead make use of the Visual Studio import/export bindings (vssettings), stored per user, with a specified set of Emacs key bindings, that can then be edited locally according to taste.

## Installation ##

These notes are taken from [a StackOverflow post](https://stackoverflow.com/questions/13884953/emacs-keybindings-in-visual-studio-2012-or-2013/14087731#14087731).

1. Open the `EmacsEmulation.sln` solution file.
  * Visual Studio may ask you to install additional components.
2. Build solution.
  * Change build type to "Release"
  * This will build into `bin/Release`.
3. Run `Command Prompt` as Administrator
4. `cd` to `bin\Release`.
5. Run the vsix file.

    ``
    start Microsoft.VisualStudio.Editor.EmacsEmulation.vsix 
    ``
6. Run: `explorer "c:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE"`
7. Find the file named: `Emacs.vsk`
8. Copy `Emacs.vsk` to `"c:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE"`
9. Run Visual Studio as Administrator
  * Only need to do this once.
  * Check that the "Emacs" extension exists in the "Tools/Extensions and Updates" menu.
  * Check that the "Emacs" keyboard shows up under the "Tools/Options/Keyboard" menu.
10. Enjoy!
