ModLoader Manual
=========================

Never edit meta.xml ever again, never too lazy to add new mods, never you will you have a problem with custom handlings, and your vehicle collisions will always work. That's exactly what this resource brings to you. You can't get any simpler than this. Isn't that great?

Installation
------------

First of all, download modloader from *here*. Make sure to **unzip** the downloaded package into your resources directory of MTA. Now you must change the folder of the resource from `modloader` to something like `modloader-mysuffix`. You can change `mysuffix` to whatever you want it to be, for example, `modloader-ABCD` for the ABCD server. We strongly recommend you to choose a unique name when doing this so that your users won't have to download all your modifications again when they join a server with the same resource name.

After you've done that, you **must** give ModLoader access to the restartResource function. The easiest way to do this is by adding `<object name="resource.modloader-mysuffix"></object>` under the admin group in _acl.xml_. Just pop it underneath `<object name="resource.admin">` and you'll be all set up.

Installing mods
---------------

Installing modifications has never been this easy. All you've got to do is find your favorite vehicle, weapon or skin modifications from your preferred source and just place them in the correct folder. [GTAInside][3] and [GTAGarage][4] are popular sources for mods.

After you've downloaded a mod, you'll need to take the TXD and DFF and place them in the correct folder. These files **must** have the name of the GTA harcoded name. They cannot be capitalised at all - it must be completely lowercase. If modloader isn't loading your mod, make sure it's in the format of `carname.dff` like `infernus.dff` - not `Infernus.DFF` - it's the number one rule!

#### Vehicles
Vehicles usually come with a handling file, a TXD (texture) file and a DFF (model) file. ModLoader removes the requirement to understand how to code and lets you easily set up your first vehicle modification. Setting up the handling file needs a little understanding of creating files with custom extensions but setting up the textures and models - the things that make up a visual modification - is super easy.

1. Copy the texture and model files into the vehicles folder. ![screenshot](http://puu.sh/6nkEz.png)
2. If your modification contains a handling configuration and you'd like to add it to your server, read the next section.

#### Handling configurations
Installing handling configurations take a little bit of playing around, but it's easy once you get the hang of it. My lamborghini modification for my infernus came with a README file containing the handling line. I won't go into detail with how they work, but I'll just teach you how to import them into modloader.

Your README file might contain something like this. ![screenshot](http://puu.sh/6nncT.png)
At the moment, MTA (and by extension, modloader), doesn't support the feature to import the other files mentioned here, but it doesn't mean that your modification wont work (albeit not as the author intended). But don't worry. Just copy the handling contents into your clipboard. ![screenshot](http://puu.sh/6nnje.png)

You need to copy this to the same vehicles folder. To do this you need to create a `.hnd` file with the same name as your vehicle. In Notepad, just copy it over, and save the file as `yourvehicle.hnd`. It is really important you set the file types as `all files` so that the extension is properly set.

![screenshot](http://puu.sh/6nmef.png)

Once you're done with saving it... that's it. You've got your vehicle and handling file imported into modloader!

#### Skins and weapons
Replacing skins and weapons work pretty much the same way. In the future we may add the ability to change weapon properties which modifications may give you but at the moment we only support textures (TXD) and models (DFF). It's simple if you've read through everything else above, just move the file into the folder!

Commands
-----

To delete a single mod after modloader has loaded it: `mdel [moddir] [modname]`
Example: `mdel vehicles infernus`

To delete all mods: `mclear [moddir]`
Example: `mclear vehicles`

Technical information
---------------------

Since the latest versions of MTA, vehicle collisisions are properly supported. This means ModLoader does not have to take care of making sure the collisions work anymore. If the following is not the case already, please disable the loading of collisions by opening `replacer_c.lua` with a text editor and changing `local allowCollissions = true` to `local allowCollissions = false`. The `maxVehicles` variable can be ignored from now on.

Support
-------

For issues and support you can refer to the [forums][1] or [submit an issue][2] on this GitHub page.


[1]: http://forum.mtasa.com/viewtopic.php?f=108&t=36481
[2]: https://github.com/Deltanic/modloader/issues
[3]: http://www.gtainside.com/en/
[4]: http://www.gtagarage.com/
