Install printer
===============

1. Basic installation (only one of them required)

   a. as AppImage:

      1. download appimage from https://github.com/SoftFever/OrcaSlicer/releases/tag/v2.4.2 and safe it as ``orca``
      2. mark the appimage as executable (``chmod +x ~/orca``)
      3. start Orcaslicer via ``~/orca``

   b. Install from flathub::

         flatpak --user remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
         flatpak --user config --set languages ""
         flatpak --user install com.orcaslicer.OrcaSlicer

2. Select to use the System SSL certificates (and let it remember the choice)
3. Go through each step of the Setup Wizard and create a dummy printer (which will not be used by us)

   a. Press "Get Started"
   b. Select "Europe" and press "Next"
   c. Select under "Generic Klipper Printer" and press "Next"
   d. Select "Generic PLA" and press "Next"
   e. Select "Enable Stealth Mode."
   f. Don't select proprietary Plugins and just press "Finish"

4. If the "New Version" dialog appears, just select "Check for stable updates only" and then "Skip this version"

5. Download profiles from https://github.com/ecsv/orcaslicer_ldo-trident-r2-300/archive/refs/heads/orcaslicer.zip
6. Go to ``File`` -> ``Import`` -> ``Import Configs`` and select the downloaded ``orcaslicer_ldo-trident-r2-300-orcaslicer.zip``
7. Repeat the last step (no, I am not joking) and let it overwrite all profiles/filaments
8. Switch to the ``Prepare`` tab and switch the printer to ``Voron Trident-R2 0.4 nozzle``
9. Click on the Wifi symbol next to the printer to set the ``Hostname, IP or URL`` point to the printer ``$IP``, select as "Agent" ``Moonraker``
10. Select the correct Bed type (usually, ``Cool Plate`` is wrong) - stick to ``Textured PEI`` for now
11. Select the correct Filament type (the more precise the better)
12. Select the correct process type

    ``0.20mm Standard @Voron``
      is basically the default profile for Voron Trident 300

Bundle
======

Instead of manually downloading the presets in orcaslicaer (step 5-7), you can also just
use OrcaSlicer Cloud (requires login) and subscribe to
https://cloud.orcaslicer.com/b/3d738f62a3f7

Clear OrcaSlicer state
======================

This repository contains experimental configurations for Voron Trident-R2.
Changes will not be done in a backward or forward compatible way. So when
in doubt, please clear the Orcaslicer state::

  rm -rf ~/.cache/orca-slicer/ ~/.local/share/orca-slicer/ ~/.config/OrcaSlicer/
  rm -rf ~/.var/app/com.orcaslicer.OrcaSlicer/
