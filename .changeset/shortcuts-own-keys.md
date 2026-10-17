---
'@ioai/lerobot-studio': patch
---

Playback shortcuts (Space, arrow keys) no longer fire while a widget that owns those keys has focus: tabs, sliders, radios, checkboxes, menus, listboxes and resize handles. A focused button or link keeps Space for its own activation (one press, one click), while the arrow keys still step playback there; with focus on the page or an episode row, Space plays and pauses. Element checks are realm-safe for hosts that render into another window.
