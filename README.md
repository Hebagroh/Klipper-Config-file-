# Klipper-Config-file-
For Ender 3 / SKR Mini E3 V3 STM32G0B1 /  CR Touch / Sprite Pro direct drive all metal extruder

## Usage

Both configs are for the same printer and peripherals -- a Creality Ender 3
(220x220x250) with a BIGTREETECH CR Touch probe, a BIGTREETECH Sprite Pro
direct drive extruder, and a BIGTREETECH TFT35 running in Klipper/Touch
mode (no printer.cfg entries needed for the TFT35 either way) -- just on
different mainboards:

- `printer.cfg` -- BIGTREETECH SKR Mini E3 V3.0 (STM32G0B1), TMC2209 drivers
- `printer-creality-v4.2.7.cfg` -- Creality/Sovol "Silent" Board V4.2.7
  (STM32F103), onboard TMC2225 drivers (fixed current/microsteps, not
  software-configurable on this board)

Use whichever file matches your mainboard as your `printer.cfg` on the Pi.

Before printing:
1. Set `[mcu] serial` to your board's actual `/dev/serial/by-id/...` path.
2. Measure and correct `x_offset`/`y_offset` in `[bltouch]` for your CR Touch mount.
3. Run `PROBE_CALIBRATE` to set `z_offset`, then `SAVE_CONFIG`.
4. Calibrate extruder `rotation_distance` with a 100mm extrusion test.
5. Run `PID_CALIBRATE` for both the extruder and bed, then `SAVE_CONFIG`.
6. Run `BED_MESH_CALIBRATE` (or let `PRINT_START` do it) and check the mesh.
