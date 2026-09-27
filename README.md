# Awesome Dart & Flutter for Windows [![Awesome](https://raw.githubusercontent.com/sindresorhus/awesome/main/media/badge.svg)](https://awesome.re)

> A curated catalog of **Windows-focused** Dart & Flutter resources — packages, tooling, templates, docs, scripts, and community for building native Windows desktop apps.

Windows desktop is a first-class Flutter target: real Win32 windows, MSIX installers, Fluent UI, WebView2, system tray, registry access, and full `dart:ffi` access to the OS. This list collects the good stuff for that specific niche — down to the raw Win32 bindings, FFI codegen, native build toolchains, and system-level scripting.

**Contents**

**Getting started**

- [Official Documentation](#official-documentation)
- [Announcements & Deep Dives](#announcements--deep-dives)
- [Window Management & Chrome](#window-management--chrome)
- [File Dialogs, Shell & Taskbar](#file-dialogs-shell--taskbar)
- [System Tray & Notifications](#system-tray--notifications)
- [Autostart, Hotkeys & Auto-Update](#autostart-hotkeys--auto-update)
- [Packaging, Installers & Deployment](#packaging-installers--deployment)
- [System, Hardware & Device Info](#system-hardware--device-info)
- [Windows UI (Fluent)](#windows-ui-fluent)
- [WebView2](#webview2)
- [Templates, Samples & Showcase Apps](#templates-samples--showcase-apps)
- [Community](#community)

**Low level: the raw OS surface**

- [Win32, COM & WinRT Interop](#win32-com--winrt-interop)
- [FFI: Calling Native Code](#ffi-calling-native-code)
- [FFI Codegen & Binding Generators](#ffi-codegen--binding-generators)
- [Native Assets & Build Hooks](#native-assets--build-hooks)
- [Embedding Dart in Native Apps](#embedding-dart-in-native-apps)
- [Process, Memory & Modules](#process-memory--modules)
- [Raw Input: Hooks & Low-Level Devices](#raw-input-hooks--low-level-devices)
- [Graphics: DirectX, OpenGL, Vulkan & Capture](#graphics-directx-opengl-vulkan--capture)
- [Audio & Media Low Level](#audio--media-low-level)
- [IPC, Pipes & Shell Integration](#ipc-pipes--shell-integration)
- [System APIs: WMI, Registry, Services & Tasks](#system-apis-wmi-registry-services--tasks)
- [Clipboard, Storage & Cryptography](#clipboard-storage--cryptography)
- [Networking & HTTP](#networking--http)
- [Scripting from Dart](#scripting-from-dart)
- [Win32 API Reference (Microsoft)](#win32-api-reference-microsoft)

**Toolchain**

- [Native Build Toolchain (CMake, MSVC, MinGW)](#native-build-toolchain-cmake-msvc-mingw)
- [Dart CLI & Standalone Executables](#dart-cli--standalone-executables)
- [Testing & Debugging on Windows](#testing--debugging-on-windows)
- [Tooling & Build](#tooling--build)

**Ecosystem**

- [Related Windows Platform Resources](#related-windows-platform-resources)
- [Contributing](#contributing)

> ⚠️ **A note on `win32*` packages.** Several packages below are community-maintained and young (v0.x). Always check the version, likes, and Windows platform badge on pub.dev before depending on them in production.

---

## Official Documentation

**Flutter — Windows desktop**

- [Windows platform integration](https://docs.flutter.dev/platform-integration/windows) — The hub for everything Windows.
- [Set up Windows development](https://docs.flutter.dev/platform-integration/windows/setup) — Visual Studio, the **"Desktop development with C++"** workload, and `flutter doctor -v`.
- [Building Windows apps](https://docs.flutter.dev/platform-integration/windows/building) — `flutter build windows`, the runner, CMake, and packaging options.
- [External (non-Flutter) Win32 windows](https://docs.flutter.dev/platform-integration/windows/extern_win) — Hosting Flutter inside an existing Win32 window and handling lifecycle.
- [Desktop support overview](https://docs.flutter.dev/platform-integration/desktop) — `flutter create --platforms=windows`.
- [Deployment to the Microsoft Store](https://docs.flutter.dev/deployment/windows) — Partner Center, versioning, and the Windows App Certification Kit.
- [App flavors for Windows](https://docs.flutter.dev/deployment/flavors-windows) — Per-environment configurations.
- [Supported platforms](https://docs.flutter.dev/reference/supported-platforms) — Where Windows sits in the support matrix.
- [Install Flutter on Windows](https://docs.flutter.dev/get-started/install/windows) — Getting the SDK running.

**Dart — native & OS interop**

- [C interop with `dart:ffi`](https://dart.dev/interop/c-interop) — The main guide to calling native code.
- [`dart:ffi` API reference](https://api.dart.dev/dart-ffi/dart-ffi-library.html) — Types, `DynamicLibrary`, `NativeFunction`.
- [Build hooks](https://dart.dev/tools/hooks) — Bundle native C/C++ code with your Dart package.
- [`package:ffi`](https://pub.dev/packages/ffi) — Helpers for native memory, strings, and allocations.
- [`ffigen`](https://pub.dev/packages/ffigen) — Generate FFI bindings straight from C headers.
- [Core libraries](https://dart.dev/libraries) — `dart:io`, `dart:convert`, and friends.

---

## Announcements & Deep Dives

- [Announcing Flutter for Windows](https://flutter.dev/blog/announcing-flutter-for-windows) — Stable Windows desktop support lands in Flutter 2.10 (Feb 2022).
- [Flutter 2.10: What's New](https://flutter.dev/blog/whats-new-in-flutter-2-10) — The release post for Windows stable.
- [Flutter and Desktop](https://flutter.dev/blog/flutter-and-desktop) — The original tech preview and `flutter build windows`.
- [Announcing Flutter for Windows — Alpha](https://flutter.dev/blog/announcing-flutter-windows-alpha) — Where it all started (Sep 2020).
- [What's New in Flutter 3](https://flutter.dev/blog/whats-new-in-flutter-3) — Desktop stability across all three desktop OSes.
- [Dart \| Windows](https://win32.pub) — The Dart + Windows suite site: docs, blog, and live examples.
- [Calling Windows APIs in Dart with win32](https://win32.pub/blog/calling-windows-apis) — Practical FFI walkthrough.
- [Windows fun with Dart FFI](https://timsneath.medium.com/windows-fun-with-dart-ffi-687c4619e78d) — Tim Sneath's hands-on FFI post.
- [Introducing Dart \| Windows](https://timsneath.medium.com/introducing-dart-windows-4c0b55b063b0) — The story behind the `win32` package.

---

## Window Management & Chrome

| Package | Description |
| --- | --- |
| [bitsdojo_window](https://pub.dev/packages/bitsdojo_window) | Custom border/title bar and window ops — the classic way to make a frameless window. |
| [window_manager](https://pub.dev/packages/window_manager) | Resize, reposition, minimize/maximize, and query the desktop window. |
| [window_manager_plus](https://pub.dev/packages/window_manager_plus) | Multi-window: create, resize, and communicate between windows. |
| [desktop_multi_window](https://pub.dev/packages/desktop_multi_window) | Create and manage additional top-level windows (MixinNetwork). |
| [desktop_window](https://pub.dev/packages/desktop_window) | Get/set window size, min/max size, fullscreen, and borders. |
| [window_size](https://pub.dev/packages/window_size) | Minimal resize and reposition for the Flutter window. |
| [window_to_front](https://pub.dev/packages/window_to_front) | Bring the app back to the front of the Z-order (useful from tray/hotkey). |
| [flutter_acrylic](https://pub.dev/packages/flutter_acrylic) | Acrylic, Mica, blur, and transparency effects on the window. |
| [screen_retriever](https://pub.dev/packages/screen_retriever) | Display metrics, bounds, and cursor position across monitors. |
| [windows_single_instance](https://pub.dev/packages/windows_single_instance) | Force a single instance and focus the existing window on relaunch. |
| [desktop_drop](https://pub.dev/packages/desktop_drop) | Drag-and-drop files from Explorer onto the app. |

---

## File Dialogs, Shell & Taskbar

| Package | Description |
| --- | --- |
| [file_selector](https://pub.dev/packages/file_selector) | Official native open/save/directory pickers (Windows implementation included). |
| [filepicker_windows](https://pub.dev/packages/filepicker_windows) | Native common-dialog file and directory picker. |
| [path_provider_windows](https://pub.dev/packages/path_provider_windows) | Windows implementation of `path_provider`. |
| [windows_taskbar](https://pub.dev/packages/windows_taskbar) | Taskbar progress, overlay icons, and window state. |
| [resolve_windows_shortcut](https://pub.dev/packages/resolve_windows_shortcut) | Resolve the target path of `.lnk` shortcut files. |
| [flutter_platform_alert](https://pub.dev/packages/flutter_platform_alert) | Native `MessageBox` / `TaskDialogIndirect` with alert sounds. |
| [windows_printer](https://pub.dev/packages/windows_printer) | Printer management, including thermal/receipt printers. |

---

## System Tray & Notifications

| Package | Description |
| --- | --- |
| [system_tray](https://pub.dev/packages/system_tray) | Custom tray icon and menu for desktop apps. |
| [tray_manager](https://pub.dev/packages/tray_manager) | Define a system tray icon (LeanFlutter). |
| [desktop_tray](https://pub.dev/packages/desktop_tray) | Tray icons and menus across desktop platforms. |
| [local_notifier](https://pub.dev/packages/local_notifier) | Show local notifications on desktop. |
| [win_toast](https://pub.dev/packages/win_toast) | Windows toast notifications (Notification Center). |
| [windows_notification](https://pub.dev/packages/windows_notification) | Templated Windows notification content. |
| [flutter_local_notifications](https://pub.dev/packages/flutter_local_notifications) | The standard local notifications plugin, with Windows support. |

---

## Autostart, Hotkeys & Auto-Update

| Package | Description |
| --- | --- |
| [launch_at_startup](https://pub.dev/packages/launch_at_startup) | Launch the app automatically at login. |
| [open_at_login](https://pub.dev/packages/open_at_login) | Enable/disable start-at-login for the current user. |
| [hotkey_manager](https://pub.dev/packages/hotkey_manager) | System-wide global hotkeys. |
| [flutter_hotkeys](https://pub.dev/packages/flutter_hotkeys) | Global and scoped keyboard shortcut manager. |
| [auto_updater](https://pub.dev/packages/auto_updater) | Self-update support (WinSparkle-based, Windows + macOS). |
| [restart_app](https://pub.dev/packages/restart_app) | Restart/relaunch the running app. |

---

## Packaging, Installers & Deployment

| Package / Tool | Description |
| --- | --- |
| [msix](https://pub.dev/packages/msix) | Turn a Flutter Windows build into an MSIX package for the Microsoft Store — configure via `msix_config:` in `pubspec.yaml`. |
| [innosetup](https://pub.dev/packages/innosetup) | Build a Windows installer with Inno Setup. |
| [inno_build](https://pub.dev/packages/inno_build) | CLI for producing an `.exe` installer via Inno Setup. |
| [inno_bundle](https://pub.dev/packages/inno_bundle) | Automated Inno Setup installer builds. |
| [fastforge](https://pub.dev/packages/fastforge) | Packaging and publishing tooling for desktop apps. |

**External tooling**

- [MSIX overview (Microsoft)](https://learn.microsoft.com/en-us/windows/msix/overview) — What the MSIX format actually is.
- [Inno Setup](https://jrsoftware.org/isinfo.php) — The classic Windows installer compiler.
- [WiX Toolset](https://wixtoolset.org/) — MSI-based installers for more complex cases.
- [Visual Studio](https://visualstudio.microsoft.com/vs/) — Required for the C++ desktop workload.
- [VC++ deployment examples](https://learn.microsoft.com/en-us/cpp/windows/deployment-examples?view=msvc-170) — Shipping the VC++ redistributable DLLs (`msvcp140.dll`, `vcruntime140.dll`, `vcruntime140_1.dll`).
- [CodeMagic CI/CD](https://codemagic.io/docs/) — Flutter CI with Windows build and MSIX packaging.

---

## System, Hardware & Device Info

| Package | Description |
| --- | --- |
| [system_info2](https://pub.dev/packages/system_info2) | Architecture, kernel, memory, OS, CPU, and user info. |
| [device_info_plus](https://pub.dev/packages/device_info_plus) | Device and OS information, including Windows. |
| [windows_hello](https://pub.dev/packages/windows_hello) | Windows Hello biometrics/PIN and Credential Manager. |
| [biometric_storage](https://pub.dev/packages/biometric_storage) | Encrypted storage, optionally biometric-locked. |
| [volume_controller](https://pub.dev/packages/volume_controller) | Control system volume. |
| [screen_brightness](https://pub.dev/packages/screen_brightness) | Control screen brightness. |
| [screen_capturer](https://pub.dev/packages/screen_capturer) | Screenshot capture on desktop. |
| [printing](https://pub.dev/packages/printing) | Generate and print documents, including on Windows. |

---

## Windows UI (Fluent)

| Package | Description |
| --- | --- |
| [fluent_ui](https://pub.dev/packages/fluent_ui) | Microsoft's Fluent Design system for Flutter — the go-to for a native Windows look. Flutter Favorite. |
| [fluentui_system_icons](https://pub.dev/packages/fluentui_system_icons) | Microsoft's Fluent icon set (published by Microsoft). |
| [desktop](https://pub.dev/packages/desktop) | Design-standard widgets tuned for desktop layouts. |

---

## WebView2

| Package | Description |
| --- | --- |
| [webview_windows](https://pub.dev/packages/webview_windows) | WebView2-backed webview widget for Windows. |
| [webview_flutter_windows](https://pub.dev/packages/webview_flutter_windows) | The Windows implementation of `webview_flutter` (WebView2). |
| [desktop_webview_window](https://pub.dev/packages/desktop_webview_window) | Open a webview as its own separate desktop window. |
| [flutter_inappwebview](https://pub.dev/packages/flutter_inappwebview) | Inline and headless webviews with an in-app browser. |

---

## Templates, Samples & Showcase Apps

**Templates & official samples**

- [`windows.tmpl`](https://github.com/flutter/flutter/tree/master/packages/flutter_tools/templates/app/windows.tmpl) — The Windows runner template used by `flutter create`.
- [`plugin/windows.tmpl`](https://github.com/flutter/flutter/tree/master/packages/flutter_tools/templates/plugin/windows.tmpl) — Windows plugin template.
- [Flutter samples](https://github.com/flutter/samples) — Official sample catalog.
- [desktop_photo_search](https://github.com/flutter/samples/tree/main/desktop_photo_search) — Desktop sample referenced by the official Windows docs.
- [`dart:ffi` samples](https://github.com/dart-lang/samples/tree/main/ffi) — Official FFI examples.
- [Flutter Gallery](https://github.com/flutter/gallery) — Includes desktop form factors.
- [flutter/packages](https://github.com/flutter/packages) — Where the official platform-implementation packages live.

**Showcase apps worth reading the source of**

- [Harmonoid](https://github.com/harmonoid/harmonoid) — Windows-focused music player.
- [Invoice Ninja Flutter client](https://github.com/invoiceninja/flutter-client) — Production-grade Flutter desktop app.
- [Flokk](https://github.com/gskinnerTeam/Flokk) — Google Contacts desktop client from the Windows alpha announcement.
- [win32 examples](https://github.com/halildurmus/win32) — Extensive Win32 usage examples.
- [flutter-desktop-embedding](https://github.com/google/flutter-desktop-embedding) — Historical early desktop embedding project *(archived)*.

**Browse:** [GitHub topic `flutter-windows`](https://github.com/topics/flutter-windows)

---

## Community

- [Flutter Discord](https://discord.com/invite/N7Yshp4) — The `#desktop` and Windows channels are where desktop questions get answered.
- [r/FlutterDev](https://www.reddit.com/r/FlutterDev/) — Active subreddit for desktop discussion.
- [Stack Overflow — `flutter-desktop`](https://stackoverflow.com/questions/tagged/flutter-desktop) — 300+ targeted questions.
- [Stack Overflow — `flutter`](https://stackoverflow.com/questions/tagged/flutter) — The main tag.
- [Flutter GitHub issues — `platform-windows`](https://github.com/flutter/flutter/issues?q=is%3Aissue%20label%3Aplatform-windows) — 2,000+ open/closed Windows-specific issues.
- [Flutter Forum](https://forum.itsallwidgets.com/) — The official forum.
- [Flutter Community hub](https://flutter.dev/community) — Canonical index of all official channels.
- [Meetup — Flutter](https://www.meetup.com/pro/flutter/) — Local groups, many desktop-active.

> Note: `flutter/flutter` has no GitHub Discussions — Issues and Discord are the channels.

---

## Win32, COM & WinRT Interop

The heart of "Windows-only" Dart — direct, type-safe access to the OS.

| Package | Description |
| --- | --- |
| [win32](https://pub.dev/packages/win32) | Call common Win32 APIs and COM objects directly from Dart via FFI. The flagship package. |
| [win32_gui](https://pub.dev/packages/win32_gui) | Object-oriented Win32 GUI helpers built on `win32` + `dart:ffi`. |
| [win32_registry](https://pub.dev/packages/win32_registry) | Type-safe Windows Registry read/write. |
| [win32_gamepad](https://pub.dev/packages/win32_gamepad) | Type-safe XInput gamepad access. |
| [win32_runner](https://pub.dev/packages/win32_runner) | Run a Flutter Windows app from a pure-Dart Win32 entry point — no C++ compiler needed. |
| [win32audio](https://pub.dev/packages/win32audio) | Enumerate audio devices, set the default device, and control master/per-app volume. |
| [win32_clipboard](https://pub.dev/packages/win32_clipboard) | Modern, type-safe Windows Clipboard API with custom format support. |
| [win32_suspend_process](https://pub.dev/packages/win32_suspend_process) | Suspend and resume processes from native Dart code. |
| [winrt](https://pub.dev/packages/winrt) | Windows Runtime (WinRT) APIs from a single package — experimental. |
| [com](https://pub.dev/packages/com) | Idiomatic Dart projection of the COM APIs (prototype). |
| [windart](https://pub.dev/packages/windart) | Lightweight Win32 bindings for Dart via FFI. |
| [winmd](https://pub.dev/packages/winmd) | Inspect and generate Windows Metadata (`.winmd`) files per the ECMA-335 standard. |
| [dart_console](https://pub.dev/packages/dart_console) | Console color, cursor, and input control for Dart CLI tools. |
| [file_saver](https://pub.dev/packages/file_saver) | Native save-file dialogs and file writing. |
| [serial_port_win32](https://pub.dev/packages/serial_port_win32) | Serial port I/O over the Win32 API. |

**Explore more:** [pub.dev packages compatible with Windows](https://pub.dev/packages?q=platform%3Awindows) · [search `win32`](https://pub.dev/packages?q=win32) · [search `ffi`](https://pub.dev/packages?q=ffi)

---

## FFI: Calling Native Code

`dart:ffi` is how you get below Flutter and talk to Windows directly.

**Official docs**

- [C interop with `dart:ffi`](https://dart.dev/interop/c-interop) — The main guide.
- [`dart:ffi` API reference](https://api.dart.dev/dart-ffi/dart-ffi-library.html) — `DynamicLibrary`, `NativeFunction`, `Pointer`, `Struct`.
- [Bind native code in Flutter](https://docs.flutter.dev/platform-integration/bind-native-code) — Flutter-specific FFI guidance.
- [Build hooks](https://dart.dev/tools/hooks) — Compile and bundle native code as part of your package build.

| Package | Description |
| --- | --- |
| [ffi](https://pub.dev/packages/ffi) | Core helpers: `Utf8`, `calloc`, `malloc`, `structOf`, size calculations. |
| [ffigen](https://pub.dev/packages/ffigen) | Generate Dart FFI bindings directly from C headers. |
| [jnigen](https://pub.dev/packages/jnigen) | Generate bindings from JNI/native headers for Java and Dart interop. |
| [sqlite3](https://pub.dev/packages/sqlite3) | FFI bindings to SQLite — the canonical "bundle a C library" example. |
| [opengl](https://pub.dev/packages/opengl) | OpenGL 4.6 FFI bindings for Dart (Linux, macOS, Windows). |
| [vulkan](https://pub.dev/packages/vulkan) | Vulkan 1.3 FFI bindings for Dart (Linux, Windows). |
| [sdl2](https://pub.dev/packages/sdl2) | SDL 2 bindings for Dart via FFI — windowing, input, audio, GPU. |
| [quickjs](https://pub.dev/packages/quickjs) | Embed the QuickJS JavaScript engine in Dart via native assets. |
| [dart_odbc](https://pub.dev/packages/dart_odbc) | ODBC database driver via FFI. |
| [stdc](https://pub.dev/packages/stdlibc) *(pkg `stdlibc`)* | Libc-style bindings for Dart via FFI. |

---

## FFI Codegen & Binding Generators

Write the bindings by hand, or generate them.

| Tool | Description |
| --- | --- |
| [ffigen](https://pub.dev/packages/ffigen) | The standard generator: parse C headers → Dart FFI bindings. |
| [dllimport_gen](https://pub.dev/packages/dllimport_gen) | Generate Dart code from the Windows API docs, emulating C#'s `[DllImport]` notation. |
| [winmd](https://pub.dev/packages/winmd) | Read/generate Windows Metadata (`.winmd`) — the source for WinRT projections. |
| [win32](https://pub.dev/packages/win32) | Ships pre-generated bindings, so you rarely need to run a generator yourself. |
| [jnigen](https://pub.dev/packages/jnigen) | Bindings generator for JNI and native interop. |
| [dart-lang/native](https://github.com/dart-lang/native) | Dart team's repo for native interop experiments and design. |

---

## Native Assets & Build Hooks

The modern way to compile C/C++/Rust into a Dart package — no CMake wrangling required.

- [Build hooks (official)](https://dart.dev/tools/hooks) — Declare and build native assets from `hook/build.dart`.

| Package | Description |
| --- | --- |
| [hooks](https://pub.dev/packages/hooks) | The hook API for building native assets. |
| [hooks_runner](https://pub.dev/packages/hooks_runner) | Runs the build hooks for a package. |
| [native_toolchain_c](https://pub.dev/packages/native_toolchain_c) | Drive a C compiler from a build hook. |
| [native_toolchain_cmake](https://pub.dev/packages/native_toolchain_cmake) | Drive CMake from a build hook. |
| [native_toolchain_rust](https://pub.dev/packages/native_toolchain_rust) | Build Rust crates as native assets. |
| [native_toolchain_ninja](https://pub.dev/packages/native_toolchain_ninja) | Ninja-based builds from a hook. |
| [native_assets_builder](https://pub.dev/packages/native_assets_builder) | Helpers for composing native asset builds. |
| [code_assets](https://pub.dev/packages/code_assets) | Code-generation assets (prebuilt binaries) for packages. |

---

## Embedding Dart in Native Apps

The reverse direction — call Dart from C, C++, or a native host.

- [dart-lang/native](https://github.com/dart-lang/native) — Tooling and design docs for native interop in both directions.
- [dart:ffi API reference](https://api.dart.dev/dart-ffi/dart-ffi-library.html) — Includes the `Dart_` C API and the DL API surface.
- [C interop guide](https://dart.dev/interop/c-interop) — Structs, callbacks, and calling conventions.
- [`dart_api_dl.h`](https://github.com/dart-lang/sdk/blob/main/runtime/include/dart_api_dl.h) — The dynamic-loading C API header: `Dart_Initialize`, `Dart_LoadLibrary`, and friends.
- [Flutter Windows — external Win32 windows](https://docs.flutter.dev/platform-integration/windows/extern_win) — Hosting Flutter inside an existing native window.

---

## Process, Memory & Modules

| Package / Resource | Description |
| --- | --- |
| [win32_suspend_process](https://pub.dev/packages/win32_suspend_process) | Suspend/resume processes natively. |
| [win32](https://pub.dev/packages/win32) | Process/thread creation, memory allocation, module loading, `GetLastError`. |
| [System error codes](https://learn.microsoft.com/en-us/windows/win32/debug/system-error-codes) | The documented `HRESULT`/`GetLastError` table. |
| [`GetLastError`](https://learn.microsoft.com/en-us/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) | Read the last Win32 error code. |
| [Process Monitor (Procmon)](https://learn.microsoft.com/en-us/sysinternals/downloads/procmon) | Sysinternals — watch every file/registry/process op an app performs. |
| [Process Explorer](https://learn.microsoft.com/en-us/sysinternals/downloads/process-explorer) | Inspect loaded modules, threads, and handles. |

---

## Raw Input: Hooks & Low-Level Devices

Global hooks (`SetWindowsHookEx`), raw input, HID, and gamepads.

| Package | Description |
| --- | --- |
| [win32hooks](https://pub.dev/packages/win32hooks) | Track mouse buttons and window events on Windows. |
| [uiohook_dart](https://pub.dev/packages/uiohook_dart) | Cross-platform desktop keyboard & mouse hooking (libuiohook). |
| [uiohook_flutter](https://pub.dev/packages/uiohook_flutter) | Flutter bindings for global input hooks. |
| [winhooker](https://pub.dev/packages/winhooker) | Low-level keyboard and mouse event stream. |
| [winhooker_mouse](https://pub.dev/packages/winhooker_mouse) | Raw mouse events scoped to a window. |
| [win32_gamepad](https://pub.dev/packages/win32_gamepad) | XInput gamepad access. |
| [hid4flutter](https://pub.dev/packages/hid4flutter) | Raw HID device access from Flutter. |
| [bluetooth_rfcomm](https://pub.dev/packages/bluetooth_rfcomm) | Bluetooth RFCOMM serial-style transport. |
| [Subclassing controls](https://learn.microsoft.com/en-us/windows/win32/controls/subclassing-overview) | Intercept another window's input at the Win32 level. |
| [Messages and message queues](https://learn.microsoft.com/en-us/windows/win32/winmsg/about-messages-and-message-queues) | The core of Win32 input handling. |
| [AutoHotkey v2 — Hotkeys](https://www.autohotkey.com/docs/v2/Hotkeys.htm) | Great reference for global-hotkey behavior and edge cases. |

---

## Graphics: DirectX, OpenGL, Vulkan & Capture

| Package | Description |
| --- | --- |
| [opengl](https://pub.dev/packages/opengl) | OpenGL 4.6 FFI bindings. |
| [vulkan](https://pub.dev/packages/vulkan) | Vulkan 1.3 FFI bindings. |
| [dxgi_dart](https://pub.dev/packages/dxgi_dart) | Very high-performance screen capture on Windows via low-level FFI (DXGI). |
| [sdl2](https://pub.dev/packages/sdl2) | SDL 2 bindings — windowing, rendering, input, audio in one FFI surface. |
| [windows_gpu_recovery](https://pub.dev/packages/windows_gpu_recovery) | Recover from `EGL_CONTEXT_LOST` / `DXGI_ERROR_DEVICE_REMOVED` after sleep or driver reset. |
| [DWM functions](https://learn.microsoft.com/en-us/windows/win32/dwm/functions) | Desktop Window Manager — composition, opacity, and blur. |
| [`dwmapi.dll` API index](https://learn.microsoft.com/en-us/windows/win32/api/dwmapi/) | The DWM entry points. |

---

## Audio & Media Low Level

| Package | Description |
| --- | --- |
| [win32audio](https://pub.dev/packages/win32audio) | Audio device enumeration, default device, and volume control. |
| [audio_flutter_windows](https://pub.dev/packages/audio_flutter_windows) | Windows audio backend for Flutter audio. |
| [flutter_miniaudio](https://pub.dev/packages/flutter_miniaudio) | miniaudio backend for playback and capture. |
| [miniav](https://pub.dev/packages/miniav) | Cross-platform audio/video capture and playback. |
| [miniav_recorder](https://pub.dev/packages/miniav_recorder) | Record audio and video from Dart. |
| [system_audio_visualizer](https://pub.dev/packages/system_audio_visualizer) | Visualize system audio output. |
| [sdl2](https://pub.dev/packages/sdl2) | SDL audio subsystem if you want one FFI dep for input+audio. |

---

## IPC, Pipes & Shell Integration

| Package / Resource | Description |
| --- | --- |
| [portable_pty](https://pub.dev/packages/portable_pty) | Cross-platform pseudo-terminal (PTY) for Dart — spawn shells on Windows via ConPTY. |
| [pty2](https://pub.dev/packages/pty2) | Pseudo-terminal file descriptors for Dart and Flutter. |
| [flutter_pty2](https://pub.dev/packages/flutter_pty2) | Maintained FFI PTY plugin for Flutter. |
| [win32](https://pub.dev/packages/win32) | Named pipes, shared memory, mailslots, and `CreateProcess`. |
| [ConPTY — creating a pseudoconsole](https://learn.microsoft.com/en-us/windows/console/creating-a-pseudoconsole-session) | How Windows fakes a terminal for a child process. |
| [`CreatePseudoConsole`](https://learn.microsoft.com/en-us/windows/console/createpseudoconsole) | The ConPTY entry point. |
| [Windows Terminal](https://learn.microsoft.com/en-us/windows/terminal/) | The modern host console. |
| [`ShellExecuteExW`](https://learn.microsoft.com/en-us/windows/win32/api/shellapi/nf-shellapi-shellexecuteexw) | Launch files/URLs with the shell (elevation, "run as"). |

---

## System APIs: WMI, Registry, Services & Tasks

| Package / Resource | Description |
| --- | --- |
| [wmi](https://pub.dev/packages/wmi) | Query Windows Management Instrumentation. |
| [win32_registry](https://pub.dev/packages/win32_registry) | Type-safe Registry read/write. |
| [registry](https://pub.dev/packages/registry) | Tiny service-locator for Dart/Flutter with no codegen. |
| [event_tracing_windows](https://pub.dev/packages/event_tracing_windows) | Monitor process and filesystem activity in real time via ETW. |
| [Task Scheduler reference](https://learn.microsoft.com/en-us/windows/win32/taskschd/task-scheduler-reference) | The COM API for scheduled tasks. |
| [`schtasks` command](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/schtasks) | The CLI for scheduling tasks. |
| [Services API (`winsvc.h`)](https://learn.microsoft.com/en-us/windows/win32/api/winsvc/) | Install and control Windows services. |
| [System information](https://learn.microsoft.com/en-us/windows/win32/sysinfo/system-information) | `GetSystemInfo`, memory, and CPU details. |
| [Event Tracing for Windows (ETW)](https://learn.microsoft.com/en-us/windows/win32/etw/event-tracing-portal) | The OS-wide tracing subsystem. |

---

## Clipboard, Storage & Cryptography

| Package | Description |
| --- | --- |
| [win32_clipboard](https://pub.dev/packages/win32_clipboard) | Type-safe clipboard access, including custom formats. |
| [windows_hello](https://pub.dev/packages/windows_hello) | Windows Hello biometrics/PIN and Credential Manager. |
| [biometric_storage](https://pub.dev/packages/biometric_storage) | Encrypted storage, optionally biometric-locked. |
| [win32](https://pub.dev/packages/win32) | DPAPI, CryptoAPI, and certificate-store functions via FFI. |

---

## Networking & HTTP

| Package | Description |
| --- | --- |
| [win_http](https://pub.dev/packages/win_http) | `package:http` client over the native WinHTTP API — system proxy, Schannel TLS, auto decompression. |
| [win32](https://pub.dev/packages/win32) | Winsock, `WinHttp`, and HTTP.sys functions. |
| [TCPView](https://learn.microsoft.com/en-us/sysinternals/downloads/tcpview) | See every socket your app opens. |

---

## Scripting from Dart

Drive the shell, PowerShell, and the Windows command set from Dart.

**Dart-side**

- [`Process.run`](https://api.dart.dev/dart-io/Process/run.html) — Run a program and capture stdout/stderr.
- [`Process` class](https://api.dart.dev/dart-io/Process-class.html) — Start, kill, and read `exitCode`.
- [`dart:io` reference](https://api.dart.dev/dart-io/) — Filesystem, sockets, and processes.
- [fiber_shell](https://pub.dev/packages/fiber_shell) — Typed shell-command builder for desktop; pipes and chaining in Dart instead of shell strings.
- [shell_executor](https://pub.dev/packages/shell_executor) — Run shell commands with output capture.

**Shell-side**

- [PowerShell docs](https://learn.microsoft.com/en-us/powershell/) · [install `pwsh`](https://learn.microsoft.com/en-us/powershell/scripting/install/install-powershell-on-windows?view=powershell-7.6) · [about_pwsh](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7.6)
- [cmd command reference](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/cmd) · [all Windows commands A–Z](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)
- [Console code pages](https://learn.microsoft.com/en-us/windows/console/console-code-pages) — The classic Windows encoding gotcha.
- [Console application issues](https://learn.microsoft.com/en-us/windows/console/console-application-issues) — CRLF, encoding, and why your output looks wrong.
- [Code-page identifiers](https://learn.microsoft.com/en-us/windows/win32/intl/code-page-identifiers) — CP936/GBK and friends.
- [`exit` / errorlevel](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/exit) · [`chcp`](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/chcp) · [`robocopy`](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/robocopy) · [`reg`](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/reg)

---

## Win32 API Reference (Microsoft)

Go read the source of truth when a package doesn't cover what you need.

- [Win32 and COM — build desktop apps](https://learn.microsoft.com/en-us/windows/win32/) — The entry point.
- [`WinMain` — the application entry point](https://learn.microsoft.com/en-us/windows/win32/learnwin32/winmain--the-application-entry-point) — How a Windows app actually starts.
- [Window procedures](https://learn.microsoft.com/en-us/windows/win32/winmsg/about-window-procedures) — `WndProc`, the callback at the heart of every window.
- [Messages and message queues](https://learn.microsoft.com/en-us/windows/win32/winmsg/about-messages-and-message-queues) — How input reaches your app.
- [Working with strings (`WinMain`)](https://learn.microsoft.com/en-us/windows/win32/learnwin32/working-with-strings) — The `wWinMain` / Unicode story.
- [Code Pages (Win32)](https://learn.microsoft.com/en-us/windows/win32/intl/code-pages) — Encoding reference.
- [DWM reference](https://learn.microsoft.com/en-us/windows/win32/dwm/reference) — Desktop Window Manager.
- [Services API](https://learn.microsoft.com/en-us/windows/win32/api/winsvc/) · [service functions](https://learn.microsoft.com/en-us/windows/win32/services/service-functions)
- [System information](https://learn.microsoft.com/en-us/windows/win32/sysinfo/system-information)
- [Task Scheduler reference](https://learn.microsoft.com/en-us/windows/win32/taskschd/task-scheduler-reference)
- [ConPTY](https://learn.microsoft.com/en-us/windows/console/creating-a-pseudoconsole-session) · [pseudoconsoles overview](https://learn.microsoft.com/en-us/windows/console/pseudoconsoles)

---

## Native Build Toolchain (CMake, MSVC, MinGW)

To produce the DLLs and EXEs that FFI calls into.

- [Flutter Windows — building](https://docs.flutter.dev/platform-integration/windows/building) — How the Windows runner uses CMake.
- [Flutter Windows — setup](https://docs.flutter.dev/platform-integration/windows/setup) — Install the C++ workload.

**MSVC / Visual Studio**

- [MSVC compiler options](https://learn.microsoft.com/en-us/cpp/build/reference/compiler-options?view=msvc-170) — `/LD`, `/MT`, optimization flags.
- [MSVC linker options](https://learn.microsoft.com/en-us/cpp/build/reference/linker-options?view=msvc-170) — Export a DLL from a `.def` or `__declspec(dllexport)`.
- [`cl` command-line syntax](https://learn.microsoft.com/en-us/cpp/build/reference/compiler-command-line-syntax?view=msvc-170)
- [Build from the command line](https://learn.microsoft.com/en-us/cpp/build/building-on-the-command-line?view=msvc-170) — `vcvarsall.bat` and the Developer Prompt.
- [AddressSanitizer for MSVC](https://learn.microsoft.com/en-us/cpp/sanitizers/asan?view=msvc-170) — `/fsanitize=address` to catch memory bugs in your native code.
- [`/fsanitize` flag](https://learn.microsoft.com/en-us/cpp/build/reference/fsanitize?view=msvc-170)

**CMake & alternatives**

- [CMake `find_package`](https://cmake.org/cmake/help/latest/command/find_package.html) · [CMake packages](https://cmake.org/cmake/help/latest/manual/cmake-packages.7.html) · [`cmake(1)`](https://cmake.org/cmake/help/latest/manual/cmake.1.html)
- [Ninja](https://ninja-build.org/) · [Ninja manual](https://ninja-build.org/manual.html) — The fast build tool Flutter's Windows runner uses.
- [MSYS2](https://www.msys2.org/) · [MSYS2 environments](https://www.msys2.org/docs/environments/) — UCRT64, CLANG64, etc.
- [MinGW-w64](https://www.mingw-w64.org/) — GCC-based toolchain for Windows.
- [Clang](https://clang.llvm.org/) · [Clang getting started](https://clang.llvm.org/get_started.html)

**Windows SDK & resources**

- [Windows SDK downloads](https://learn.microsoft.com/en-us/windows/apps/windows-sdk/downloads) — Headers, libs, and `rc.exe`.
- [Resource compiler (`rc.exe`)](https://learn.microsoft.com/en-us/windows/win32/menurc/resource-compiler) — Embed icons, version info, and manifests into your DLL/EXE.
- [About resource files](https://learn.microsoft.com/en-us/windows/win32/menurc/about-resource-files) · [`rc` command line](https://learn.microsoft.com/en-us/windows/win32/menurc/using-rc-the-rc-command-line-)
- [VC++ deployment examples](https://learn.microsoft.com/en-us/cpp/windows/deployment-examples?view=msvc-170) — Ship `msvcp140.dll`, `vcruntime140.dll`, `vcruntime140_1.dll`.

---

## Dart CLI & Standalone Executables

Turn Dart scripts into real Windows binaries — great for the tools that support your app.

- [`dart compile`](https://dart.dev/tools/dart-compile) — `exe`, `aot-snapshot`, `kernel`, `jit-snapshot`.
- [CLI distribution](https://dart.dev/tools/cli-distribution) — Ship a single self-contained binary.
- [`dartaotruntime`](https://dart.dev/tools/dartaotruntime) — Rehost an AOT snapshot (not Windows-specific, but useful to know).

| Tool | Description |
| --- | --- |
| [very_good_cli](https://pub.dev/packages/very_good_cli) | Scaffold production-quality Dart/Flutter CLIs and packages. |
| [dcli](https://pub.dev/packages/dcli) | Shell-style DSL for Dart scripts — commands, arguments, progress. |
| [mason_cli](https://pub.dev/packages/mason_cli) | Code generation and scaffolding via Dart bricks. |
| [build_cli](https://pub.dev/packages/build_cli) | Turn argv into a typed CLI with minimal boilerplate. |
| [args](https://pub.dev/packages/args) | The standard argument parser. |
| [fiber_shell](https://pub.dev/packages/fiber_shell) | Typed shell-command builder for desktop tools. |
| [dart_console](https://pub.dev/packages/dart_console) | Colorized, cursor-aware console output. |

---

## Testing & Debugging on Windows

- [Flutter integration tests](https://docs.flutter.dev/testing/integration-tests) · [testing overview](https://docs.flutter.dev/testing/overview) · [integration-test cookbook](https://docs.flutter.dev/cookbook/testing/integration/introduction)
- [test](https://pub.dev/packages/test) · [mocktail](https://pub.dev/packages/mocktail) — The Dart testing stack.

**Sysinternals — see what your app actually does**

- [Sysinternals Suite](https://learn.microsoft.com/en-us/sysinternals/downloads/) — The full toolkit.
- [Process Monitor](https://learn.microsoft.com/en-us/sysinternals/downloads/procmon) — File, registry, and process operations in real time.
- [Process Explorer](https://learn.microsoft.com/en-us/sysinternals/downloads/process-explorer) — Loaded modules, threads, handles.
- [DebugView](https://learn.microsoft.com/en-us/sysinternals/downloads/debugview) — Capture `OutputDebugString` and `print` output.
- [ProcDump](https://learn.microsoft.com/en-us/sysinternals/downloads/procdump) — Dump a hung or crashing process.
- [TCPView](https://learn.microsoft.com/en-us/sysinternals/downloads/tcpview) — Every socket on the machine.

**Profilers & debuggers**

- [Windows Performance Toolkit](https://learn.microsoft.com/en-us/windows-hardware/test/wpt/) — [Recorder](https://learn.microsoft.com/en-us/windows-hardware/test/wpt/windows-performance-recorder) / [Analyzer](https://learn.microsoft.com/en-us/windows-hardware/test/wpt/windows-performance-analyzer).
- [Event Tracing for Windows (ETW)](https://learn.microsoft.com/en-us/windows-hardware/test/wpt/event-tracing-for-windows) · [Win32 ETW portal](https://learn.microsoft.com/en-us/windows/win32/etw/event-tracing-portal)
- [WinDbg / Debugging Tools](https://learn.microsoft.com/en-us/windows-hardware/drivers/debugger/) — Microsoft's native debugger.
- [Windows Error Reporting](https://learn.microsoft.com/en-us/windows/win32/wer/windows-error-reporting) — How Windows reports crashes.
- [`GetLastError`](https://learn.microsoft.com/en-us/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) — The first thing to check when an FFI call fails.

---

## Tooling & Build

- **Enable desktop:** `flutter config --enable-windows-desktop`, then `flutter create --platforms=windows my_app`.
- **Run:** `flutter run -d windows`
- **Build:** `flutter build windows` → output in `build\windows\runner\Release`
- **Rename the binary:** set `BINARY_NAME` in `windows\CMakeLists.txt`.
- **Native code:** open the Visual Studio solution generated under `build\windows`.
- **Validate your setup:** `flutter doctor -v` and `flutter devices`.
- **Icon/resources:** `windows\runner\resources`.
- **Versioning:** `--build-name` / `--build-number` when building for release.

---

## Related Windows Platform Resources

Non-Dart, but directly relevant to shipping a Windows Flutter app.

- [WebView2](https://developer.microsoft.com/en-us/microsoft-edge/webview2/) — The engine behind every Flutter Windows webview.
- [Windows App SDK](https://learn.microsoft.com/en-us/windows/apps/windows-app-sdk/) — Modern Windows app platform.
- [Windows UI design guidance](https://learn.microsoft.com/en-us/windows/apps/design/) — Microsoft's design system docs (linked from Flutter's own Windows docs).
- [MSIX packaging](https://learn.microsoft.com/en-us/windows/msix/overview) — The Store-ready package format.
- [C++ deployment examples](https://learn.microsoft.com/en-us/cpp/windows/deployment-examples?view=msvc-170) — Redistributing the VC++ runtime.

---

## Contributing

PRs are welcome! Please:

1. **Check the link resolves** before submitting.
2. Prefer **Windows-specific** resources; cross-platform packages belong in [awesome-flutter](https://github.com/Solido/awesome-flutter) instead — here they qualify only if they have meaningful Windows-specific value.
3. Keep descriptions to **one line**, sentence case, no trailing period.
4. Add new entries to the **most relevant section**, in alphabetical order within the table.
5. Follow the awesome-list [contribution guidelines](https://github.com/sindresorhus/awesome/blob/main/contributing.md).

## License

[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/) — to the extent possible law, the authors have waived all copyright and related rights to this list.
