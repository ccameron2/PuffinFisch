#  Puffin
Auto-fishing bot for the Roblox game Fisch. Reads the screen with OpenCV, plays the reel, cast, and shake minigames, and runs from a tkinter control panel.

<table> <tr> 
<td rowspan="2"><img width="480" height="667" alt="PuffinUI" src="https://github.com/user-attachments/assets/13e81b37-43e3-4b32-a198-dce426fa9b2a" /></td> 
<td><img width="520" alt="PuffinCircles" src="https://github.com/user-attachments/assets/d694e905-a98b-4406-9fa6-30f2b5122d1d" /></td> 
</tr> <tr> <td><img width="520" alt="PuffinMinigame" src="https://github.com/user-attachments/assets/2ddbe308-5b55-4cd7-8fbd-48ff8b7909a9" /></td> 
</tr> </table>

## How it works
Puffin captures the Roblox window with `mss` and uses HSV/saturation masks to track the on-screen game state in real time, then drives the mouse via `SendInput`:

- Reel minigame: keeps the control bar over the fish
- Cast minigame: releases at the green tip for a perfect cast
- Shake button: detects the dark overlay disk and clicks it

<br> No memory reading or injection: only looks at pixels and moves the mouse

## Rod modes
- Standard: Grey fish capsule, lit moving bar
- Requiem: Custom bar, hold/release control capped at ~100 BPM
- Pinions: Custom bar + note targeting
- Tryhard: Custom All-red UI: detection keys on saturation instead of hue
- Perfect Cast:	Holds the cast until the fill bar reaches the green tip

<br> Modes are mutually exclusive and persist in the Windows registry along with the toggle key and bar colour

## Install
- Download the latest Puffin.exe from [Releases](https://github.com/ccameron2/PuffinFisch/releases)
- Requires [Python](https://www.python.org/downloads/) to be installed

## Run
- Launch Roblox and open Fisch
- Position facing a body of water where you want to fish
- Run Puffin.exe
- Pick a mode in the panel, then press start. Puffin resizes and tracks the Roblox window automatically
- Enable Debug & Console to see the CV overlays and live log
