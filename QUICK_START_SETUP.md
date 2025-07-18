# QUICK START GUIDE - Free Tools Installation
## Get Up and Running in 30 Minutes

### 🚀 Essential Tools Download List

#### **Video Production Suite**
```
1. DaVinci Resolve 19 (FREE - Professional Editor)
   ├── Download: https://www.blackmagicdesign.com/products/davinciresolve
   ├── Size: ~3.5GB download
   ├── System: Windows 10/11, 16GB RAM minimum
   └── Time: 20 minutes install + 10 minutes setup

2. OBS Studio (FREE - Screen Recording)
   ├── Download: https://obsproject.com/
   ├── Size: ~300MB download  
   ├── System: Windows 10/11, any modern PC
   └── Time: 5 minutes install + 5 minutes config

3. Audacity (FREE - Audio Editor)
   ├── Download: https://www.audacityteam.org/
   ├── Size: ~50MB download
   ├── System: Windows 10/11, minimal requirements
   └── Time: 3 minutes install + 2 minutes setup
```

#### **Graphics & Design**
```
4. GIMP (FREE - Image Editor)
   ├── Download: https://www.gimp.org/
   ├── Size: ~200MB download
   ├── Alternative: Paint.NET (lighter option)
   └── Time: 5 minutes install

5. Canva (FREE Web-based)
   ├── Access: https://www.canva.com/
   ├── Account: Free registration required
   ├── Templates: Video thumbnails, social graphics
   └── Time: 2 minutes signup
```

### ⚡ Step-by-Step Installation Process

#### **Phase 1: Core Video Tools (20 minutes)**

**Step 1: DaVinci Resolve Installation**
```
1. Visit https://www.blackmagicdesign.com/products/davinciresolve
2. Click "Download Now" (free version)
3. Fill registration form (required for download)
4. Download DaVinci_Resolve_19_Windows.exe
5. Run installer as Administrator
6. Choose "Install for all users"
7. Accept default installation path
8. Wait for completion (~15 minutes)
9. Launch and complete initial setup wizard
```

**Step 2: OBS Studio Setup**
```
1. Visit https://obsproject.com/
2. Click "Download OBS Studio" → Windows
3. Run OBS-Studio-XX-Windows-Installer.exe
4. Accept defaults, install
5. Launch OBS Studio
6. Run Auto-Configuration Wizard:
   - Purpose: "Recording"
   - Resolution: 1920x1080
   - FPS: 30
   - Quality: "High quality, medium file size"
```

#### **Phase 2: Audio & Graphics (10 minutes)**

**Step 3: Audacity Installation**
```
1. Visit https://www.audacityteam.org/
2. Download Audacity for Windows
3. Run installer, accept defaults
4. Launch Audacity
5. Go to Edit → Preferences → Recording
6. Set quality to "44100 Hz, 16-bit, Stereo"
```

**Step 4: Graphics Tools Setup**
```
Option A - GIMP (Full Featured):
1. Download from https://www.gimp.org/
2. Run installer, accept defaults
3. Launch and skip startup tips

Option B - Paint.NET (Lighter):
1. Download from https://www.getpaint.net/
2. Install .NET Framework if prompted
3. Run installer, accept defaults
```

### 🔧 Essential Configuration

#### **OBS Studio Recording Setup**
```
SCENES TO CREATE:

Scene 1: "Full Desktop"
├── Source: Display Capture
├── Settings: Capture entire primary monitor
├── Use: Intro/outro, overview shots

Scene 2: "Browser Window"  
├── Source: Window Capture
├── Target: Chrome/Edge browser
├── Use: Power Apps, Azure demos

Scene 3: "PowerPoint"
├── Source: Window Capture  
├── Target: PowerPoint presentation
├── Use: Slides and explanations

RECORDING SETTINGS:
├── Output → Recording → Recording Path: C:\VideoProduction\Recordings\
├── Output → Recording → Recording Format: MP4
├── Output → Recording → Encoder: Software (x264)
├── Video → Base Resolution: 1920x1080
├── Video → Output Resolution: 1920x1080
├── Video → FPS: 30
├── Audio → Sample Rate: 44.1kHz
```

#### **DaVinci Resolve Project Template**
```
INITIAL SETUP:
1. Launch DaVinci Resolve
2. Create new project: "Belgian_SME_Template"
3. Project Settings:
   - Timeline resolution: 1920x1080 HD
   - Timeline frame rate: 30fps
   - Playback frame rate: 30fps
4. Save as template for future projects

BASIC TIMELINE SETUP:
├── Track V1: Main video content
├── Track V2: Graphics/overlays
├── Track V3: Transitions
├── Track A1: Voice recording
├── Track A2: Background music
└── Track A3: Sound effects
```

### 📁 Folder Structure Creation

**Copy this PowerShell command to create instant folder structure:**
```powershell
# Run this in PowerShell to create production folders
$basePath = "$env:USERPROFILE\Documents\VideoProduction"
$folders = @(
    "Projects\01_E-Facturatie",
    "Projects\02_AI_Document",
    "Projects\03_Power_Apps", 
    "Projects\04_API_Security",
    "Projects\05_Data_Sovereignty",
    "Projects\06_Cost_Optimization",
    "Projects\07_Cybersecurity",
    "Projects\08_AI_for_SME",
    "Projects\09_Platform_Governance",
    "Projects\10_Peppol_Troubleshooting",
    "Assets\Audio",
    "Assets\Graphics",
    "Assets\Templates",
    "Exports\Final_Videos",
    "Exports\Social_Media",
    "Archives"
)

foreach ($folder in $folders) {
    New-Item -Path "$basePath\$folder" -ItemType Directory -Force
}
Write-Host "Video production folders created at: $basePath"
```

### 🎤 Audio Setup Testing

#### **Microphone Test Procedure**
```
1. Connect USB microphone (or use built-in)
2. Open Audacity
3. Click red "Record" button
4. Speak: "This is a microphone test for video production"
5. Click "Stop" button
6. Play back recording
7. Check levels: Should peak around -12dB to -6dB
8. If too quiet: Increase microphone gain
9. If too loud: Reduce microphone gain or move further away
```

#### **OBS Audio Testing**
```
1. In OBS, check "Audio Mixer" panel
2. Speak into microphone
3. Watch audio levels meter
4. Target: Green zone (-20dB to -12dB while speaking)
5. Adjust: Right-click microphone → Filters → Gain
6. Test recording: Start Recording → speak → Stop Recording
7. Check file location and playback quality
```

### ✅ Installation Verification Checklist

```
BEFORE STARTING FIRST VIDEO:
[ ] DaVinci Resolve launches without errors
[ ] OBS Studio records screen successfully  
[ ] Audacity records and plays audio clearly
[ ] Graphics software (GIMP/Paint.NET) opens
[ ] Folder structure created for organization
[ ] Microphone levels tested and optimal
[ ] Test recording completed and reviewed
[ ] All software shortcuts added to desktop
[ ] Browser bookmarks created for web tools
[ ] Project template saved in DaVinci Resolve
```

### 🆘 Common Installation Issues

#### **DaVinci Resolve Problems**
```
Issue: "GPU not supported" error
Solution: Update graphics drivers or use proxy media

Issue: Slow performance
Solution: Lower timeline resolution to 720p for editing

Issue: Audio not syncing
Solution: Check project frame rate matches source footage
```

#### **OBS Studio Problems**  
```
Issue: Black screen when recording
Solution: Run OBS as Administrator

Issue: Audio not recording
Solution: Check microphone permissions in Windows Privacy settings

Issue: Large file sizes
Solution: Adjust encoder settings to "Fast" preset
```

### 📞 Support Resources

```
HELP DOCUMENTATION:
├── DaVinci Resolve: https://documents.blackmagicdesign.com/
├── OBS Studio: https://obsproject.com/wiki/
├── Audacity: https://manual.audacityteam.org/
└── General: YouTube "beginner tutorials" for each tool

COMMUNITY SUPPORT:
├── Reddit: r/davinciresolve, r/obs
├── Forums: Official support forums for each tool
├── YouTube: Thousands of free tutorial videos
└── Local: Belgian video production Facebook groups
```

---

## 🎯 **YOU'RE READY TO START!**

Once these tools are installed and tested, you have everything needed to begin professional video production. **Estimated total setup time: 30-45 minutes.**

**Next step:** Review the complete script for Video 1 (E-facturatie 2026) and begin your first demo recording!

**Remember:** Start simple, improve with each video. The tools are powerful but user-friendly - perfect for creating professional content that will establish your company as the leading IT partner for Belgian SMEs.
