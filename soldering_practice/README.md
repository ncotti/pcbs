# About footprints

QFN / VQFN / WQFN all have the same pad size, it only differs on height and whether you can see the pads from the side.

Can you give a table comparing pitch, pad size and stuff of the different SMD packages, for example QFN, SOIC, TSSOP, SSOP, etc?

Absolutely — here’s a clear comparison table of common SMD packages with their typical lead/pin pitch, approximate pad sizes, and other relevant characteristics. Note that exact pad sizes depend on the specific package variant & manufacturer; values here are typical reference guidelines used for PCB land-pattern design (e.g., IPC recommendations and common practice).

| **Package**                   | **Typical Pitch**       | **Pad Type**           | **Typical Pad Width / Length**     | **Notes / Characteristics**                                            |
| ----------------------------- | ----------------------- | ---------------------- | ---------------------------------- | ---------------------------------------------------------------------- |
| **SOIC** (Small Outline *IC*) | 1.27 mm                 | Gull-wing pads         | ~0.51 mm × ~1.5–2.0 mm             | Through-hole style IC replacement, easy hand soldering                 |
| **SSOP** (Shrink SOIC)        | 0.65 mm – 0.80 mm       | Gull-wing pads         | ~0.30 mm × ~1.0–1.4 mm             | Narrow body, finer than SOIC but still easy to solder                  |
| **TSSOP** (Thin SSOP)         | 0.65 mm – 0.80 mm       | Gull-wing pads         | ~0.25 mm × ~0.8–1.0 mm             | Thin profile, reduced width vs SSOP                                    |
| **MSOP** (Mini SSOP)          | 0.65 mm                 | Gull-wing pads         | ~0.20 mm × ~0.8 mm                 | Very small variant of SSOP                                             |
| **QFN** (Quad Flat No-lead)   | 0.40 mm – 1.0 mm        | Bottom pads (no leads) | Pad ~0.30–0.40 mm square (per pin) | Excellent electrical/thermal; requires stencil and good reflow control |
| **DFN** (Dual Flat No-lead)   | 0.40 mm – 0.80 mm       | Bottom pads            | Similar to QFN (per pin)           | Smaller QFN family for fewer pins                                      |
| **QFP** (Quad Flat *IC*)      | 0.40 mm – 0.80 mm       | Gull-wing              | ~0.25–0.35 mm × ~0.8–1.2 mm        | Classic leaded QFP                                                     |
| **LQFP** (Low-profile QFP)    | 0.50 mm – 0.80 mm       | Gull-wing              | ~0.30–0.40 mm × ~0.9–1.2 mm        | Lower height vs QFP                                                    |
| **BGA** (Ball Grid Array)     | 0.50 mm – 1.27 mm balls | Solder balls (pads)    | ~0.30–0.40 mm pads                 | Best for high pin counts; needs X-ray for inspection                   |
| **WLCSP** (Wafer-Level CSP)   | 0.40 mm – 0.80 mm       | Solder balls           | ~0.20–0.30 mm                      | Very small; direct die packaging                                       |
| **SOT-23** (Discrete)         | –                       | Leaded, gull-wing      | ~0.40 mm × ~1.2 mm                 | 3-lead transistor/regulator package                                    |
| **SOT-223**                   | –                       | Leaded                 | ~1.0 mm × ~2.2 mm                  | Power discrete package                                                 |
| **TO-263 (D2PAK)**            | –                       | Leaded                 | ~1.3 mm × ~3.0+ mm                 | Power device package                                                   |

📊 How to Read This
🧩 Pitch

Distance between centers of adjacent pins.

Smaller pitch → higher density and more challenging routing/soldering.

📏 Pad Size

Approximate PCB copper pad dimensions.

For QFN/DFN/BGA, the pad is directly under the device — critical for solder volume & thermal performance.

📌 Pad Type

Gull-wing = conventional outward bent pins.

Bottom pads = pins under body (QFN/BGA/DFN).

Solder balls = BGA/WLCSP.

📈 General Notes

SOIC → SSOP → TSSOP → MSOP: progressively smaller pitch & body.

QFN/DFN: very low profile, great for thermal/electrical performance, but require good stencil design.

BGA: extremely high pin count but requires precise assembly & inspection tools.

🛠️ Typical IPC Footprint Considerations

When designing PCB footprints you usually consult:

IPC-7351 standard (land patterns for surface mount)

Package specific datasheet (exact pad, courtyard & solder mask values)

Example design tips:

For 0.65 mm pitch TSSOP: pad length ≈ 0.8–1.0 mm, pad spacing based on pitch

For QFN 0.5 mm pitch: pad width ~0.25–0.30 mm, keep solder mask opening slightly smaller than pad

For BGA 0.8 mm pitch: pad dia ~0.35 mm, solder mask defined for paste control

| **Package Group**   | **Ease of Hand-Soldering** | **Routing Difficulty** | **Best For**                   |
| ------------------- | -------------------------- | ---------------------- | ------------------------------ |
| SOIC / SSOP / TSSOP | 👍 Easy                    | 🟢 Moderate            | Low-medium pin logic/ICs       |
| QFP / LQFP          | 🙂 OK                      | 🟡 Moderate-High       | Mid-count microcontrollers     |
| QFN / DFN           | ⚠️ Tough                   | 🔴 High                | Performance/compact ICs        |
| BGA / WLCSP         | ❗ Hardest                  | 🔴 Very High           | High pin count/miniaturization |


https://chatgpt.com/c/694fe0f6-76b0-8327-ae25-6591ec4e33aa