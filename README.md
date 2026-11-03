This is a custom FPT Windows x64 package, and `Application/` is the working copy of it with modified restriction behaviour. It documents a finding, it is not a supported product.

## Repository layout

Two folders, everything else is metadata.

| Path | What it holds |
| --- | --- |
| `Application/` | The runnable program: `SafeExamBrowser.exe`, `SafeExamBrowser.Client.exe`, SEB and CefSharp assemblies, Chromium resources, plus the `Configuration`, `Reset` and `Service` component folders |
| `Installation/` | `SEB_3.10.0.794_AutoSettings.msi`, the Windows Installer package for the same build, 311 MB |
| `.gitattributes` | Declares that `.dll`, `.exe` and `.msi` are stored with Git LFS |
| `README.md` | This file |

## Versions

| | Version | Source |
| --- | --- | --- |
| Build in this repository | 3.10.0.794 | Custom FPT package |
| Replacement build | 3.12 | Custom FPT package, dated 15 November 2026 |

The 3.10.0.794 and 3.12 versions are custom packages, not official releases (upstream's latest is 3.10.2). The MSI is what matters: it installs the build to `C:\Program Files (x86)\`, registers the service and creates Start Menu shortcuts, while the `Application` folder is just a working copy.

## Installation

This build requires version 3.10.0.794. The 3.12 package replaces it and removes the behaviour being studied.

1. Check the installed version under Settings → Apps → Safe Exam Browser.
2. If 3.12 is installed, uninstall it completely first, as its service component conflicts with the older build.
3. Install `Installation/SEB_3.10.0.794_AutoSettings.msi`.
4. Verify that the registered version is 3.10.0.794 before starting a session.

The package creates two uninstall entries: Safe Exam Browser (x64) and Safe Exam Browser, both showing version 3.10.0.794.

## Launch

Open `Application/` and double click `SafeExamBrowser.exe`. That starts the modified build from the folder, no installation needed.

- Keep the folder intact, as the executable depends on the DLLs and Chromium resources inside it.
- If a session leaves the machine in a blocked state, run `Application/Reset/SafeExamBrowser.ResetUtility.exe`.

# NOTICE

**Educational & Experimental Use Only**

This software is an unofficial custom build of Safe Exam Browser (SEB), modified exclusively for educational, research, and experimental purposes.

- Do not use this software for cheating, academic dishonesty, or unauthorized examination activities.
- Do not use it to circumvent institutional policies, security controls, or examination regulations.
- Use this software responsibly and only in environments where you have appropriate authorization.
- This build is not affiliated with, endorsed by, or officially supported by the original SEB development team.
- The software is provided "AS IS", without any warranties or guarantees.
- Users are solely responsible for their use of this software and must comply with applicable laws, licenses, and institutional policies.

**This custom build is intended for learning and experimentation, not for facilitating academic misconduct.**
