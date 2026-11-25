# ZeldaDOI Speedhack Edition

**Final release candidate** for the **1 GB Anbernic RG35XX SP running
muOS** (though other Anbernic 1 GB devices are expected to work). Both ZIPs
contain the same Speedhack build (`9d2dc97a`) and include the Installer,
Launcher, Remover, and dungeon preview.

The main Dungeons of Infinity project is maintained by the community on
[GitHub](https://github.com/zdoi-devs/dungeons-of-infinity).

**Install the original Zelda: Dungeons of Infinity v1.1.6 first.** Download
and import the original [zeldadoi.zip][original-zip] separately. PortMaster
autoinstall imports the ZIPs you put on the SD card. The Speedhack Installer
uses the original game on the card to create a separate patched installation.

## 1. Install the original ZeldaDOI v1.1.6

Skip this step if the original v1.1.6 port is already installed on the
same card. If PortMaster's on-device catalog hides the original because
of its memory requirement, import the official ZIP manually.

1. On your computer, download
   [zeldadoi.zip from PortMaster's official release][original-zip].
2. Copy [zeldadoi.zip][original-zip] to `ports/autoinstall/` on the muOS SD card.
   Leave it zipped.
3. Safely eject the card, boot muOS, and open **PortMaster**. Let it
   finish importing the original game.
4. Confirm `ports/zeldadoi/zeldadoi.port` exists on the card. You can
   proceed to the Speedhack installation without launching the original.

The official [zeldadoi.zip][original-zip] has SHA-256
`cf13009f3f8f5578a17ca4a45de051ea1315280037f01434c187ebc9d9e91353`.
See the [PortMaster offline installation guide](https://portmaster.games/installation/installing-ports/).

## 2. Choose a Speedhack ZIP

| File | What it does |
| --- | --- |
| [zeldadoi-v1.1.6-1gb-speedhack-automatic-install.zip][automatic-zip] | **Recommended.** Import this ZIP through PortMaster to install the patch tools and launchers. |
| [zeldadoi-v1.1.6-1gb-speedhack-manual-install.zip][manual-zip] | Manual SD-card installation of the same release. Extract this ZIP at the root of the card. |
| `SHA256SUMS` | Checksums for both ZIPs and the manifest. Use it on your computer to verify the download. |
| `release-manifest.json` | Records the exact game build, candidate status, file sizes, and hashes. Keep it with the downloads for verification. |

Choose **one** Speedhack ZIP. Keep the checksum file and manifest on your
computer for verification.

## If the card already has a Speedhack installation

Before importing or extracting the new package, move the two folders below
and the existing Speedhack launchers into a separate backup folder outside
`ports/` and `ROMS/PORTS/`. This keeps the old saves and settings together
and clears the installation paths. The old launchers match
`ZeldaDOI V6 Guarded *.sh`. Any previous install of this candidate uses
`ZeldaDOI Speedhack *.sh`. Leave the original ZeldaDOI launcher in place.

- `ports/zeldadoi-speedhack-v6-lease-15fd1403/` contains the separate Speedhack saves.
- `ports/zeldadoi-speedhack-v6-lease-tools-15fd1403/` contains the patch tools.
- The Speedhack launchers are under `ROMS/PORTS/` on muOS.

Leave the original `ports/zeldadoi/` installation in place. Installer
creates a fresh separate save area and leaves the backed-up saves where
you put them.

## 3. Install the Speedhack through PortMaster

1. Copy [zeldadoi-v1.1.6-1gb-speedhack-automatic-install.zip][automatic-zip]
   to `ports/autoinstall/` on the SD card. Leave it zipped.
2. Safely eject the card, boot the handheld, and open **PortMaster** once
   to import the ZIP.
3. In muOS, launch **ZeldaDOI Speedhack Installer**. Wait for it to return to
   the menu. If it reports an error, keep the message and stop before
   opening Launcher.
4. Launch **ZeldaDOI Speedhack Launcher** to play.

Check that the launcher names say **ZeldaDOI Speedhack** after import.
If you see only **ZeldaDOI V6 Guarded** entries, the older package is still
installed. Back it up using the instructions above, then import the
current automatic ZIP.

## Alternative manual Speedhack installation

1. Extract [zeldadoi-v1.1.6-1gb-speedhack-manual-install.zip][manual-zip]
   at the **root of the SD card**. The launchers go in `ROMS/PORTS/` and
   the tools go in `ports/`.
2. Safely eject the card and boot the handheld. Run **ZeldaDOI Speedhack
   Installer**, wait for it to finish, then open **ZeldaDOI Speedhack Launcher**.

## Play, save, and restore

- Start with **Fast Lighting** and **CRT Off**. Standard lighting can
  slow down in dim rooms. Profile **Options** lets you change these
  settings separately.
- **Installer** prepares the separate game installation.
  **Launcher** plays it. To play with your original profiles, launch
  the original PortMaster game.
- Save at a SaveTent. **Continue** consumes that checkpoint when it
  succeeds. Reach another SaveTent to save again.
- To roll back the patch, close the game and run **ZeldaDOI Speedhack
  Remover** from muOS. It restores the original game archive in the
  separate Speedhack installation and preserves its saves and settings.
  If launch reports an interrupted save, preserve the entire save folder
  and follow the included player guide before trying recovery.

## Licenses

- [Source code (GNU GPL v3)](./licenses/source_code.txt)
- [Original artwork (CC BY-NC 4.0)](./licenses/original_artwork.txt)

## Verify the download

Save `SHA256SUMS` next to your downloaded ZIP. Open a terminal in that
folder and run:

```sh
sha256sum --ignore-missing -c SHA256SUMS
```

Expect `OK` next to your ZIP. If you downloaded both ZIPs and the manifest,
`sha256sum -c SHA256SUMS` checks all three. The automatic ZIP hash starts with
`95efae30`, and the manual ZIP hash starts with `8ea1cb9d`.

[original-zip]: https://github.com/PortsMaster-MV/PortMaster-MV-New/releases/download/2024-12-03_1532/zeldadoi.zip
[automatic-zip]: ./zeldadoi-v1.1.6-1gb-speedhack-automatic-install.zip
[manual-zip]: ./zeldadoi-v1.1.6-1gb-speedhack-manual-install.zip
