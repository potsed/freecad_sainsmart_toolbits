SainSmart Genmitsu FreeCAD tool library rebuilt from the provided Fusion 360 JSON and CSV.

Primary source:
- SainSmart Bits F360 3018-Metric(V3.0).json

Supplementary source:
- SainSmart Bits GWizard(V3.0).csv

Build rules:
- flat end mill -> endmill.fcstd
- ball end mill -> ballend.fcstd
- chamfer mill -> v-bit.fcstd
- drill -> drill.fcstd
- tapered mill / tapered_ball -> ballend.fcstd approximation, with taper metadata preserved

Angle handling:
- V-bit included angle = 2 * TA
- Drill point angle = SIG from Fusion JSON; where not present, standard 118 deg would be used

Notes:
- No bullnose tools were identified in the provided source data.
- 11 tapered-ball tools are included in the full library, but they use ballend.fcstd because tapered-ball was not among the stock ToolShapes you provided.
- A second library file excludes those 11 tools for strict stock-shape compatibility.

