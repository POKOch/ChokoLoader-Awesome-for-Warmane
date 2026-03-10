# ChokoLoader — AwesomeWoTLK on Warmane

> **Use at your own risk. No guarantees. You are fully responsible for your account.**

A tool that allows [AwesomeWoTLK](https://github.com/noname08662/awesome_wotlk) modifications to work
on Warmane (Lordaeron / Icecrown / Frostmourne) without detection.

---

## ⚠️ CRITICAL WARNING

> **DO NOT press "Logout" or "Back to Login" while playing!**
>
> If you **Logout → Back**, there is a **HIGH chance of detection**.
> If you **Logout** at all, there is still a **chance of detection**.
>
> **This will be fixed in a future version.**
>
> ✅ **Correct usage:** Inject → Play → Close the game when done.
> ❌ **Wrong usage:** Inject → Play → Logout → Back → Play again.

---

## 📦 Contents

| File / Folder | Description |
|---------------|-------------|
| `AwesomeWotlk.dll` | Main modification library |
| `AwesomePatcher.exe` | One-time game client patcher |
| `skia.dll` | Graphics library (required by Awesome) |
| `AwesomeCVar/` | Addon folder for Awesome settings |
| `Choko.dll` | Protection module |
| `DLL_Injector.exe` | Simple DLL injector |
| `inject.bat` | One-click injection script |

---

## 🚀 Installation (one-time setup)

### Step 1 — Copy files

Copy these files into your **World of Warcraft root folder** (where `Wow.exe` is):

```
World of Warcraft/
├── Wow.exe                ← already here
├── AwesomeWotlk.dll       ← copy here
├── AwesomePatcher.exe     ← copy here
├── skia.dll               ← copy here
├── Choko.dll              ← copy here
├── DLL_Injector.exe       ← copy here
└── inject.bat             ← copy here
```

### Step 2 — Copy the addon

Copy the `AwesomeCVar` **folder** into your `Interface/AddOns` directory:

```
World of Warcraft/
└── Interface/
    └── AddOns/
        └── AwesomeCVar/   ← copy this entire folder here
            ├── AwesomeCVar.toc
            ├── AwesomeCVar.lua
            └── ...
```

> 💡 If the `Interface/AddOns` folder doesn't exist, create it manually.

### Step 3 — Patch the client

1. Run `AwesomePatcher.exe` from the WoW folder
2. Wait for "Patch successful" message
3. Done! You can delete the patcher or keep it — your choice

> ⚠️ You only need to patch **once**. Don't run the patcher again unless you
> reinstall the game client.

---

## 🎮 How to Play (every time)

### Option A — Easy (recommended)

1. Launch your **patched** `Wow.exe`
2. At the login screen, **double-click** `inject.bat`
3. **⚡ IMPORTANT:** A **VMProtect dialog box** will appear — click **"OK"** to continue
4. Wait 2-3 seconds
5. Log in and play!

### Option B — Manual (advanced)

1. Launch your **patched** `Wow.exe`
2. Open **Command Prompt** (cmd) in the game folder
3. Run:
   ```
   DLL_Injector.exe Wow.exe Choko.dll
   ```
4. **⚡ IMPORTANT:** A **VMProtect dialog box** will appear — click **"OK"** to continue
5. You should see "Injection successful"
6. Log in and play!

> 💡 **Tip:** To open cmd in the game folder, type `cmd` in the
> Windows Explorer address bar while in the WoW folder, then press Enter.

---

## ⚡ VMProtect Dialog

When you inject `Choko.dll`, you will see a popup window from VMProtect:

```
┌──────────────────────────────────┐
│                                  │
│   VMProtect message / warning    │
│                                  │
│            [ OK ]                │
│                                  │
└──────────────────────────────────┘
```

**This is normal and expected.** Simply click **"OK"** and the game will continue loading.

---

## 📋 inject.bat

Create this file in your WoW folder (or use the one provided):

```bat
@echo off
echo ============================================
echo   ChokoLoader - Injecting...
echo ============================================
echo.
echo   Make sure you clicked OK on the
echo   VMProtect dialog before injecting!
echo.

timeout /t 2 /nobreak >nul

DLL_Injector.exe Wow.exe Choko.dll

if %ERRORLEVEL% EQU 0 (
    echo.
    echo [OK] Injection successful! You can play now.
) else (
    echo.
    echo [!!] Injection failed. Make sure WoW is running.
    echo [!!] Did you click OK on the VMProtect dialog?
    echo [!!] Try running this .bat as Administrator.
)

echo.
echo ============================================
echo   DO NOT Logout or press Back in-game!
echo   Just close the game when you are done.
echo ============================================
echo.
pause
```

---

## ❓ Troubleshooting

| Problem | Solution |
|---------|----------|
| VMProtect dialog appeared | This is normal — just click **OK** |
| `Injection failed` | Make sure WoW.exe is running and you clicked OK on VMProtect dialog |
| `DLL not found` | Make sure all files are in the same folder as Wow.exe |
| `Access denied` | Right-click `inject.bat` → **Run as Administrator** |
| Game crashes on inject | Make sure you patched with `AwesomePatcher.exe` first |
| Awesome features not working | Wait a few seconds after injection before logging in |
| Awesome UI/settings missing | Make sure `AwesomeCVar` folder is in `Interface/AddOns/` |
| Antivirus blocks files | Add your WoW folder to antivirus exclusions |
| VMProtect dialog does not appear | You may be running the unpatched Wow.exe — run the patcher first |

---

## 🔒 Safety Rules

| ✅ DO | ❌ DON'T |
|-------|----------|
| Click OK on VMProtect dialog | Don't close the VMProtect dialog with X |
| Inject at login screen | Don't inject while in-game |
| Close game when done | Don't use Logout button |
| Use on alt accounts first | Don't use on your main without testing |
| Keep files up to date | Don't share your account |
| Wait 2-3 sec after inject | Don't spam inject multiple times |

---

## 📌 Important Notes

- Works with **WoW 3.3.5a (12340)** — Warmane servers
- Requires the **specific Wow.exe** that matches AwesomeWoTLK
- A **VMProtect dialog** will appear on every injection — always click **OK**
- If the game freezes during injection, kill `Wow.exe` in Task Manager and try again
- **Always test on a throwaway account first**

---

## 🔄 Updating

When a new version is released:
1. Close WoW
2. Replace the old files with the new ones
3. If `AwesomePatcher.exe` is included — run it again
4. Update `AwesomeCVar` addon folder if a new version is provided
5. Launch WoW → Inject `Choko.dll` → click OK on VMProtect dialog 

---

## ⚖️ Disclaimer

```
THIS SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND.

USE AT YOUR OWN RISK.

The authors are not responsible for any bans, account suspensions,
or other consequences resulting from the use of this software.

By using this software, you accept full responsibility for any
outcomes related to your game account(s).
```

---

## 📊 Version

| Component | Version |
|-----------|---------|
| ChokoLoader | 1.0.0 |
| Supported client | 3.3.5a (12340) |
| Last updated | 2026 |
