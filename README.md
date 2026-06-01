## What is HDR-Auto?
A system tray application that automatically toggles HDR on in the Windows settings when a game that supports HDR is run. It will also toggle HDR off when the game exits. 

## Why use HDR-Auto?
Leaving HDR on in the Windows settings results in a raised black level for SDR content. Setting "SDR content brightness" in the Windows doesn't resolve this issue because Windows 11 uses a piecewise sRGB gamma, rather the 2.2 gamma used by most content.

## How to use HDR-Auto
Download the hdr-auto.exe from the releases page. Run the program and look for the system tray icon to ensure it is running.

Whenever the application is run it will download the latest community curated list. You can also create a custom list using this format:
```text
007FirstLight.exe
DOOMTheDarkAges.exe
MonsterHunterWilds.exe
```

This list is case insensitive and the .exe is optional. You can edit your custom list by clicking "Edit custom game list" in the system tray menu. You may choose to use either the default list, the custom list, or both.

## Building from source
Install [Rust](https://www.rust-lang.org/tools/install), then clone this repository and run:

```powershell
cargo build --release
```

The compiled executable will be created at `target/release/hdr-auto.exe`.

## Contributing
You may contribute to the community list by editing the games_default.txt and creating a pull request. Please ensure the game you add is not already in the list, and is listed as "Native support" on the [PCGamingWiki HDR Page](https://www.pcgamingwiki.com/wiki/List_of_games_that_support_high_dynamic_range_display_(HDR)). Also ensure the .exe name is correct by running it on your computer and checking the HDR toggles on as intended.
