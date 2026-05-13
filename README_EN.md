Modernized Keyball QMK Firmware Set

English README and Japanese README are provided below.

README_EN.md

Modernized Keyball QMK Firmware Set

Modernized firmware set for Keyball series keyboards using recent QMK environments.

Tested with:

QMK MSYS

avr-gcc 14.x

Recent QMK firmware builds (2025–2026 era)

Supported keyboards:

Keyball39

Keyball44

Keyball61

Features retained:

Trackball support

PMW3360 support

RGB lighting

Split keyboard support

VIA support

OLED support

OLED always-on firmware variants

Why this repository exists

Many Keyball firmware forks were originally designed for older QMK versions.

Recent QMK changes introduced breaking API changes such as:

KC_LANG1/2 → KC_LNG1/2

RESET → QK_BOOT

RGB_DI_PIN → WS2812_DI_PIN

config_common.h removal

matrix_scan_quantum() removal

old pointing device API removal

stricter avr-gcc compilation

This repository modernizes the original firmware so it can compile on modern QMK environments.
