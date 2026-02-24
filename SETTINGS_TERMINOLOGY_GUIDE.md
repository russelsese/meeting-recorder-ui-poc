# VoiceInsight Settings — Terminology & Recommendations Guide

---

## 1. Terminology Clarification

### API Key vs Token vs Credential

| Term | Definition | Usage in VoiceInsight |
|------|-----------|----------------------|
| **API Key** | Long alphanumeric secret credential that authenticates your app to an external service | ✅ Correct term: "Enter your OpenAI **API Key**" |
| **Token** | In LLM context: units of text being processed (not authentication) | ❌ Don't use for authentication: "Enter your token" |
| **Credential** | Umbrella term for authentication secrets (API keys, passwords, tokens) | ✅ Can use: "Manage your **credentials**" |
| **API Secret** | Alternative name for API Key (less common) | ✅ Can use: "Your API **secret**" |

**Best Practice**: Use **"API Key"** when prompting users to enter authentication credentials.

### Provider Selection

| Term | Definition | Usage |
|------|-----------|-------|
| **Provider** | A service/company offering AI capabilities (OpenAI, Anthropic, Google, etc.) | ✅ "Select your AI **provider**" |
| **Model** | The specific AI model within a provider (GPT-4, Claude 3 Opus, etc.) | ✅ "Choose a **model** within your provider" |
| **Service** | General term for external service | ✅ Can use, but less specific |
| **Engine** | Alternative for model (OpenAI historically used this) | ⚠️ Outdated, avoid |

**Best Practice**: Use **"Provider"** for company selection, **"Model"** for specific AI selection within that provider.

---

## 2. Recommended Settings by Category

### Category 1: AI & Language Processing
**Purpose**: Control which AI services power the core functionality

#### Setting: Primary Transcription Provider
```
Label: "Transcription Service"
Description: "Which AI converts speech to text"

Options:
┌─────────────────────────────────────┐
│ ○ OpenAI Whisper (Recommended)      │  Most accurate, ~$0.36/min
│ ○ Google Cloud Speech-to-Text       │  Good accuracy, $1.44/hr
│ ○ Anthropic (Claude)                │  Context-aware, enterprise
│ ○ AssemblyAI                        │  Fast, good for live
└─────────────────────────────────────┘

Why: Different services have different accuracy, latency, and cost
```

**Alternatives to consider:**
- Azure Speech Services
- AWS Transcribe
- Rev AI
- Descript

#### Setting: AI Provider for Summarization
```
Label: "Summary AI Model"
Description: "Which AI generates summaries and key points"

Options:
┌─────────────────────────────────────┐
│ ○ OpenAI GPT-4 (Best quality)       │  ~$0.03/min
│ ○ OpenAI GPT-3.5-turbo (Faster)     │  ~$0.003/min (10x cheaper)
│ ○ Anthropic Claude 3 Opus (Best)    │  Most capable, context-aware
│ ○ Anthropic Claude 3 Sonnet         │  Balanced speed/quality
│ ○ Google Gemini Pro                 │  Fast, decent quality
│ ○ Cohere                            │  Good for enterprise
└─────────────────────────────────────┘

Why: Different models have different quality, speed, and cost tradeoffs
```

#### Setting: Transcript Language
```
Label: "Primary Language"
Description: "Language of recordings"

Recommended options:
- Auto-detect (intelligently choose)
- English (US)
- English (UK)
- Spanish (ES)
- French (FR)
- Mandarin (ZH)
- Japanese (JA)
- German (DE)
- Portuguese (BR)
- [+10 more]

Why: Improves accuracy of transcription and analysis
```

#### Setting: Summary Detail Level
```
Label: "Summary Length"
Description: "How detailed should summaries be?"

Options:
┌──────────────────────────────────────────┐
│ ○ Brief (1 paragraph, ~100 words)        │
│ ● Standard (2-3 paragraphs, ~200 words)  │
│ ○ Detailed (4-5 paragraphs, ~400 words)  │
│ ○ Very Detailed (6-8 paragraphs, +600)   │
└──────────────────────────────────────────┘

Why: Users may prefer quick summaries or comprehensive overviews
```

#### Setting: Key Points Count
```
Label: "Key Points per Recording"
Description: "How many takeaways to extract?"

Options:
┌───────────────────────────────────┐
│ ○ Few (3-5 points)                │
│ ● Standard (5-8 points)           │
│ ○ Comprehensive (8-12 points)     │
│ ○ Exhaustive (12+ points)         │
└───────────────────────────────────┘

Why: More points may be useful for long meetings, distracting for short ones
```

---

### Category 2: API Keys & Credentials
**Purpose**: Securely store and manage authentication

#### Setting: OpenAI Configuration
```
┌─────────────────────────────────────────┐
│ OpenAI API Configuration                │
├─────────────────────────────────────────┤
│ API Key: [••••••••••••••••••]            │  Masked for security
│           [View] [Copy] [Change]        │
│                                         │
│ Organization ID: [optional]             │  For multi-org accounts
│                                         │
│ ℹ️ Get key: https://platform.openai.com │
└─────────────────────────────────────────┘

Features:
- View last 4 chars: sk-...nJ7k
- Copy to clipboard for easy pasting
- Validate before saving
- Show status: ✓ Active or ✗ Invalid
```

#### Setting: Anthropic Configuration
```
┌─────────────────────────────────────────┐
│ Anthropic API Configuration             │
├─────────────────────────────────────────┤
│ API Key: [••••••••••••••••••]            │
│           [View] [Copy] [Change]        │
│                                         │
│ Default Model Selection:                │
│ ○ Claude 3 Opus (Most capable)          │ Best for complex tasks
│ ○ Claude 3 Sonnet (Balanced)            │ Recommended (fast & good)
│ ○ Claude 3 Haiku (Fastest)              │ For quick summaries
│                                         │
│ Max Tokens: [4096 ▼]                    │ Output length limit
│                                         │
│ ℹ️ Get key: https://console.anthropic.com
└─────────────────────────────────────────┘

Features:
- Choose between 3 Claude models
- Adjust output length (tokens)
- API key validation
```

#### Setting: Google Cloud Configuration
```
┌─────────────────────────────────────────┐
│ Google Cloud API Configuration          │
├─────────────────────────────────────────┤
│ API Key: [••••••••••••••••••]            │
│           [View] [Copy] [Change]        │
│                                         │
│ Project ID: [my-project-12345]          │
│                                         │
│ Models Available:                       │
│ ✓ Gemini 1.5 Pro                        │
│ ✓ Gemini 1.5 Flash                      │
│ ✓ Speech-to-Text API                    │
│ ✓ Text-to-Speech API                    │
│                                         │
│ ℹ️ Set up: https://console.cloud.google │
└─────────────────────────────────────────┘

Features:
- Requires Project ID
- Multiple services available
- Free tier available
```

#### Setting: Multi-Provider Fallback (Advanced)
```
Label: "Backup Provider"
Description: "Use if primary service fails"

Options:
┌──────────────────────────────────────┐
│ ○ Disabled (fail if primary down)    │
│ ● Enable (auto-switch on error)      │
│                                      │
│ Fallback priority:                   │
│ 1. OpenAI GPT-3.5-turbo              │
│ 2. Anthropic Claude 3 Sonnet         │
│ 3. Google Gemini                     │
└──────────────────────────────────────┘

Why: Keeps app working even if primary service is down
```

---

### Category 3: Recording Preferences
**Purpose**: Control how audio is captured

#### Setting: Recording Quality
```
Label: "Audio Quality"
Description: "Sample rate (quality vs file size)"

Options:
┌──────────────────────────────────────────┐
│ ○ Low (8 kHz) - Phone quality, ~5 MB/hr │
│ ○ Standard (16 kHz) - Good, ~10 MB/hr   │
│ ● High (44.1 kHz) - CD quality, ~40 MB  │
│ ○ Very High (48 kHz) - Studio, ~45 MB   │
└──────────────────────────────────────────┘

Why: Higher = better transcription accuracy but larger files
```

#### Setting: Audio Format
```
Label: "Audio Format"
Description: "File format for recordings"

Options:
┌──────────────────────────────────────────┐
│ ● WAV (Lossless, ~45 MB/hr)              │ Best quality
│ ○ MP3 (Compressed, ~4 MB/hr)             │ Most compatible
│ ○ WEBM (Modern, ~6 MB/hr)                │ Web-optimized
│ ○ FLAC (Lossless, ~25 MB/hr)             │ Archive quality
└──────────────────────────────────────────┘

Why: WAV for archival, MP3 for sharing, WEBM for web
```

#### Setting: Microphone Selection
```
Label: "Input Device"
Description: "Which microphone to use"

Options (dynamic):
┌──────────────────────────────────────────┐
│ ○ Default Device                         │ System default
│ ○ Built-in Microphone                    │ Laptop/phone mic
│ ○ Bluetooth Headset                      │ Wireless
│ ○ USB Microphone                         │ External
│ ○ [Detect Devices]                       │ Refresh list
└──────────────────────────────────────────┘

Why: Some mics are better for different environments
```

#### Setting: Silence Detection
```
Label: "Silence Detection"
Description: "Auto-stop on extended silence"

Control:
┌──────────────────────────────────────────┐
│ Enable Noise Gate             [Toggle ON] │
│ Threshold: [-40 dB] ← ← → → [+5 dB]    │
│ Timeout: [5 seconds] ← → [30 seconds]   │
│                                          │
│ ℹ️ Recording will pause if no sound      │
│    detected for specified duration       │
└──────────────────────────────────────────┘

Why: Saves space and reduces background noise
```

---

### Category 4: Playback & Display
**Purpose**: Customize user interface experience

#### Setting: Default Playback Speed
```
Label: "Default Playback Speed"
Options: 0.75x | 1x (Normal) | 1.25x | 1.5x

Why: Users may want faster playback to save time
```

#### Setting: Transcript Font Size
```
Label: "Transcript Text Size"
Options:
- Small (10px) - Fit more text
- Medium (12px) - Default
- Large (14px) - Better readability
- Extra Large (16px) - Accessibility

Why: Different users have different vision needs
```

#### Setting: Visual Preferences
```
☑ Show Timestamps in Transcript      [Toggle ON]
☑ Auto-scroll with Playback          [Toggle OFF]
☑ Highlight Current Speaker          [Toggle ON]
☑ Show Confidence Scores             [Toggle OFF]
☑ Dark Mode                          [Toggle OFF]

Why: Different preferences for different use cases
```

---

### Category 5: Data & Privacy
**Purpose**: Control data retention and privacy

#### Setting: Auto-Delete Policy
```
Label: "Auto-Delete After"
Options:
┌──────────────────────────────────────┐
│ ● Keep Forever                       │
│ ○ 30 Days                            │
│ ○ 90 Days                            │
│ ○ 1 Year                             │
│ ○ Never (manual only)                │
└──────────────────────────────────────┘

Why: Compliance with data retention policies
```

#### Setting: Storage Location
```
Label: "Where Are Recordings Stored?"
Options:
┌──────────────────────────────────────┐
│ ● Local Device Only (Most Private)   │
│ ○ Cloud Backup (Firebase)            │
│ ○ Hybrid (Local + Cloud)             │
│ ○ Enterprise Server                  │
└──────────────────────────────────────┘

Storage Status:
Using: 2.4 GB / 10 GB free
[Clear Cache] [Manage Files]

Why: Privacy vs accessibility tradeoff
```

#### Setting: Privacy Mode
```
☐ Include Device Data            [Toggle OFF]
☐ Track Usage Analytics          [Toggle OFF]
☐ Share Error Logs               [Toggle OFF]
☐ Allow Crash Reporting          [Toggle OFF]

Why: User may want maximum privacy
```

---

### Category 6: Export & Backup
**Purpose**: Control data export and archival

#### Setting: Default Export Format
```
Label: "Export Format"
Options:
┌──────────────────────────────────────┐
│ ○ PDF (Formatted document)           │ Best for sharing
│ ● TXT (Plain text)                   │ Simple
│ ○ MARKDOWN (With formatting)         │ For docs
│ ○ JSON (All metadata)                │ For archival
│ ○ Word (.docx)                       │ For editing
│ ○ CSV (Tabular data)                 │ For analysis
└──────────────────────────────────────┘

Why: Different formats for different purposes
```

#### Setting: Automatic Backup
```
Label: "Auto-Backup"
Options:
┌──────────────────────────────────────┐
│ ○ Disabled                           │
│ ○ Daily                              │
│ ● Weekly (Recommended)               │
│ ○ Monthly                            │
│ ○ On Every Save                      │
└──────────────────────────────────────┘

Backup Service:
[Google Drive ▼] [Edit Credentials]

Last Backup: Feb 24, 2:34 PM
[Backup Now]

Why: Protection against data loss
```

---

### Category 7: Notifications & Alerts
**Purpose**: Control how app communicates with user

#### Recommended Notifications
```
☑ Recording Started              [Toggle ON]
☑ Processing Complete            [Toggle ON]
☑ Upload Failed                  [Toggle ON]
☐ Daily Summary                  [Toggle OFF]
☐ Storage Limit Warning          [Toggle ON]
☐ Update Available               [Toggle ON]
```

---

### Category 8: About & Help
**Purpose**: App information and support

#### Essential Links
```
- Version: 1.0.0 (Build 2026.024)
- [Check for Updates]
- [Release Notes]
- [Privacy Policy]
- [Terms of Service]
- [API Documentation]
- [Send Feedback]
- [Report a Bug]
- [Contact Support]
```

---

## 3. Settings Architecture

### Data Structure (JSON)
```javascript
{
  // AI Configuration
  ai: {
    transcription: {
      provider: "openai" | "google" | "anthropic" | "assemblyai",
      language: "auto" | "en-US" | "es-ES" | ...,
      apiKey: "sk-..." // Encrypted
    },
    summarization: {
      provider: "openai" | "anthropic" | "google",
      model: "gpt-4" | "claude-3-opus" | "gemini-1.5-pro",
      detailLevel: "brief" | "standard" | "detailed",
      keyPointsCount: 5 | 8 | 12
    },
    fallback: {
      enabled: boolean,
      primaryProvider: string,
      secondaryProvider: string
    }
  },

  recording: {
    quality: 8000 | 16000 | 44100 | 48000,
    format: "wav" | "mp3" | "webm" | "flac",
    silenceDetection: boolean,
    silenceThreshold: -40, // dB
    silenceTimeout: 5 // seconds
  },

  playback: {
    defaultSpeed: 0.75 | 1 | 1.25 | 1.5,
    fontSize: "small" | "medium" | "large" | "xl",
    showTimestamps: boolean,
    autoScroll: boolean,
    highlightSpeaker: boolean
  },

  privacy: {
    autoDeleteDays: null | 30 | 90 | 365,
    storageLocation: "local" | "cloud" | "hybrid",
    analyticsEnabled: boolean,
    crashReportingEnabled: boolean
  },

  export: {
    defaultFormat: "txt" | "pdf" | "markdown" | "json" | "docx",
    autoBackup: "disabled" | "daily" | "weekly" | "monthly",
    backupService: "google-drive" | "dropbox" | "aws-s3"
  },

  notifications: {
    recordingStart: boolean,
    processingComplete: boolean,
    uploadFailed: boolean,
    dailySummary: boolean,
    storageWarning: boolean,
    updateAvailable: boolean
  }
}
```

---

## 4. Security Best Practices for Settings

### API Key Storage
```
✅ DO:
- Store in encrypted localStorage
- Encrypt sensitive data
- Validate before saving
- Show only last 4 characters
- Allow copy-to-clipboard

❌ DON'T:
- Store in plain text
- Send to own backend (in POC)
- Display full key in UI
- Log to console
- Include in exports
```

### Validation Checklist
```javascript
// Before saving API key:
1. Check if key is non-empty
2. Check if key format matches provider (sk-... for OpenAI)
3. Validate API key by making test call
4. Show success/error message
5. Encrypt before storing
6. Log validation only (not key value)
```

---

## 5. User Workflow: Initial Setup

```
First Launch
  ↓
Dashboard
  ↓
[Tap Settings icon or menu]
  ↓
Settings Screen
  ↓
Select Transcription Provider (OpenAI, Google, Anthropic)
  ↓
[Edit API Key] → Enter key → Validate
  ↓
Select Summarization AI (GPT-4, Claude, Gemini)
  ↓
[Edit API Key] → Enter key → Validate
  ↓
(Optional) Adjust Recording Quality & Format
  ↓
(Optional) Adjust Playback & Display
  ↓
Save Settings
  ↓
Ready to Record!
```

---

## 6. Default Settings Recommendations

```javascript
// Recommended defaults for best UX
{
  ai: {
    transcription: { provider: "openai", language: "auto" },
    summarization: {
      provider: "openai",
      model: "gpt-3.5-turbo", // Cheaper/faster
      detailLevel: "standard",
      keyPointsCount: 5
    }
  },
  recording: {
    quality: 44100,      // CD quality
    format: "wav",       // Lossless
    silenceDetection: false
  },
  playback: {
    defaultSpeed: 1,
    fontSize: "medium",
    showTimestamps: true
  },
  privacy: {
    autoDeleteDays: null,  // Keep forever
    storageLocation: "local"
  },
  export: {
    defaultFormat: "txt"
  },
  notifications: {
    recordingStart: true,
    processingComplete: true,
    uploadFailed: true
  }
}
```

---

*VoiceInsight Settings Guide v1.0 · February 2026*
