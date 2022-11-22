# Mod-Hub
A shared settings window for blueprint mods that want to use it.

## How to use as a mod user
Download ModHub.pak and install into AstroColony/Content/Paks/LogicMods (Unreal Mod Loader is required)

## How to use as a mod developer
Download the most recent release of _ModHub.zip

Extract the folder _ModHub from within this .zip into your UE project's Content folder. So an example project path should be AstroColony/Content/_ModHub

There are 3 interfaces:
* `IHub` - Coontains functions that can be called on the Mod Hub Manager. More on that later
* `IHubPageWidget` - The interface to add to every widget blueprint page that you want to add to Mod Hub
* `IHubMod` - The interface to add to the main mod actor of your mod

![1](/Images/Interfaces.png)

### IHubPageWidget
1. Add it under class settings.

![2](/Images/IHubPageWidget_Interface.png)

2. Double click on the interface functions and fill out the return variable.

![3](/Images/IHubPageWidget_Impl.png)

### IHubMod
1. Add it under class settings.

![4](/Images/IHubMod_Interface.png)

2. Double click on the interface functions and fill out the return variables.

![5](/Images/IHubMod_Info_Impl.png)

3. When adding pages, keep in mind that you need to instantiate your mod page widgets for them to show.

![6](/Images/IHubMod_Pages_Impl.png)

**Optional:**
4. Right click the event functions and implement them. You can now handle these events.
5. Mod Registered gets called when your mod is registered with Mod Hub. It returns a reference to the Hub.
6. As shown are some of the functions that can be used with the IHub reference.

![7](/Images/Functions.png)

### Notes
- Do not pack the _ModHub folder nor its contents with your mod. A copy already exists with the ModHub itself.