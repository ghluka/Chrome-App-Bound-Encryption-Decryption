# ChromElevator <sup><sub><sup>(`Chrome App-Bound Encryption Decryption`)

## 🚀 Overview

![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Windows%20x64%20%7C%20ARM64-lightgrey)
![Languages](https://img.shields.io/badge/code-C%2B%2B%20%7C%20ASM-9cf)
[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/xaitax/Chrome-App-Bound-Encryption-Decryption)

A post-exploitation tool demonstrating a complete, in-memory bypass of Chromium's **App-Bound Encryption (ABE)**. Made by xaitax, support [xaitax's ko-fi](https://ko-fi.com/M4M61EP5XL) if you enjoyed this project. This fork compiles the elevator as a DLL instead of an EXE. Check [xaitax's original README](https://github.com/xaitax/Chrome-App-Bound-Encryption-Decryption/blob/main/README.md) for more information about how this works.

## 🔧 Build Instructions

Build Options:
- `make.bat build_target_dll` - builds chromelevator.dll

### Automated Builds with GitHub Actions

This project uses GitHub Actions to automatically build the injector executable (`chromelevator.dll`) for both **x64** and **ARM64** architectures.

**Release Package Contents:**

- `chromelevator_x64.dll`
- `chromelevator_arm64.dll`

## 📦 Supported & Tested Versions

| Browser                    | Tested Version (x64 & ARM64) |
| -------------------------- | ---------------------------- |
| **Google Chrome**          | 144.0.7559.133               |
| **Google Chrome Beta**     | 145.0.7632.18                |
| **Brave**                  | 1.86.148 (144.1.86.148)      |
| **Microsoft Edge**         | 145.0.3800.36                |
| **Avast Secure Browser**   | 143.0.33371.147              |

> **Note:** Chrome/Brave/Edge 144+ use the new `IElevator2` COM interface. This tool automatically uses `IElevator2` when available and falls back to `IElevator` for older versions. Avast Secure Browser uses a custom `IElevatorChrome` interface with an extended vtable (12 methods, DecryptData at offset 104).

## 🔍 Feature Support Matrix

This matrix outlines the extraction capabilities for each supported browser.

| Feature              | Google Chrome          | Microsoft Edge         | Brave                  | Avast Secure Browser   |
|----------------------|------------------------|------------------------|------------------------|------------------------|
| **Cookies**         | ✅ ABE                | ✅ ABE                | ✅ ABE                | ✅ ABE                |
| **Passwords**       | ✅ ABE                | ✅ ABE                | ✅ ABE                | ✅ ABE                |
| **Payment Methods** | ✅ ABE                | ✅ ABE                | ✅ ABE                | ✅ ABE                |
| **IBANs**           | ✅ ABE                | ❌ N/A                | ✅ ABE                | ✅ ABE                |
| **Auth Tokens**     | ✅ Google             | ❌ N/A                | ❌ N/A                | ❌ N/A                |

## 🔬 Technical Workflow

[Check xaitax's original README for more information about how this works.](https://github.com/xaitax/Chrome-App-Bound-Encryption-Decryption/blob/main/README.md#-technical-workflow)