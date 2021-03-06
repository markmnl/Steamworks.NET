Steamworks.NET
=======

_Steamworks.NET_ is a C# Wrapper for Valve's Steamworks API, it can be used either with Unity or your C# based Application. This project relies on dynamic libraries created by [CSteamworks](https://github.com/rlabrecque/CSteamworks). (Prebuilt and included for ease of use)

_Steamworks.NET_ was designed to be as close as possible to the original C++ API, as such the documentation provided from Valve largely covers usage of _Steamworks.NET_. 
Niceties and C# Idioms can be easily implemented on top of _Steamworks.NET_.

_Steamworks.NET_ currently supports Windows, OSX, and Linux in both 32 and 64bit varieties. Currently building against Steamworks SDK 1.31.

* Author: [Riley Labrecque](https://github.com/rlabrecque)
* License: [MIT](http://www.opensource.org/licenses/mit-license.php)
* [Discussion Thread](http://steamcommunity.com/groups/steamworks/discussions/0/666827974770212954/)
* [Reporting Issues](https://github.com/rlabrecque/Steamworks.NET/issues)
* 1-on-1 support is available by donating $40 USD or greater.
 * Support can be obtained via [Email](mailto:support@rileylabrecque.com), [Skype](http://rileylabrecque.com/skype), or [Steam](http://steamcommunity.com/id/rlabrecque)
 * I can only help with Steamworks.NET specific issues, general API questions should be asked on the [Steamworks discussion board](http://steamcommunity.com/groups/steamworks/discussions).

[![Support via Paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=YFZZER8VNXKRC)


Usage
-----

To use _Steamworks.NET_ you must be a Steamworks developer.
_Steamworks.NET_ requires Unity Pro for the plugin functionality.

* Download the .unitypackage [Stable (5.0.0)](https://github.com/rlabrecque/Steamworks.NET/releases/download/5.0.0/Steamworks.NET_5.0.0.unitypackage) or Clone from [Github](https://github.com/rlabrecque/Steamworks.NET)
* Extract and copy Steamworks.NET's `Plugins/` and `Editor/` folders into your `Assets/` folder.
* Open `Plugins/Steamworks.NET/redist/steam_appid.txt` and replace `480` with your own AppId.
* Launch your Unity project. The included editor scripts will copy steam_appid.txt (and steam_api.dll if your on windows) into the root of your project.
* Close Unity and relaunch the project so that it loads the freshly copied steam_appid.txt & steam_api.dll.

##### Samples
Check out these sample projects to get started:
* [Steamworks.NET Example](https://github.com/rlabrecque/Steamworks.NET-Example)
* [Steamworks.NET Test](https://github.com/rlabrecque/Steamworks.NET-Test)

Not using Unity?
----------------

If you are not using Unity then you have two available routes that you could take.
* A: The peferable route is to build the standalone assemblies with the project file located in `Standalone/`. Alternatively you can download the prebuilt binaries which are available on the [Releases](https://github.com/rlabrecque/Steamworks.NET/releases) page.
 * Further instructions are provided by the [README.md](https://github.com/rlabrecque/Steamworks.NET/blob/master/Standalone/README.md) in the `Standalone/` folder.
* B: Copy `Plugins/Steamworks.NET` into your C# project. In Visual Studio open your project properties, change to the Build tab and define `STEAMWORKS_WIN` or `STEAMWORKS_LIN_OSX` globally via `Conditional compilation symbols`.
 * This is only recommended if your binary is not portable across platforms already. If you ship on multiple platforms you must have multiple build targets for each platforms. Please prefer the second route.

Using Steam Encrypted App Ticket?
---------------------------------

If you wish to use the functions from `sdkencryptedappticket.dll` then you will need to manually place the dll/so/dylib in the following location:
* Windows: Next to steam_api.dll
* OSX: In `/Contents/Frameworks/MonoEmbedRuntime/osx/`
* Linux: Next to CSteamworks.so

`sdkencryptedappticket.dll` can be found in the Steamworks SDK in Valve's partner backend. Ensure that you get them from the same version of the SDK that Steamworks.NET is built against. (Usually the latest.)
