# FreeCAD tool library (metric only) — SainSmart / Genmitsu

SainSmart Genmitsu FreeCAD tool library rebuilt from the official resources on the [Genmitsu milling bits resource page](https://www.sainsmart.com/pages/genmitsu-milling-bits-resource-page-sainsmart).

## Installing the tool library in FreeCAD

This is the quickest way to get the full tool library running in FreeCAD without creating tools manually.

### 1. Copy the ToolBit files (`.fctb`)

Place all `.fctb` files where FreeCAD expects them.

**ToolBit folder**

- **Windows**  
  `C:\Users\<YourUsername>\AppData\Roaming\FreeCAD\Mod\CAM\Tools\Bit`

- **Linux**  
  `~/.local/share/FreeCAD/Mod/CAM/Tools/Bit`

- **macOS**  
  `~/Library/Application Support/FreeCAD/Mod/CAM/Tools/Bit`

Then copy every `.fctb` file into that folder.

### 2. Copy the library file (`.fctl`)

Install the library file that tells FreeCAD how to organise the tools.

**Library folder**

`.../Mod/CAM/Tools/Library`

(Use the same prefix as above for your OS, ending in `Mod/CAM/Tools/Library`.)

Then copy the `.fctl` file into this folder.

### 3. Restart FreeCAD

Close FreeCAD completely and reopen it. FreeCAD will not see new tools until it reloads.

### 4. Load the library

1. Open the **CAM** workbench.
2. Open the **ToolBit Library** editor.
3. Select your library (e.g. SainSmart Genmitsu Library).
4. Your tools should appear with their assigned tool numbers.

## Notes

- Keep `.fctb` files in the **Bit** folder and `.fctl` files in the **Library** folder.
- If you rename files, update the paths inside the `.fctl` file.
- On some systems you may need elevated permissions to copy into these directories.

## After setup

Once loaded, the library behaves like any native FreeCAD tool library and is available in your CAM jobs.

## Source documents

- `SainSmart Bits F360 3018-Metric(V3.0).json`
- `SainSmart Bits GWizard(V3.0).csv`

## Build rules

- Flat end mill → `endmill.fcstd`
- Ball end mill → `ballend.fcstd`
- Chamfer mill → `v-bit.fcstd`
- Drill → `drill.fcstd`
- Tapered mill / `tapered_ball` → `ballend.fcstd` approximation, with taper metadata preserved

## Angle handling

- V-bit included angle = `2 * TA`
- Drill point angle = `SIG` from Fusion JSON; where absent, a standard 118° point is assumed.

## Library notes

- No bullnose tools were identified in the provided source data.
- Eleven tapered-ball tools are included in the full library; they use `ballend.fcstd` because tapered-ball is not among the stock ToolShapes.
- A second library file omits those eleven tools for strict stock-shape compatibility.
