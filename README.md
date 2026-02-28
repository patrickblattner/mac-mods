# mac-mods

Contains all my Mac modifications that I use to maintain a consistent control experience across macOS, Linux, and Windows.

## Keyboard Mappings

When frequently switching between different system platforms (Mac, Linux, or Windows), the biggest issue is that the keys behave differently or are mapped inconsistently — even when using the same external keyboard.
Since I don’t want to constantly deal with that inconsistency, I simply standardized everything to match the majority setup: Linux and Windows.
For that I used Karabinger-Elements.

Dowmload Karabinger-Elements here:
https://karabiner-elements.pqrs.org/

Important note: This works properly for Logitech MX combined, with DE-CH Layout only!

### Installation

1. Download karabiner-elements
2. Setup karabiner-elements
3. Chose Chose "ISO (...)"
4. Open console
5. Execute the following commands:
```SHELL
cd ~/.config/karabiner/assets/complex_modifications
curl -O https://raw.githubusercontent.com/patrickblattner/mac-mods/main/keyboard/windows_like_basics.json
```
6. Right mouse click on the menu bar icon of karabinger-elements
7. Select "Restart Karabiner-Elements"
8. Right mouse click on the menu bar icon of karabinger-elements
9. Select "Settings..."
10. Select "Device"
10. Activate "Modify events" for only the "Logitech MX Keyboard"
11. Select "Virtual Keyboard"
12. Chose "ISO (...)"
13. Select "Profiles"
14. Press "Add New Profile"
15. Name it as you wanna, lets say MX for this tutorial
16. Select Profile "MX"
16. Select "Complex Modifications"
17. Select "Add predefined rule"
18. Select under "Windows basics: Ctrl...", the button "Enable all"
