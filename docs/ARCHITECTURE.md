# Velune architecture

Velune is split into three conceptual layers.

## 1. Chromium layer

Chromium/CEF owns web compatibility and rendering.

Responsibilities:

- page rendering
- JavaScript execution
- networking
- cookies and storage
- permissions plumbing
- downloads plumbing
- DevTools plumbing
- process isolation

Velune should avoid reimplementing browser-engine responsibilities unless there is a strong reason.

## 2. Browser layer

Velune owns browser behavior above Chromium.

Responsibilities:

- tab model
- navigation model
- omnibox behavior
- history
- bookmarks
- downloads UI state
- profiles
- settings
- theme selection
- browser-specific commands

This layer should stay as platform-independent as practical.

## 3. Platform UI layer

### macOS

Swift + SwiftUI + AppKit.

Goals:

- native window behavior
- native keyboard shortcuts and menus
- smooth SwiftUI animations where appropriate
- AppKit where lower-level control is needed
- Liquid Glass-inspired materials for the flagship theme

### Linux

A separate native UI implementation will consume the same browser concepts and Chromium integration.

## theme system

A Velune theme is not just a palette.

It may define:

- toolbar structure
- tab-strip structure
- tab shape
- corner radii
- spacing
- typography choices
- icon treatment
- translucency / material
- sidebar presentation
- control placement
- animation behavior
- compactness

Themes should never modify webpage content.

## early development rule

Get Chromium rendering reliably inside a native Velune window before building large amounts of browser UI. A beautiful shell around a fake browser is not the goal.
