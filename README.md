# slabv-zmk

ZMK firmware for a wireless [slabV](https://github.com/brickbots/slabv) (36-key MX unibody by brickbots) on a nice!nano v2.

The slabV has no ZMK shield upstream, so this repo carries one in `boards/shields/slabv/`. The matrix is the same as the chocV in QMK (rows F4 F5 D1 D0, cols B6 B2 B3 B1 F7 C6 D7 E6 B4 B5, COL2ROW), checked against the slabV KiCad netlist.

The keymap is my daemoncat40 layout from [qmk_userspace](https://github.com/jtcarrasco/qmk_userspace) (Keyboardio Atreus), without the Atreus centre cluster. Layers: QWERTY, NUM, FUN (F keys plus Bluetooth and USB/BLE output), MOUSE. Combos are the same vertical pairs.

## Build and flash

Push to GitHub and Actions builds the firmware (ZMK v0.3). Download the `firmware` artifact, double-tap reset on the nice!nano, and copy `slabv-nice_nano_v2-zmk.uf2` onto the drive that appears.

`settings_reset-nice_nano_v2-zmk.uf2` wipes stored Bluetooth pairings if they get stuck.

ZMK Studio is enabled over USB for remapping without reflashing.

## Battery

The slabV PCB has no battery pads. The LiPo is soldered to the nice!nano's B+/B- and sits under the controller.
