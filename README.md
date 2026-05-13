README_JP.md
最新QMK対応 Keyball Firmware セット

最近のQMK環境向けに移植・更新した Keyball firmware セットです。

動作確認環境:

QMK MSYS
avr-gcc 14.x
2025〜2026系 QMK Firmware

対応機種:

Keyball39
Keyball44
Keyball61

維持している機能:

トラックボール機能
PMW3360対応
RGB LED
Split Keyboard 対応
VIA対応
OLED対応
OLED常時点灯版
この repository について

多くの Keyball firmware fork は古いQMK向けに作られており、最近のQMKでは正常に build できなくなっているものがあります。

この repository では、古い Keyball firmware を最近のQMK向けに modernize しています。

最近のQMKで発生する主な変更点:

KC_LANG1/2 → KC_LNG1/2
RESET → QK_BOOT
RGB_DI_PIN → WS2812_DI_PIN
config_common.h 廃止
matrix_scan_quantum() 廃止
古い pointing device API 廃止
avr-gcc 14.x 対応

これらへ対応することで、最近のQMK環境でも build 可能にしています。

主な修正内容
QMK modernize
廃止keycodeの置換
RGB driver 名修正 (WS2812 → ws2812)
AVR platform 定義追加
USB descriptor 修正
deprecated define 削除
RGBLIGHT compatibility define 追加
Trackball / Pointing Device

最近のQMKでは古い register_button() API が削除されています。

そのため、trackball button 処理を最近の pointing device API 向けへ修正しています。

トラックボール機能は維持しています。

OLED

OLED常時点灯版 firmware を追加:

#define OLED_TIMEOUT 0
Firmware
VIA版
keyball_keyball39_via.hex
keyball_keyball44_via.hex
keyball_keyball61_via.hex
OLED常時点灯版
keyball_keyball39_oledtest.hex
keyball_keyball44_oledtest.hex
keyball_keyball61_oledtest.hex
Build例
qmk compile -kb keyball/keyball44 -km via

OLED常時点灯版:

qmk compile -kb keyball/keyball44 -km oledtest
Flash方法

推奨ツール:

QMK Toolbox

各機種へ対応する firmware を書き込んでください。

Keyball39 → Keyball39 firmware
Keyball44 → Keyball44 firmware
Keyball61 → Keyball61 firmware
注意

一部 firmware は AVR 容量上限に近づいています。

必要なら以下で容量削減できます:

LTO_ENABLE = yes
CONSOLE_ENABLE = no
COMMAND_ENABLE = no
Status
Keyball39
最新QMK build: OK
VIA: OK
Trackball: OK
OLED常時点灯: 対応
Keyball44
最新QMK build: OK
VIA: OK
Trackball: OK
OLED常時点灯: 対応
Keyball61
最新QMK build: OK
VIA: OK
Trackball: OK
OLED常時点灯: 対応
Credits

Original Keyball firmware and hardware design belong to the original Keyball project contributors.

This repository contains modernization and compatibility updates for recent QMK environments.
