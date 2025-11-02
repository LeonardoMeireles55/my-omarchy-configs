# 🌀 Hyprland + Walker Configuration

## 🧩 Theme Import
```css
@import "../../../../../../../.config/omarchy/current/theme/walker.css";
```

---

## 🎨 Walker (GTK) Style

```css
* {
  all: unset;
  border-radius: 8px;
  font-family: monospace;
  font-size: 18px;
  color: @text;
}

scrollbar {
  opacity: 0;
}

.normal-icons { -gtk-icon-size: 16px; }
.large-icons { -gtk-icon-size: 32px; }

.box-wrapper {
  background: alpha(@base, 0.95);
  padding: 20px;
  border: 0px solid @border;
}

.search-container {
  background: @base;
  padding: 10px;
}

.input placeholder { opacity: 0.5; }
.input:focus, .input:active { box-shadow: none; outline: none; }

.item-box { padding-left: 14px; }
.item-text-box { all: unset; padding: 14px 0; }

.item-subtext {
  font-size: 0px;
  min-height: 0px;
  margin: 0px;
  padding: 0px;
}

.item-image {
  margin-right: 14px;
  -gtk-icon-transform: scale(0.9);
}

child:selected .item-box * { color: @selected-text; }
.current { font-style: italic; }

.keybind-hints {
  background: @background;
  padding: 10px;
  margin-top: 10px;
}

.preview { background: @background; }
```

---

## ⚙️ Hyprland Configuration

### Default Sources
```ini
# Omarchy defaults
source = ~/.local/share/omarchy/default/hypr/autostart.conf
source = ~/.local/share/omarchy/default/hypr/bindings/media.conf
source = ~/.local/share/omarchy/default/hypr/bindings/clipboard.conf
source = ~/.local/share/omarchy/default/hypr/bindings/tiling-v2.conf
source = ~/.local/share/omarchy/default/hypr/bindings/utilities.conf
source = ~/.local/share/omarchy/default/hypr/envs.conf
source = ~/.local/share/omarchy/default/hypr/looknfeel.conf
source = ~/.local/share/omarchy/default/hypr/input.conf
source = ~/.local/share/omarchy/default/hypr/windows.conf
source = ~/.config/omarchy/current/theme/hyprland.conf
```

### Personal Overrides
```ini
source = ~/.config/hypr/monitors.conf
source = ~/.config/hypr/input.conf
source = ~/.config/hypr/bindings.conf
source = ~/.config/hypr/envs.conf
source = ~/.config/hypr/looknfeel.conf
source = ~/.config/hypr/autostart.conf
```

---

## 🪟 Window Rules

```ini
xwayland {
  force_zero_scaling = false
}

# Opacity
windowrule = opacity 0.90 0.75, class:.*
windowrule = opacity 0.85 0.70, class:^(Alacritty|code)

# No borders for dialogs and menus
windowrulev2 = noborder, xwayland:1, windowtype:^(dialog|splash|utility|popup_menu|dropdown_menu|tooltip)

# Hide video bridge windows
windowrule = opacity 0.0 override, class:^(xwaylandvideobridge)$
windowrule = noanim, class:^(xwaylandvideobridge)$
windowrule = noinitialfocus, class:^(xwaylandvideobridge)$
windowrule = maxsize 1 1, class:^(xwaylandvideobridge)$
windowrule = noblur, class:^(xwaylandvideobridge)$
windowrule = nofocus, class:^(xwaylandvideobridge)$

# Touchpad scroll rules
windowrule = scrolltouchpad 1.5, class:(Alacritty|kitty)
windowrule = scrolltouchpad 0.2, class:com.mitchellh.ghostty
```

---

## ⚙️ General Settings

```ini
general {
  gaps_in = 3
  gaps_out = 5
  border_size = 0
}
```

---

## 💫 Decoration

```ini
decoration {
  rounding = 6
  blur {
    enabled = true
    size = 8
    passes = 1
    ignore_opacity = true
    new_optimizations = true
  }
}
```

---

## ⌨️ Input Configuration

```ini
input {
  kb_layout = br
  kb_options = compose:caps
  repeat_rate = 40
  repeat_delay = 600
  numlock_by_default = true

  touchpad {
    scroll_factor = 0.4
  }
}
```

---

## 🧭 Gestures

```ini
# gesture = 3, horizontal, workspace
```
