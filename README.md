# Klipper-Config-file-
For Ender 3 / SKR Mini E3 V3 STM32G0B1 /  CR Touch / Sprite Pro direct drive all metal extruder

## Usage

`printer.cfg` is a Klipper config for:
- Creality Ender 3 (220x220x250)
- BIGTREETECH SKR Mini E3 V3.0 (STM32G0B1)
- BIGTREETECH CR Touch probe
- BIGTREETECH Sprite Pro direct drive extruder
- BIGTREETECH TFT35 running in Klipper/Touch mode (no printer.cfg entries needed)

Before printing:
1. Set `[mcu] serial` to your board's actual `/dev/serial/by-id/...` path.
2. Measure and correct `x_offset`/`y_offset` in `[bltouch]` for your CR Touch mount.
3. Run `PROBE_CALIBRATE` to set `z_offset`, then `SAVE_CONFIG`.
4. Calibrate extruder `rotation_distance` with a 100mm extrusion test.
5. Run `PID_CALIBRATE` for both the extruder and bed, then `SAVE_CONFIG`.
6. Run `BED_MESH_CALIBRATE` (or let `PRINT_START` do it) and check the mesh.
