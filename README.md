# Awesome Dart & Flutter for Windows [![Awesome](https://raw.githubusercontent.com/sindresorhus/awesome/main/media/badge.svg)](https://awesome.re)

> A curated catalog of **Windows-focused** Dart & Flutter resources — packages, tooling, templates, docs, and community for building native Windows desktop apps.

Windows desktop is a first-class Flutter target: real Win32 windows, MSIX installers, Fluent UI, WebView2, system tray, registry access, and full `dart:ffi` access to the OS. This list collects the good stuff for that specific niche.

**Contents**

- [Official Documentation](#official-documentation)
- [Announcements & Deep Dives](#announcements--deep-dives)
- [Window Management & Chrome](#window-management--chrome)
- [Win32, COM & WinRT Interop](#win32-com--winrt-interop)
- [File Dialogs, Shell & Taskbar](#file-dialogs-shell--taskbar)
- [System Tray & Notifications](#system-tray--notifications)
- [Autostart, Hotkeys & Auto-Update](#autostart-hotkeys--auto-update)
- [Packaging, Installers & Deployment](#packaging-installers--deployment)
- [System, Hardware & Device Info](#system-hardware--device-info)
- [Windows UI (Fluent)](#windows-ui-fluent)
- [WebView2](#webview2)
- [Media, Printing & Input](#media-printing--input)
- [Templates, Samples & Showcase Apps](#templates-samples--showcase-apps)
- [Tooling & Build](#tooling--build)
- [Community](#community)
- [Related Windows Platform Resources](#related-windows-platform-resources)

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

## Win32, COM & WinRT Interop

The heart of "Windows-only" Dart.

| Package | Description |
| --- | --- |
| [win32](https://pub.dev/packages/win32) | Call common Win32 APIs and COM objects directly from Dart via FFI. The flagship package. |
| [win32_gui](https://pub.dev/packages/win32_gui) | Object-oriented Win32 GUI helpers built on `win32` + `dart:ffi`. |
| [win32_registry](https://pub.dev/packages/win32_registry) | Type-safe Windows Registry read/write. |
| [win32_gamepad](https://pub.dev/packages/win32_gamepad) | Type-safe XInput gamepad access. |
| [winrt](https://pub.dev/packages/winrt) | Windows Runtime (WinRT) APIs from a single package — experimental. |
| [serial_port_win32](https://pub.dev/packages/serial_port_win32) | Serial port I/O over the Win32 API. |
| [dart_console](https://pub.dev/packages/dart_console) | Console color, cursor, and input control for Dart CLI tools. |
| [file_saver](https://pub.dev/packages/file_saver) | Native save-file dialogs and file writing. |

**Explore more:** [pub.dev packages compatible with Windows](https://pub.dev/packages?q=platform%3Awindows)

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
