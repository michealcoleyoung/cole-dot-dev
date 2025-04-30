```bash
theme = "gruvbox_dark_hard"

[editor]
line-number = "relative"
mouse = false

[editor.cursor-shape]
insert = "bar"
normal = "block"
select = "underline"

[editor.file-picker]
hidden = false

[editor.auto-save]
# Enable automatic saving on the focus moving away from Helix.
# Requires focus event support from your terminal
focus-lost = true

# Enable automatic saving after auto-save.after-delay.timeout
# milliseconds have passed since last edit.
after-delay.enable = true

# Time in milliseconds since last edit before auto save timer triggers.
after-delay.timeout = 1000
```