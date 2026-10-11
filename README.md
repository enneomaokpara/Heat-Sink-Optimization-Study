## Heat-Sink-Optimization-Study
Parametric thermal optimization of a plate-fin heat sink in Fusion 360. Five design variants tested, best cooling-per-gram identified.
# Objective
Find the fin design that gives the most cooling per gram of aluminum — not just the coldest design, but the most efficient one.
# Design (baseline, Case O)
Modeled in Fusion 360 (Education license):
﻿﻿Base plate: 100 × 60 mm, 6 mm thick, 10 mm corner radii
﻿﻿4 x mounting holes, 6 mm diameter, one per corner
﻿﻿Fins: 14 × plate fins, 1.5 mm thick, 50 mm long, 40 mm tall
﻿﻿# Material: Aluminum 6061
Simulation setup (identical for all cases)
﻿﻿# Study type: Steady-state thermal (Fusion 360 Simulation)
﻿﻿Bottom face: fixed temperature 353.15 K (80degreesC) - simulates a hot chip
﻿﻿All other faces: convection, film coefficient 15 W/(m2K), ambient 293.15 K (20 °C)
﻿﻿Mesh: default auto-mesh, regenerated per variant
## Results https://bravemailuncp-my.sharepoint.com/:x:/g/personal/eno002_bravemail_uncp_edu/IQCmDs-xxvy0Qr6u8Sj6EqG4AQDGREQoVrNIfKXV40_ikHY?e=ziKbmr
# Analytical validation (MATLAB)
A 1D fin-theory hand check (heatsink_check.m) was run against the baseline case:
• Fin parameter mH = 0.44, adiabatic-tip solution
• Analytical tip temp: 74.5 °C
• Simulation tip temp: 78.1°C
• Agreement within 3.6 °C (tolerance: 15 °C) - PASS
## Conclusion
Case 2 (1.5 mm × 17 fins) wins at 0.01010 K/g - roughly 2.7x better cooling per gram than the baseline.
# What the data shows:
• Fewer, widely spaced fins (Case 1) beat the baseline — each fin gets more airflow.
• But more fins (Case 2) won overall: the extra surface area outweighed the extra mass.
• Thicker fins (Case 4) were the heaviest and scored worst - more metal, diminishing returns.
# Takeaway: for this footprint, more closely-packed fins are the most mass-efficient way to cool.
## Files
• full data table with formulas
• CAD screenshots: isometric, front, top views
• Simulation plots: baseline vs. winner temperature plots
