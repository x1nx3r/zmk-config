# SLEC61 Matrix Pinout (nice!nano v2 / nRF52840)

**Diode direction:** `col2row` · **Matrix:** 14 columns × 5 rows

---

## Row Pinout

| Row | Pro Micro Pin | nRF52840 GPIO | PCB Label | GPIO Config                |
| --- | ------------- | ------------- | --------- | -------------------------- |
| R0  | `4`           | P0.20         | `020`     | `ACTIVE_HIGH \| PULL_DOWN` |
| R1  | `5`           | P0.22         | `022`     | `ACTIVE_HIGH \| PULL_DOWN` |
| R2  | `6`           | P0.24         | `024`     | `ACTIVE_HIGH \| PULL_DOWN` |
| R3  | `7`           | P1.00         | `100`     | `ACTIVE_HIGH \| PULL_DOWN` |
| R4  | `8`           | P0.11         | `011`     | `ACTIVE_HIGH \| PULL_DOWN` |

## Column Pinout

| Col | Pro Micro Pin | nRF52840 GPIO | PCB Label | GPIO Config   |
| --- | ------------- | ------------- | --------- | ------------- |
| C0  | `21`          | P0.31         | `031`     | `ACTIVE_HIGH` |
| C1  | `20`          | P0.29         | `029`     | `ACTIVE_HIGH` |
| C2  | `19`          | P0.02         | `002`     | `ACTIVE_HIGH` |
| C3  | `18`          | P1.15         | `115`     | `ACTIVE_HIGH` |
| C4  | `15`          | P1.11         | `111`     | `ACTIVE_HIGH` |
| C5  | `14`          | P0.10         | `010`     | `ACTIVE_HIGH` |
| C6  | `16`          | P1.13         | `113`     | `ACTIVE_HIGH` |
| C7  | `10`          | P1.06         | `106`     | `ACTIVE_HIGH` |
| C8  | `9`           | P1.04         | `104`     | `ACTIVE_HIGH` |
| C9  | `2`           | P0.15         | `015`     | `ACTIVE_HIGH` |
| C10 | `3`           | P0.17         | `017`     | `ACTIVE_HIGH` |
| C11 | `0`           | P0.08         | `008`     | `ACTIVE_HIGH` |
| C12 | `1`           | P0.06         | `006`     | `ACTIVE_HIGH` |
| C13 | `gpio1 1`     | P1.01         | `101`     | `ACTIVE_HIGH` |

---

## nice!nano v2 Pin Mapping

```
                  ┌──────────────┐
  C11  P0.08 ─────┤ D0       RAW ├
  C12  P0.06 ─────┤ D1       GND ├
   C9  P0.15 ─────┤ D2   RST/GND ├
  C10  P0.17 ─────┤ D3       VCC ├
   R0  P0.20 ─────┤ D4       021 ├───── P0.31  C0
   R1  P0.22 ─────┤ D5       020 ├───── P0.29  C1
   R2  P0.24 ─────┤ D6       019 ├───── P0.02  C2
   R3  P1.00 ─────┤ D7       018 ├───── P1.15  C3
   R4  P0.11 ─────┤ D8       015 ├───── P1.11  C4
   C8  P1.04 ─────┤ D9       014 ├───── P0.10  C5
   C7  P1.06 ─────┤ D10      016 ├───── P1.13  C6
                  └──────┬───────┘
                    ┌────┴────┐
                    │101│102│107│  ← 3 extra bottom pads
                    └───┴───┴───┘
                     C13  ·   ·
                    P1.01 P1.02 P1.07
                    (used) (free) (free)
```

---

## Key Matrix Layout

```
Row 0: │ 0,0 │ 0,1 │ 0,2 │ 0,3 │ 0,4 │ 0,5 │ 0,6 │ 0,7 │ 0,8 │ 0,9 │0,10 │0,11 │0,12 │0,13 │
       │ ESC │  1  │  2  │  3  │  4  │  5  │  6  │  7  │  8  │  9  │  0  │  -  │  =  │BKSP │

Row 1: │ 1,0  │ 1,1 │ 1,2 │ 1,3 │ 1,4 │ 1,5 │ 1,6 │ 1,7 │ 1,8 │ 1,9 │1,10 │1,11 │1,12 │1,13 │
       │ TAB  │  Q  │  W  │  E  │  R  │  T  │  Y  │  U  │  I  │  O  │  P  │  [  │  ]  │  \  │

Row 2: │ 2,0   │ 2,1 │ 2,2 │ 2,3 │ 2,4 │ 2,5 │ 2,6 │ 2,7 │ 2,8 │ 2,9 │2,10 │2,11 │   2,12   │
       │ CAPS  │  A  │  S  │  D  │  F  │  G  │  H  │  J  │  K  │  L  │  ;  │  '  │  ENTER   │

Row 3: │ 3,0     │ 3,1 │ 3,2 │ 3,3 │ 3,4 │ 3,5 │ 3,6 │ 3,7 │ 3,8 │ 3,9 │3,10 │   3,11    │
       │ LSHIFT  │  Z  │  X  │  C  │  V  │  B  │  N  │  M  │  ,  │  .  │  /  │  RSHIFT   │

Row 4: │ 4,0 │ 4,1 │ 4,2 │          4,5           │ 4,9 │4,10 │4,11 │4,12 │
       │LCTL │LGUI │LALT │         SPACE           │RALT │ FN  │MENU │RCTL │
```

---

## Notes

- **Diode direction** is `col2row` — diodes point from column wire to row wire (anode on column, cathode on row).
- **PCB Labels** use the nRF52840 GPIO numbering format: `PXY` → `XYY` (e.g., P0.31 → `031`, P1.15 → `115`).
- **Column ordering** is non-sequential on Pro Micro pins: `21→20→19→18→15→14→16→10→9→2→3→0→1`.
- **Extra bottom pads** — the nice!nano v2 has 3 bonus GPIOs below the main footprint:
  - `101` (P1.01) → **used** as Column 13
  - `102` (P1.02) → **free**
  - `107` (P1.07) → **free**
