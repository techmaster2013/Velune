# Velune

Velune is a Chromium-based web browser focused on being fast, secure, simple to use, and actually pleasant to look at.

## platforms

- macOS first
- Linux next
- Windows later
- mobile later

## architecture

Velune uses Chromium/CEF for the actual browser engine:

- Blink for rendering
- V8 for JavaScript
- Chromium networking and site isolation
- Chromium DevTools

The browser chrome is ours.

### macOS

The macOS UI is built in Swift using SwiftUI and AppKit, with native materials and a strong Apple-inspired design language.

### Linux

Linux uses the same browser concepts and Chromium core, with its own native UI layer matching Velune's design as closely as practical.

## themes

Velune themes can change more than colors. They can control tab shape, toolbar layout, spacing, materials, icon style, animation, sidebar behavior, and whether controls float or attach to the window.

Planned built-in themes:

1. **Chromium** — familiar classic browser layout
2. **Liquid Glass** — translucent, floating, Apple-inspired chrome
3. **Velune** — the default house style
4. **Compact** — reduced spacing and maximum page area
5. **Retro** — old-school browser chrome
6. **Bare** — almost-fullscreen minimal UI

## first milestone — v0.0.1

- native macOS app window
- Chromium/CEF page rendering
- one working tab
- omnibox
- back / forward / reload
- basic navigation state
- initial theme system
- Chromium, Liquid Glass, and Velune themes

## project layout

```text
Velune/
├── app/                  # platform app shells
│   ├── macos/            # Swift / SwiftUI / AppKit
│   └── linux/            # Linux UI layer
├── browser/              # browser-level logic
│   ├── navigation/
│   ├── tabs/
│   ├── history/
│   ├── bookmarks/
│   ├── downloads/
│   └── settings/
├── chromium/             # CEF / Chromium integration layer
├── themes/               # built-in theme definitions
│   ├── chromium/
│   ├── liquid-glass/
│   ├── velune/
│   ├── compact/
│   ├── retro/
│   └── bare/
├── resources/
└── docs/
```

## status

very early development. things will move around a lot.
