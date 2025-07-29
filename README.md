# Microbadge
Do you find Minibadges too big? Do you want to go even smaller? Try out the Microbadge! A minibadge can hold 6 of them!

The Microbadge is a 6mm x 6mm badge that uses 1.00mm pin headers to connect to a carrier board.
# Version 2! Do not use V1 anymore!
The Microbadge has been updated to V2 to support I2C, 1.00mm pins, and an additional 2x PROG pins for programming.  The microbadge has shrunk from 6.9mm to 6mm, and is small enough that you can fit 6 on a minibadge.

<img  height="400" alt="image" src="https://github.com/user-attachments/assets/2017b302-8d0c-4197-817d-e0df04d9d387" />


# Pictures
<img height="250" alt="Full Microbadge" src="https://github.com/user-attachments/assets/9416e99f-954c-4d11-9a21-1a8b5485afc8" /><img height="250" alt="Simple Microbadge" src="https://github.com/user-attachments/assets/481b4655-0e68-435f-9187-42f538a56e53" />

<img height="250" alt="Full Microbadge" src="https://github.com/user-attachments/assets/163dc83a-3495-4eae-8463-c900dab8fda4" /><img height="250" alt="Simple Microbadge" src="https://github.com/user-attachments/assets/8f2cdaf6-47dd-44bb-9ad6-3d44205e12f0" />

There are two Microbadge types - Simple and Full. Simple exposes +VBATT, CLK, 3x GND, and 2x +3v. The Full Microbadge adds two programming pins, and I2C SDA and SCL.

<img height="250" alt="Full Microbadge footprint" src="https://github.com/user-attachments/assets/dcfd611c-8b5e-4c43-9ec3-78b550eecfa8" />


 # Importing into Kicad
 1. From the **Project Viewer**, **Symbol Editor** or the **Schematic Editor**, select **Preferences** > **Manage Symbol Libraries...** 

<img width="289" height="218" alt="image" src="https://github.com/user-attachments/assets/7794d458-4bab-4ac6-8e24-288983d0cf00" />

 2. Under **Global Libraries**, click **Add Existing Library to Table**, Select the `Microbadge V2.kicad-sym` file. I personally put it in `Documents\KiCad\{version}\symbols` on Windows, there's an equivalent folder on Mac and Linux as well.
 3. From the **Project Viewer**, **Footprint Editor**, or **PCB Editor**, select **Preferences** > **Manage Footprint Libraries...** 

<img width="280" height="161" alt="image" src="https://github.com/user-attachments/assets/2f47b1a1-3200-4314-929e-d31f42843eb4" />

 4. Under **Global Libraries**, click **Add Existing**, Select the `Microbadge V2.pretty` folder. I personally put it in `Documents\KiCad\{version}\footprints` on Windows, there's an equivalent folder on Mac and Linux as well.

# Creating a Microbadge carrier board (Minibadge)
This assumes you already have the SAINTCON Minibadge footprints and symbols added to your libraries.
 1. Open the **Schematic Editor**, and import a Minibadge symbol and at least one Microbadge symbol.
 2. Atatch **Power Symbols** and **Global Labels** to the Minibadge symbol. If you want blinking, don't forget to connect CLK. 

<img height="400" alt="image" src="https://github.com/user-attachments/assets/d57700af-7a37-448e-8791-fa78a05269d9" />

 3. Atatch the same Symbols to each Microbadge symbol you created. Each symbol will be a microbadge socket. 

<img height="400" alt="image" src="https://github.com/user-attachments/assets/8fbb647b-0452-4b47-85f4-43814fbdd10e" />

 4. Select **Assign Footprints** > Assign a **Minibadge Footprint** (`Minibadge_Simple`, `Minibadge_Full`) to the **Minibadge** (not a slot), and assign a **Microbadge socket** footprint to the **Microbadges**. 

<img width="577" height="120" alt="image" src="https://github.com/user-attachments/assets/51ad0dd0-c56b-411c-bac4-76975eebf846" />

 5. Do your schematic and PCB work. Add LEDs, resistors, and other components.

# Creating a Microbadge
 1. Open the Schematic editor, and import a Microbadge symbol.
 2. Atatch **Power Symbols** and **Global Labels** to the microbadge. If you want blinking, don't forget to connect **CLK**. 

<img width="793" height="557" alt="image" src="https://github.com/user-attachments/assets/11b74ffe-0071-4f0c-a54c-854ac5d1f225" />

 3. Wire up your LEDs, resistors, and other components you want to use.
 4. Select **Assign Footprints** > Assign a Microbadge footprint (Square or Round, **not** a Socket!) to the **Microbadge**
 5. Assign `0603` or `0201` sized components to your LEDs and resistors. You have very little space to work with, so the smaller, the better.
 6. Do your PCB routing, silkscreening, etc.
