# kbd-swap

driver PoC that intercepts keyboard input by swapping the `KeyboardClassServiceCallback` pointer in `kbdclass.sys`

### How it works?
1. Opens a handle to `\Device\KeyboardClass0`.
2. Locates the `DeviceExtension` structure.
3. Swaps the original `ServiceCallback` pointer with our custom hook to log key events (`MakeCode` and `Flags`)
