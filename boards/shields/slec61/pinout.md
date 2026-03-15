# SLEC61 Matrix Pinout (nice!nano v2 / nRF52840)

**Diode direction:** `col2row` · **Matrix:** 14 columns × 5 rows

---

## Row Pinout

| Row | Pro Micro Pin | nRF52840 GPIO | PCB Label | GPIO Config                |
| --- | ------------- | ------------- | --------- | -------------------------- |
| R0  | `4`           | P0.22         | `022`     | `ACTIVE_HIGH \| PULL_DOWN` |
| R1  | `5`           | P0.24         | `024`     | `ACTIVE_HIGH \| PULL_DOWN` |
| R2  | `6`           | P1.00         | `100`     | `ACTIVE_HIGH \| PULL_DOWN` |
| R3  | `7`           | P0.11         | `011`     | `ACTIVE_HIGH \| PULL_DOWN` |
| R4  | `8`           | P1.04         | `104`     | `ACTIVE_HIGH \| PULL_DOWN` |

## Column Pinout

| Col | Pro Micro Pin | nRF52840 GPIO | PCB Label | GPIO Config   |
| --- | ------------- | ------------- | --------- | ------------- |
| C0  | `21`          | P0.31         | `031`     | `ACTIVE_HIGH` |
| C1  | `20`          | P0.29         | `029`     | `ACTIVE_HIGH` |
| C2  | `19`          | P0.02         | `002`     | `ACTIVE_HIGH` |
| C3  | `18`          | P1.15         | `115`     | `ACTIVE_HIGH` |
| C4  | `15`          | P1.13         | `113`     | `ACTIVE_HIGH` |
| C5  | `14`          | P1.11         | `111`     | `ACTIVE_HIGH` |
| C6  | `16`          | P0.10         | `010`     | `ACTIVE_HIGH` |
| C7  | `10`          | P0.09         | `009`     | `ACTIVE_HIGH` |
| C8  | `9`           | P1.06         | `106`     | `ACTIVE_HIGH` |
| C9  | `2`           | P0.17         | `017`     | `ACTIVE_HIGH` |
| C10 | `3`           | P0.20         | `020`     | `ACTIVE_HIGH` |
| C11 | `0`           | P0.08         | `008`     | `ACTIVE_HIGH` |
| C12 | `1`           | P0.06         | `006`     | `ACTIVE_HIGH` |
| C13 | `gpio1 1`     | P1.01         | `101`     | `ACTIVE_HIGH` |

---

## SuperMini nRF52840 Pin Mapping

```
(left side)       ┌──────────────┐      (right side)
  BATT NEG  B- ───┤ B-        B+ ├─── B+  BATT POS
   C12     006 ───┤ 006      RAW ├─── RAW
   C11     008 ───┤ 008      GND ├─── GND
           GND ───┤ GND      RST ├─── RST
           GND ───┤ GND      VCC ├─── VCC
    C9     017 ───┤ 017      031 ├─── 031  C0
   C10     020 ───┤ 020      029 ├─── 029  C1
    R0     022 ───┤ 022      002 ├─── 002  C2
    R1     024 ───┤ 024      115 ├─── 115  C3
    R2     100 ───┤ 100      113 ├─── 113  C4
    R3     011 ───┤ 011      111 ├─── 111  C5
    R4     104 ───┤ 104      010 ├─── 010  C6
    C8     106 ───┤ 106      009 ├─── 009  C7
                  └──────┬───────┘
                    ┌────┴────┐
                    │101│102│107│  ← 3 extra bottom pads
                    └───┴───┴───┘
                     C13  ·   ·
                    P1.01
                    (used)
```

---

## Key Matrix Layout

```
Row 0: │ 0,0 │ 0,1 │ 0,2 │ 0,3 │ 0,4 │ 0,5 │ 0,6 │ 0,7 │ 0,8 │ 0,9 │0,10 │0,11 │0,12 │0,13 │
       │ ESC │  1  │  2  │  3  │  4  │  5  │  6  │  7  │  8  │  9  │  0  │  -  │  =  │BKSP │

Row 1: │ 1,0  │ 1,1 │ 1,2 │ 1,3 │ 1,4 │ 1,5 │ 1,6 │ 1,7 │ 1,8 │ 1,9 │1,10 │1,11 │1,12 │1,13 │
       │ TAB  │  Q  │  W  │  E  │  R  │  T  │  Y  │  U  │  I  │  O  │  P  │  [  │  ]  │  \  │

Row 2: │ 2,0   │ 2,1 │ 2,2 │ 2,3 │ 2,4 │ 2,5 │ 2,6 │ 2,7 │ 2,8 │ 2,9 │2,10 │2,11 │     2,13     │
       │ CAPS  │  A  │  S  │  D  │  F  │  G  │  H  │  J  │  K  │  L  │  ;  │  '  │    ENTER     │

Row 3: │ 3,0     │ 3,1 │ 3,2 │ 3,3 │ 3,4 │ 3,5 │ 3,6 │ 3,7 │ 3,8 │ 3,9 │3,10 │3,11 │   3,13   │
       │ LSHIFT  │  Z  │  X  │  C  │  V  │  B  │  N  │  M  │  ,  │  .  │  /  │ FN  │  RSHIFT  │

Row 4: │ 4,0 │ 4,1 │ 4,2 │          4,5           │ 4,9 │     │4,12 │4,13 │
       │LCTL │LGUI │LALT │         SPACE           │RALT │     │MENU │RCTL │
```

---

## Notes

- **Diode direction** is `col2row` — diodes point from column wire to row wire (anode on column, cathode on row).
- **PCB Labels** use the nRF52840 GPIO numbering format: `PX.YY` → `XYY` (e.g., P0.31 → `031`, P1.15 → `115`).
- **Column ordering** is non-sequential on Pro Micro pins: `21→20→19→18→15→14→16→10→9→2→3→0→1`.
- **Unlabeled pin** on the left side (between `008` and GND) — not used in this design.
- **Extra bottom pads** — the nice!nano v2 has 3 bonus GPIOs below the main footprint:
  - `101` (P1.01) → **used** as Column 13
  - `102` (P1.02) → **free**
  - `107` (P1.07) → **free**
