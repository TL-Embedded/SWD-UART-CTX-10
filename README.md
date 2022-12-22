# SWD-UART-CTX-10

This is an adaptor for the 10 pin tag-connect cables.

**Output:**
 * TC2050 or EC10 ribbon

**Input:**
 * UART via standard FTDI header
 * SWD via standard 20 pin ARM header
 * Auxilary voltage input

This is compatible with the Tag-Connect `TC2050-ARM2010 ARM 20-pin to TC2050 Adapter` in SWD mode.

# Target pinout

On the target, the TC2050 or EC10 should have the following assignment.

| Pin# | Function   |
| ---- | --------   |
| 1    | VCC_Target |
| 2    | SWDIO      |
| 3    | GND        |
| 4    | SWCLK      |
| 5    | VCC_Aux    |
| 6    | SWO        |
| 7    | TX (to target) |
| 8    | Detect     |
| 9    | RX (from target) |
| 10   | Reset      |

When the pins are arranged for the TC2050, the pinout is a bit more obvious:

| Function        | Pin# | Pin# | Function   |
| --------        | ---- | ---- | --------   |
| VCC_Target      | 1    | 2    | SWDIO      |
| GND             | 3    | 4    | SWCLK      |
| VCC_Aux         | 5    | 6    | SWO        |
| TX (to target)  | 7    | 8    | Detect     |
| RX (from target)| 9    | 10   | Reset      |

## Detect

This pin is tied to ground on the adaptor - and can be used by the target to sense the presence of the adaptor.

## VCC_Aux

This is tied to the `V+` pin. This is an optional input for providing arbitrary power to the target.

## TX & RX

The Tx and Rx are described with respect to the host, **not the target**.
