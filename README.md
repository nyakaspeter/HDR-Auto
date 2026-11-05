## What is HDR-Auto?
A system tray application that automatically toggles HDR on in the Windows settings when a game that supports HDR is run. It will also toggle HDR off when the game exits. 

## Why use HDR-Auto?
Leaving HDR on in the Windows settings results in a raised black level for SDR content. "SDR content brightness" doesn't resolve this issue because Windows uses a piecewise sRGB gamma, rather the 2.2 gamma used by most content. More information on this topic can be found [here](https://github.com/dylanraga/win11hdr-srgb-to-gamma2.2-icm/tree/main#jump-to-downloads).

## How to use HDR-Auto
Download the hdr-auto.exe from the [releases page](https://github.com/noahz123/HDR-Auto/releases) or build from source using the instructions below. Run the program and look for the system tray icon to ensure it is running.

Whenever the application is run it will download the latest community curated list. You can also create a custom list using this format:
```text
007FirstLight.exe
DOOMTheDarkAges.exe
MonsterHunterWilds.exe
```

The custom list is always active and may be left empty. Entries are case insensitive and the `.exe` extension is optional for executable names. You can edit it by clicking "Edit custom game list" in the system tray menu.

Background shader compilation workers launched by SCSKiller's `scskiller_warm.exe` are automatically ignored, even when they use a game's executable name. Games launched normally still trigger HDR while SCSKiller is open.

Use "Edit exclusion list" to prevent entries from either the community or custom list from triggering HDR. Both lists also accept full executable paths. A filename such as `launcher.exe` matches that executable anywhere, while a full path such as `D:\Games\launcher.exe` matches only that exact executable. Full-path entries should include the `.exe` extension.

## Building from source
Install [Rust](https://www.rust-lang.org/tools/install), then clone this repository and run:

```powershell
cargo build --release
```

The compiled executable will be created at `target/release/hdr-auto.exe`.

## Contributing
You may contribute to the community list by editing games_default.txt and creating a pull request. Games should support native HDR output, including limited native or automatically enabled HDR as documented on the [PCGamingWiki HDR Page](https://www.pcgamingwiki.com/wiki/List_of_games_that_support_high_dynamic_range_display_(HDR)). Games that require a mod to add HDR belong in your custom list. Verify the actual game executable rather than deriving its name from the title, and avoid shared launchers, editors, and generic executable names. Where possible, run the game and check that HDR toggles on as intended.
