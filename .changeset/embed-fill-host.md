---
'@ioai/lerobot-studio': minor
---

The embedded viewer now fills its host container. The package stylesheet is scoped to descendants of `.lerobot-root`, so the `h-full w-full` utilities on the root element itself never matched and the viewer collapsed to its content height. A base-layer `.lerobot-root` rule now sets `position: relative`, `width` / `height: 100%`, `min-width` / `min-height: 0`, and the theme `background-color` and `color`; host CSS passed through `className` still wins. In a host whose wrapper has a fixed height the viewer now stretches to it.

Below 640px of container width (the `@container/viewer` box, not the window) the episode sidebar moves under the player and stays resizable (drag the handle, or focus it and use the arrow keys; it is named "Resize episode list" and reports its size range through `aria-valuenow`, `aria-valuemin` and `aria-valuemax`). The sidebar follows the player in DOM and focus order, is moved rather than remounted when the container crosses 640px, and keeps the width the user chose. At the same width the playback bar wraps: progress on its own row, transport centred, FPS and version hidden.
