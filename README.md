# MSI Power Control

![MSI Power Control](docs/banner.png)

**One-click power modes, fan and Cooler Boost control, battery charge limit, live sensors and a RAM/CPU cleaner for MSI laptops on Windows 10 / 11.**
Built and verified on the **MSI Katana GF66 12UCOK**; other MSI laptops are supported through the built-in **Set up this laptop** learner.

## Download

**[Download the latest MSIPowerControl.exe](https://github.com/h21-x/msi-power-control/releases/latest)** (Assets, then `MSIPowerControl.exe`).

- No Python, .NET or installer needed: it is a single portable `.exe`. Run it; Windows asks for administrator rights because MSI's driver needs them.
- Needs **MSI Center** installed (it provides the driver this app talks to). The app checks everything at startup and tells you what is missing.
- The exe is not code-signed, so Windows SmartScreen may warn on first run ("More info", then "Run anyway"). Verify the download first:
  `certutil -hashfile MSIPowerControl.exe SHA256` and compare with `SHA256SUMS.txt` in the same release.

## What it does

| | |
|---|---|
| **5 one-click modes** | Highest Performance, Game, Balanced, Quiet, Power Saving: each sets the Windows power plan, the MSI Center performance mode (Extreme / Balanced / Super Battery), fans and the screen refresh rate together. Hotkeys Ctrl+Alt+1..5. |
| **Cooler Boost** | One-click fan boost (Ctrl+Alt+C), remembered across reboots. |
| **GPU overclock** | +150 core / +150 VRAM in one click on NVIDIA models, read back from the GPU. |
| **Battery care** | Adaptive charging with a 60 / 70 / 80 / 90 % charge limit. |
| **Live sensors** | CPU / GPU temperature, both fans, CPU / GPU / total power, clock, load, RAM, VRAM, commit and page file. Colour-coded gauges. |
| **Auto-switch** | Optional: switch mode when you plug in or unplug the charger. Otherwise your last mode is remembered and kept. |
| **Cleaner** | Frees RAM / CPU safely (Ctrl+Alt+R), optional auto-clean for Game mode. |
| **Remembers everything** | Last mode, window size and position, Cooler Boost, charge limit, and your settings. |
| **Other MSI laptops** | **Set up this laptop** learns your model's controller map by watching MSI Center, writing nothing it has not seen MSI change. |
| **AMD / Intel** | AMD and Intel CPUs and GPUs are supported (load, VRAM, plans). GPU overclock is NVIDIA-only. The AMD paths have not been run on real Ryzen / Radeon hardware yet. |

Close-lid behaviour is never changed: the app copies your current lid action, so working with the lid closed and an external monitor keeps working.

## Requirements

| Requirement | Needed for |
|---|---|
| An MSI laptop | everything hardware-related (Windows plans and the cleaner work anywhere) |
| **MSI Center** (with the MSI NBFoundation service) | MSI modes, Cooler Boost, fans / temps, charge limit, GPU overclock |
| Graphics driver | GPU readout (NVIDIA: `nvidia-smi`; AMD / Intel: Windows GPU counters) |
| Windows PowerShell 5.1 | included with Windows 10 / 11 |

## Safety

This app writes to your laptop's embedded controller through MSI's own driver. It only writes registers that are in a verified profile or that it has watched MSI Center change itself; unknown laptops start read-only. **Use at your own risk**, no warranty.

## Help and feedback

Open an [issue](https://github.com/h21-x/msi-power-control/issues) for bugs or to share a profile for your laptop model (the setup dialog has a share button that pre-fills one).

## Terms

Free to use and to share unmodified. The source code is not published. Provided as is, without warranty.
**Not affiliated with, endorsed by or sponsored by MSI (Micro-Star International).** MSI, MSI Center and Katana are trademarks of their respective owners and are used only to say which laptops this works with.

by H21x
