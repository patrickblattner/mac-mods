# mac-mods
Contains all my Mac modifications that I use to maintain a consistent control experience across macOS, Linux, and Windows.

## Keyboard Mappings
When frequently switching between different system platforms (Mac, Linux, or Windows), the biggest issue is that the keys behave differently or are mapped inconsistently — even when using the same external keyboard.
Since I don’t want to constantly deal with that inconsistency, I simply standardized everything to match the majority setup: Linux and Windows.

For this, I use Karabiner with the following configurations:

```JSON
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
```

