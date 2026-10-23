# UglyBot for MicroBlocks

Easy driving blocks for the **Myndsets UglyBot** two-wheel robot, built on an **ESP32 DevKit V1** and a **TB6612FNG** motor driver.

## Open it in one click

**[Open UglyBot in MicroBlocks](https://microblocks.fun/run/microblocks.html#project=https://raw.githubusercontent.com/levidontackerman/uglybot-microblocks/main/UglyBot.ubp)**

The link opens MicroBlocks in Chrome or Edge with the UglyBot blocks already loaded. There's nothing to install. Plug in the ESP32 and click **Connect → connect (USB)**.

## Wiring (ESP32 DevKit V1)

| Motor | Speed (PWM) | Direction |
|---|---|---|
| Left (A) | GPIO 32 | AIN1 33, AIN2 25 |
| Right (B) | GPIO 27 | BIN1 26, BIN2 13 |

- TB6612 **VCC** and **STBY** go to the ESP32 **3V3** pin.
- The ESP32 takes power on **VIN** from the 5 V regulator. Motors run from the driver's **VM**.
- All grounds are joined.

Speed pins avoid GPIO 25 and 26, because MicroBlocks drives those as DAC outputs, not PWM.

## Blocks

| Block | What it does |
|---|---|
| go [forward ▾] at speed 50 % | Keeps moving: forward, backward, turn left/right, spin left/right |
| go [forward ▾] at speed 50 % for 1000 ms | Moves for a time, then brakes (1000 ms = 1 second) |
| stop UglyBot | Brakes both wheels |
| set left wheel 50 % right wheel 50 % | Each wheel -100 to 100 (negative = backward, 0 = brake) |
| set [left ▾] wheel speed to 50 % | One wheel, or both |
| stop UglyBot with [brake ▾] | Brake, or coast to a stop |
| flip [left ▾] wheel direction | Fixes a wheel that turns the wrong way |
| set wheel balance left 100 % right 100 % | Lower the faster wheel if UglyBot drifts |
| set UglyBot pins … | Only for a robot wired differently |

## Files

- **UglyBot.ubp**: starter project with the library inside (this is what the link opens)
- **UglyBot.ubl**: the library on its own (drag it into MicroBlocks, or use Add Library)

MIT License · Myndsets
