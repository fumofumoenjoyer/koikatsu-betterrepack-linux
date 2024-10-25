# koikatsu-betterrepack-linux

I copy-pasted this from somewhere i dont remember for safekeeping, so if someone knows let me know so i can give credit.

 Start & End
This Guide assumes you know how to use, search & download things especially when you are using Linux anyway.

So first how to play it:

Right Click, configure and force proton compatibility Layer to Preferable latest Official/Experimental version or even better using Proton-GE. Now the "base" game should work. But we obviously want to use the HF Patch at minimum.

To install the HF Patch simply right click and open with wine. Or terminal and wine *hf setup.exe*. And just point it to the correct installation destination. Which in most cases would be /home/USERNAME/.steam/steam/steamapps/common/Koikatsu Party/ .

But to get mods and so working you have to Right Click again , configure and add these launch options: WINEDLLOVERRIDES="winhttp=n,b" %command%

Now the game + HF patch or rather mods are working fine. But we also want to use the KKManager to update mods, to do that open a terminal and do:

[You have to install wine, to do so just search online for the glorious eggroll post for "how to get out of wine dependency hell" and follow the steps needed for your specific distro of choice.]

winetricks corefonts
winecfg
Inside of winecfg add application and point it to KKManager.exe then go to libraries and add winhttp Native , Builtin and close winecfg then proceed with the following:
winetricks dotnet472
This should install 4.0 and 4.5 if i'm not mistaken but probably gonna stop working at 4.6 and onwards [IF it should install just fine though you are done and can ignore the rest of this guide and just open KKManager and update your mods.] Just force quit the command with ctrl+c and enter this next command:
winetricks dotnet35

But we are not done since KKManager needs 4.6.2 to do that we need to install it manually first open a terminal again and enter the following command:
winetricks win7

After that go to the official Microsoft page and download .NET Framework 4.6 & 4.6.2 offline installer.

Open a terminal again and do the following commands:
wine *net 4.6 setup.exe* /q
Then wait till its seemingly done and then do:
wine *net 4.6.2 setup.exe* /q

Afterwards if nothing went wrong KKManager should now open up and you can update your mods. 
