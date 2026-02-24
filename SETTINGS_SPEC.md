# VoiceInsight Settings Screen Specification

## Overview

The Settings screen allows users to configure AI providers, recording preferences, and app behavior.

---

## 1. Settings Categories

### 1.1 AI & Language Processing
**Purpose**: Configure which AI models power transcription and analysis

#### Setting: Transcription Provider
```
┌─────────────────────────────────────┐
│ Transcription Provider              │
├─────────────────────────────────────┤
│ Select service for speech-to-text   │
│                                     │
│ ○ OpenAI Whisper (Recommended)      │
│ ○ Google Cloud Speech-to-Text       │
│ ○ Anthropic (Claude with context)   │
│ ○ AssemblyAI                        │
└─────────────────────────────────────┘
```

**Why**: Different services have different accuracies, speed, and pricing

#### Setting: Transcription Language
```
┌─────────────────────────────────────┐
│ Transcription Language              │
├─────────────────────────────────────┤
│ Auto-detect (default)               │
│ English (US)                        │
│ English (UK)                        │
│ Spanish (ES)                        │
│ ... (20+ languages)                 │
└─────────────────────────────────────┘
```

**Why**: Multi-language support for global users

#### Setting: Summary Provider
```
┌─────────────────────────────────────┐
│ AI for Summarization                │
├─────────────────────────────────────┤
│ ○ OpenAI (GPT-4)                    │
│ ○ OpenAI (GPT-3.5-turbo) - Faster   │
│ ○ Anthropic (Claude 3 Opus)         │
│ ○ Anthropic (Claude 3 Sonnet)       │
│ ○ Google (Gemini Pro)               │
└─────────────────────────────────────┘
```

**Why**: Different models have different speeds/costs

#### Setting: Summary Detail Level
```
┌─────────────────────────────────────┐
│ Summary Length                       │
├─────────────────────────────────────┤
│ ○ Brief (1 paragraph)               │
│ ○ Standard (2-3 paragraphs)         │
│ ● Detailed (4-5 paragraphs)         │
└─────────────────────────────────────┘
```

#### Setting: Key Points Count
```
┌─────────────────────────────────────┐
│ How many key points to extract?      │
├─────────────────────────────────────┤
│ ○ Few (3-5 points)                  │
│ ● Standard (5-8 points)             │
│ ○ Comprehensive (8-12 points)       │
└─────────────────────────────────────┘
```

---

### 1.2 API Keys & Credentials
**Purpose**: Store and manage API keys securely

#### Setting: OpenAI Configuration
```
┌─────────────────────────────────────┐
│ OpenAI API Configuration            │
├─────────────────────────────────────┤
│ API Key: [••••••••••••••••••]        │
│                    [View] [Copy]    │
│ Update API Key  [Change]            │
│                                     │
│ ℹ️ Get API key from:                │
│ https://platform.openai.com/keys    │
└─────────────────────────────────────┘
```

#### Setting: Anthropic Configuration
```
┌─────────────────────────────────────┐
│ Anthropic API Configuration         │
├─────────────────────────────────────┤
│ API Key: [••••••••••••••••••]        │
│                    [View] [Copy]    │
│ Update API Key  [Change]            │
│                                     │
│ Model Selection:                    │
│ ○ Claude 3 Opus (Most capable)      │
│ ○ Claude 3 Sonnet (Balanced)        │
│ ○ Claude 3 Haiku (Fastest)          │
│                                     │
│ ℹ️ Get API key from:                │
│ https://console.anthropic.com      │
└─────────────────────────────────────┘
```

#### Setting: Google Cloud Configuration
```
┌─────────────────────────────────────┐
│ Google Cloud Configuration          │
├─────────────────────────────────────┤
│ API Key: [••••••••••••••••••]        │
│                    [View] [Copy]    │
│ Update API Key  [Change]            │
│                                     │
│ Project ID: [________________]      │
│                                     │
│ ℹ️ Set up at: console.cloud.google  │
└─────────────────────────────────────┘
```

**Security Notes**:
- ✅ Store API keys in secure local storage (encrypted if possible)
- ✅ Never send keys to your own server (client-side only in POC)
- ✅ Show only last 4 characters when viewing
- ✅ Provide "Copy to Clipboard" for easy pasting
- ✅ Add warning if API key is exposed

---

### 1.3 Recording Preferences
**Purpose**: Configure how recordings are captured

#### Setting: Recording Quality
```
┌─────────────────────────────────────┐
│ Recording Quality                   │
├─────────────────────────────────────┤
│ ○ Low (8 kHz) - Saves space         │
│ ○ Standard (16 kHz)                 │
│ ● High (44.1 kHz)                   │
│ ○ Very High (48 kHz) - Large file   │
└─────────────────────────────────────┘
```

#### Setting: Audio Format
```
┌─────────────────────────────────────┐
│ Audio Format                        │
├─────────────────────────────────────┤
│ ● WAV (lossless, larger files)      │
│ ○ MP3 (compressed, smaller)         │
│ ○ WEBM (modern, web-optimized)      │
│ ○ OGG (open format)                 │
└─────────────────────────────────────┘
```

#### Setting: Microphone Preference
```
┌─────────────────────────────────────┐
│ Microphone Selection                │
├─────────────────────────────────────┤
│ ○ Default device                    │
│ ○ Built-in microphone               │
│ ○ Bluetooth headset                 │
│ ○ USB microphone                    │
│                                     │
│ [Detect Microphones]                │
└─────────────────────────────────────┘
```

#### Setting: Automatic Silence Detection
```
┌─────────────────────────────────────┐
│ Silence Detection                   │
├─────────────────────────────────────┤
│ Enable noise gate            [Toggle]│
│ Threshold: _______ dB               │
│ (Stop recording if silent for >5s)  │
└─────────────────────────────────────┘
```

---

### 1.4 Playback & Display
**Purpose**: Customize playback behavior and UI

#### Setting: Default Playback Speed
```
┌─────────────────────────────────────┐
│ Default Playback Speed              │
├─────────────────────────────────────┤
│ ○ 0.75x                             │
│ ● 1x (Normal)                       │
│ ○ 1.25x                             │
│ ○ 1.5x                              │
└─────────────────────────────────────┘
```

#### Setting: Transcript Font Size
```
┌─────────────────────────────────────┐
│ Transcript Text Size                │
├─────────────────────────────────────┤
│ ○ Small (10px)                      │
│ ● Medium (12px)                     │
│ ○ Large (14px)                      │
│ ○ Extra Large (16px)                │
└─────────────────────────────────────┘
```

#### Setting: Show Timestamps in Transcript
```
┌─────────────────────────────────────┐
│ Show Timestamps          [Toggle On] │
│ Auto-scroll with playback [Toggle]   │
│ Highlight current speaker [Toggle]   │
│ Show confidence scores    [Toggle]   │
└─────────────────────────────────────┘
```

---

### 1.5 Data & Privacy
**Purpose**: Control data retention and privacy

#### Setting: Auto-Delete Recordings
```
┌─────────────────────────────────────┐
│ Auto-Delete After                   │
├─────────────────────────────────────┤
│ ● Keep forever                      │
│ ○ 30 days                           │
│ ○ 90 days                           │
│ ○ 1 year                            │
│ ○ Never (manual only)               │
└─────────────────────────────────────┘
```

#### Setting: Data Storage Location
```
┌─────────────────────────────────────┐
│ Recording Storage                   │
├─────────────────────────────────────┤
│ ○ Local device only (private)       │
│ ● Cloud (Firebase/AWS)              │
│ ○ Hybrid (local + cloud backup)     │
│                                     │
│ Storage used: 2.4 GB / 10 GB        │
│ [Manage Storage]                    │
└─────────────────────────────────────┘
```

#### Setting: Privacy Mode
```
┌─────────────────────────────────────┐
│ Privacy Mode                        │
├─────────────────────────────────────┤
│ Include device data        [Toggle]  │
│ Track usage analytics      [Toggle]  │
│ Share error logs           [Toggle]  │
│ Allow crash reporting      [Toggle]  │
└─────────────────────────────────────┘
```

---

### 1.6 Export & Backup
**Purpose**: Control how data is exported

#### Setting: Default Export Format
```
┌─────────────────────────────────────┐
│ Export Format                       │
├─────────────────────────────────────┤
│ ○ PDF (formatted document)          │
│ ● TXT (plain text)                  │
│ ○ MARKDOWN (with formatting)        │
│ ○ JSON (all data + metadata)        │
│ ○ WORD (.docx)                      │
└─────────────────────────────────────┘
```

#### Setting: Backup Preferences
```
┌─────────────────────────────────────┐
│ Automatic Backup                    │
├─────────────────────────────────────┤
│ ○ Disabled                          │
│ ○ Daily                             │
│ ● Weekly                            │
│ ○ Monthly                           │
│                                     │
│ Backup Service: Google Drive        │
│ Last backup: Feb 24, 2:34 PM        │
│ [Backup Now]                        │
└─────────────────────────────────────┘
```

---

### 1.7 Notifications & Alerts
**Purpose**: Manage app notifications

#### Setting: Recording Notifications
```
┌─────────────────────────────────────┐
│ Notify when recording starts  [Toggle] │
│ Notify when processing done   [Toggle] │
│ Notify for failed uploads     [Toggle] │
│ Daily summary notification    [Toggle] │
└─────────────────────────────────────┘
```

---

### 1.8 About & Help
**Purpose**: App information and support

#### Display Information
```
┌─────────────────────────────────────┐
│ VoiceInsight                        │
│ Version: 1.0.0                      │
│ Build: 2026.024                     │
│                                     │
│ [Check for Updates]                 │
│ [View Release Notes]                │
│ [Privacy Policy]                    │
│ [Terms of Service]                  │
│ [Send Feedback]                     │
│ [Report a Bug]                      │
│ [API Documentation]                 │
└─────────────────────────────────────┘
```

---

## 2. Settings Screen Layout

```
Settings
╔═════════════════════════════════════╗
║ ◄ Back                        ⚙️   ║
╠═════════════════════════════════════╣
║ AI & Language Processing            ║
║   Transcription Provider  [OpenAI]  ║
║   Language                [Auto]    ║
║   Summary AI Model        [GPT-4]   ║
║   Summary Length          [Standard]║
║   Key Points Count        [5-8]     ║
║                                     ║
║ API Keys & Credentials              ║
║   OpenAI Key              [Set] ▶   ║
║   Anthropic Key           [Set] ▶   ║
║   Google Cloud            [Set] ▶   ║
║                                     ║
║ Recording Preferences               ║
║   Quality                 [High] ▶  ║
║   Format                  [WAV] ▶   ║
║   Silence Detection       [On] ⚪   ║
║                                     ║
║ Playback & Display                  ║
║   Default Speed           [1x] ▶    ║
║   Font Size               [Med] ▶   ║
║   Show Timestamps         [On] ⚪   ║
║                                     ║
║ Data & Privacy                      ║
║   Auto-Delete             [Never]   ║
║   Storage Location        [Local]   ║
║   Analytics               [Off] ⚪  ║
║                                     ║
║ Export & Backup                     ║
║   Export Format           [TXT] ▶   ║
║   Auto Backup             [Weekly]  ║
║                                     ║
║ About & Help                        ║
║   Version 1.0.0                     ║
║   [Check Updates]                   ║
║                                     ║
╚═════════════════════════════════════╝
```

---

## 3. Settings File Structure

### Settings Data Model
```javascript
{
  // AI Configuration
  transcription: {
    provider: "openai" | "google" | "anthropic" | "assemblyai",
    language: "auto" | "en-US" | "es-ES" | "fr-FR" | ...,
    apiKey: "sk-...",
    apiEndpoint: "https://api.openai.com/v1"
  },

  summarization: {
    provider: "openai" | "anthropic" | "google",
    model: "gpt-4" | "gpt-3.5-turbo" | "claude-3-opus" | "gemini-pro",
    apiKey: "sk-..." | "sk-ant-...",
    detailLevel: "brief" | "standard" | "detailed",
    keyPointsCount: 5 | 8 | 12
  },

  // Recording Preferences
  recording: {
    quality: 8000 | 16000 | 44100 | 48000, // Hz
    format: "wav" | "mp3" | "webm" | "ogg",
    silenceDetection: true,
    silenceThreshold: -40 // dB
  },

  // Playback Settings
  playback: {
    defaultSpeed: 0.75 | 1 | 1.25 | 1.5,
    fontSizeTranscript: "small" | "medium" | "large" | "xl",
    showTimestamps: true,
    autoScroll: false,
    highlightSpeaker: true,
    showConfidence: false
  },

  // Privacy & Data
  privacy: {
    autoDeleteDays: null | 30 | 90 | 365,
    storageLocation: "local" | "cloud" | "hybrid",
    analyticsEnabled: false,
    crashReporting: false
  },

  // Export & Backup
  export: {
    defaultFormat: "txt" | "pdf" | "markdown" | "json" | "docx",
    autoBackup: "disabled" | "daily" | "weekly" | "monthly",
    backupService: "google-drive" | "dropbox" | "aws-s3"
  },

  // Notifications
  notifications: {
    recordingStart: true,
    processingComplete: true,
    uploadFailed: true,
    dailySummary: false
  }
}
```

---

## 4. Settings Screen Component (HTML)

```html
<!-- Tab-based approach for organization -->
<div id="settings-tabs">
  <button class="tab-btn active" onclick="showTab('ai')">AI</button>
  <button class="tab-btn" onclick="showTab('recording')">Recording</button>
  <button class="tab-btn" onclick="showTab('playback')">Playback</button>
  <button class="tab-btn" onclick="showTab('privacy')">Privacy</button>
  <button class="tab-btn" onclick="showTab('about')">About</button>
</div>

<div id="ai-tab" class="tab-content active">
  <!-- AI settings here -->
</div>

<div id="recording-tab" class="tab-content">
  <!-- Recording settings here -->
</div>

<!-- etc... -->
```

---

## 5. Validation & Error Handling

### API Key Validation
```javascript
async function validateApiKey(provider, apiKey) {
  try {
    if (provider === 'openai') {
      const response = await fetch('https://api.openai.com/v1/models', {
        headers: { 'Authorization': `Bearer ${apiKey}` }
      })
      return response.ok
    }
    // Similar for other providers
  } catch (error) {
    return false
  }
}

// Show validation feedback
if (isValid) {
  showSuccess("API Key verified ✓")
} else {
  showError("Invalid API Key - please check and try again")
}
```

### Settings Persistence
```javascript
// Save settings to localStorage
function saveSettings(settings) {
  localStorage.setItem('voiceinsight_settings',
    JSON.stringify(encryptSensitiveData(settings))
  )
}

// Load settings on app start
function loadSettings() {
  const stored = localStorage.getItem('voiceinsight_settings')
  return stored ? JSON.parse(decryptSensitiveData(stored)) : getDefaultSettings()
}
```

---

## 6. Recommended Default Settings

```javascript
const DEFAULT_SETTINGS = {
  transcription: {
    provider: "openai",
    language: "auto"
  },
  summarization: {
    provider: "openai",
    model: "gpt-3.5-turbo", // cheaper/faster option
    detailLevel: "standard",
    keyPointsCount: 5
  },
  recording: {
    quality: 44100,
    format: "wav",
    silenceDetection: false
  },
  playback: {
    defaultSpeed: 1,
    fontSizeTranscript: "medium",
    showTimestamps: true,
    autoScroll: false
  },
  privacy: {
    autoDeleteDays: null,
    storageLocation: "local"
  },
  export: {
    defaultFormat: "txt"
  },
  notifications: {
    recordingStart: true,
    processingComplete: true
  }
}
```

---

## 7. UI Flow for API Key Setup

```
Dashboard
  ↓
Settings (FAB or menu)
  ↓
AI Tab
  ↓
Select Provider (OpenAI / Anthropic / Google)
  ↓
[Enter API Key] input
  ↓
[Test Connection] button
  ↓
✓ Success message (or error)
  ↓
Save & Return to Dashboard
```

---

## 8. Security Best Practices

✅ **DO**:
- Store API keys in encrypted localStorage
- Validate API keys before saving
- Never log API keys in console
- Use HTTPS for all API calls
- Show only last 4 characters of key
- Provide copy-to-clipboard functionality

❌ **DON'T**:
- Send API keys to your own server (in POC)
- Store API keys in plain text
- Display full API key in UI
- Log API keys in error messages
- Allow API key to be shared via export

---

## 9. Mobile Responsiveness

All settings inputs should:
- Have large touch targets (44px minimum)
- Support mobile keyboards
- Use dropdowns/pickers for selection
- Display validation inline
- Show help text clearly

---

*VoiceInsight Settings Specification v1.0 · February 2026*
