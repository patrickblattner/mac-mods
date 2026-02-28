# mac-mods

Contains all my Mac modifications that I use to maintain a consistent control experience across macOS, Linux, and Windows.

## Keyboard Mappings



When frequently switching between different system platforms (Mac, Linux, or Windows), the biggest issue is that the keys behave differently or are mapped inconsistently — even when using the same external keyboard.
Since I don’t want to constantly deal with that inconsistency, I simply standardized everything to match the majority setup: Linux and Windows.



Dowmload Karabinger-Elements here:
https://karabiner-elements.pqrs.org/

### Installation

1. Download karabiner-elements
2. Setup karabiner-elements
3. Open console
4. Execute the following commands:
```SHELL
cd ~/.config/karabiner/assets/complex_modifications
nano windows_like_basics.json
cat << 'EOF' > ~/.config/karabiner/assets/complex_modifications/windows-basics.json
{
  "title": "Windows basics: Ctrl C/V/X/Z + Shift+Z Redo + Home/End",
  "rules": [
    {
      "description": "Fix Swiss keyboard: § and < swap (inkl. Shift)",
      "manipulators": [
        {
          "type": "basic",
          "from": { "key_code": "grave_accent_and_tilde", "modifiers": { "mandatory": ["shift"] } },
          "to": [{ "key_code": "non_us_backslash", "modifiers": ["shift"] }]
        },
        {
          "type": "basic",
          "from": { "key_code": "non_us_backslash", "modifiers": { "mandatory": ["shift"] } },
          "to": [{ "key_code": "grave_accent_and_tilde", "modifiers": ["shift"] }]
        },
        {
          "type": "basic",
          "from": { "key_code": "grave_accent_and_tilde" },
          "to": [{ "key_code": "non_us_backslash" }]
        },
        {
          "type": "basic",
          "from": { "key_code": "non_us_backslash" },
          "to": [{ "key_code": "grave_accent_and_tilde" }]
        }
      ]
    },
    {
      "description": "Ctrl+C/V/X -> Cmd+C/V/X (except terminals)",
      "manipulators": [
        {
          "type": "basic",
          "from": { "key_code": "c", "modifiers": { "mandatory": ["control"] } },
          "to": [{ "key_code": "c", "modifiers": ["command"] }],
          "conditions": [{ "type": "frontmost_application_unless", "bundle_identifiers": ["^com\\.apple\\.Terminal$", "^com\\.googlecode\\.iterm2$", "^co\\.zeit\\.hyper$", "^com\\.github\\.wez\\.wezterm$"] }]
        },
        {
          "type": "basic",
          "from": { "key_code": "v", "modifiers": { "mandatory": ["control"] } },
          "to": [{ "key_code": "v", "modifiers": ["command"] }],
          "conditions": [{ "type": "frontmost_application_unless", "bundle_identifiers": ["^com\\.apple\\.Terminal$", "^com\\.googlecode\\.iterm2$", "^co\\.zeit\\.hyper$", "^com\\.github\\.wez\\.wezterm$"] }]
        },
        {
          "type": "basic",
          "from": { "key_code": "x", "modifiers": { "mandatory": ["control"] } },
          "to": [{ "key_code": "x", "modifiers": ["command"] }],
          "conditions": [{ "type": "frontmost_application_unless", "bundle_identifiers": ["^com\\.apple\\.Terminal$", "^com\\.googlecode\\.iterm2$", "^co\\.zeit\\.hyper$", "^com\\.github\\.wez\\.wezterm$"] }]
        }
      ]
    },
    {
      "description": "Ctrl+Z -> Cmd+Z (Undo), Ctrl+Shift+Z -> Cmd+Shift+Z (Redo) (except terminals)",
      "manipulators": [
        {
          "type": "basic",
          "from": { "key_code": "y", "modifiers": { "mandatory": ["control", "shift"] } },
          "to": [{ "key_code": "y", "modifiers": ["command", "shift"] }],
          "conditions": [{ "type": "frontmost_application_unless", "bundle_identifiers": ["^com\\.apple\\.Terminal$", "^com\\.googlecode\\.iterm2$", "^co\\.zeit\\.hyper$", "^com\\.github\\.wez\\.wezterm$"] }]
        },
        {
          "type": "basic",
          "from": { "key_code": "y", "modifiers": { "mandatory": ["control"] } },
          "to": [{ "key_code": "y", "modifiers": ["command"] }],
          "conditions": [{ "type": "frontmost_application_unless", "bundle_identifiers": ["^com\\.apple\\.Terminal$", "^com\\.googlecode\\.iterm2$", "^co\\.zeit\\.hyper$", "^com\\.github\\.wez\\.wezterm$"] }]
        }
      ]
    },
    {
      "description": "Home/End -> Cmd+Left/Right",
      "manipulators": [
        {
          "type": "basic",
          "from": { "key_code": "home" },
          "to": [{ "key_code": "left_arrow", "modifiers": ["command"] }]
        },
        {
          "type": "basic",
          "from": { "key_code": "end" },
          "to": [{ "key_code": "right_arrow", "modifiers": ["command"] }]
        }
      ]
    }
  ]
}
EOF
```
5. Right mouse click on the menu bar icon of karabinger-elements
6. Select "Restart Karabiner-Elements"
7. Right mouse click on the menu bar icon of karabinger-elements
8. Select "Settings..."
9. Select "Device"
10. Activate "Modify events" for only the "Logitech MX Keyboard"
11. Select "Virtual Keyboard"
12. Chose "ISO (...)"
13. Select "Profiles"
14. Press "Add New Profile"
15. Name it as you wanna, lets say MX for this tutorial
16. Select Profile "MX"

