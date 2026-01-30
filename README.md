# LMU Electronic Bridge for SimHub

The **LMU Electronic Bridge** is a specialized plugin for Le Mans Ultimate (LMU) that synchronizes car electronic settings (Traction Control, ABS, Hybrid Maps, ARB) with SimHub Dashboards and Overlays.

Le Mans Ultimate does not "live broadcast" changes made to electronics via external APIs while driving. This plugin bridges that gap by tracking your button inputs and syncing with the game's internal garage data.

---

## 💾 Installation
1. Go to the [Releases](https://github.com/nikolaiNr7/LMUElectronicBridge/releases/tag/v1.0.0) page.
2. Download the latest `LMUElectronicBridge.dll`.
3. Right-click the DLL -> **Properties** -> Check **"Unblock"** (Windows security).
4. Copy the DLL into your SimHub installation folder (usually `C:\Program Files (x86)\SimHub`).
5. Restart SimHub and enable the plugin in the settings.
---

## 🎮 How to Use: Button Mapping

To keep your dashboard in sync with the car, you must map your electronic controls within the plugin:

1.  Open SimHub and navigate to the **LMU Electronics** tab.
2.  Find the setting you want to map (e.g., **TC Main**, **Regen**, or **ABS**).
3.  Click the **+ (Increase)** and **- (Decrease)** editors and press the corresponding button on your wheel/button box.
4.  **Crucial:** Ensure these same buttons are mapped inside the Le Mans Ultimate game settings.


---

## 📊 Using Data in Dashboards

The plugin provides custom properties that are much more descriptive than the default game values.

### Popular Properties
| Property | Description | Example Value |
| :--- | :--- | :--- |
| `[LMUElectronicBridge.Regen_Str]` | Current Hybrid Deployment | `51 kW` |
| `[LMUElectronicBridge.MotorMap_Str]` | Electric Motor Map | `Map 2` |
| `[LMUElectronicBridge.BrakeMigration_Str]` | Dynamic Brake Bias | `1.5% F` |
| `[LMUElectronicBridge.FrontARB_Str]` | Anti-Roll Bar Setting | `P3` |

**To add to a Dash:**
In Dash Studio, bind a text field to the NCalc formula: `[LMUElectronicBridge.Property_Name_Str]`.

---

## ⚠️ Important Limitations

> [!WARNING]
> **MFD SYNC LIMITATION**
> If you change settings using the **In-Game MFD (Multi-Function Display)** menu (using the D-pad), this plugin **cannot detect the change**. Your Dashboard will become "Out of Sync."
>
> **Always use your dedicated mapped buttons to change settings while driving.**

### How the Sync Works
The plugin is designed to be "Smart" but requires specific triggers to match the game exactly:
* **Garage Exit:** Values are automatically synced the moment you start your engine in the pits.
* **Session Change:** Values refresh when moving from Practice to Qualifying or Race.
* **Manual Sync:** Use the "Force Sync" button in the plugin settings if you suspect the data is wrong.

---

## ❓ Troubleshooting

* **Values show "N/A":** This car does not support this feature (e.g., GTE cars have no Regen).
* **Values show "-1":** The plugin hasn't talked to the game yet. Start the car or click "Force Sync."
* **Dashboard doesn't match MFD:** You likely used the in-game menu instead of your mapped buttons. Click "Force Sync" or return to the pits to reset.

---

## ⚖️ License & Terms

This project is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)**.

**What this means:**
* ✅ **Share:** You can copy and redistribute the material in any medium or format.
* ✅ **Adapt:** You can remix, transform, and build upon the material.
* ⚠️ **Attribution:** You must give appropriate credit and provide a link to the original repository.
* ❌ **Non-Commercial:** You may **not** use the material for commercial purposes (e.g., selling the DLL, including it in a paid dashboard pack, or charging for support).
