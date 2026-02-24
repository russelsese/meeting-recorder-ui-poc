# VoiceInsight — UI Proof of Concept

A mobile-first HTML proof-of-concept for **VoiceInsight**, an AI-powered voice recording application that enables users to record meetings, lectures, and conversations with automatic transcription, summarization, and key point extraction.

## Live Demo

**View the live demo:** https://russelsese.github.io/meeting-recorder-ui-poc/

Or open `index.html` in your browser locally to navigate through all screens:

```bash
# Open the POC navigator
open index.html   # macOS
start index.html  # Windows
```

> Open on a mobile device or use your browser's DevTools to emulate a mobile screen (390px width recommended) for the best experience.

---

## Screens

| Screen | File | Description |
|--------|------|-------------|
| POC Navigator | `index.html` | Jump between all screens from one place |
| Dashboard | `dashboard.html` | Home screen with recent recordings and quick record button |
| Voice Recording | `recording.html` | Record audio with timer, waveform visualization, and controls |
| Recording Details | `recording-detail.html` | View recording with audio player and AI features (Transcript, Summary, Key Points) |
| Activity Calendar | `calendar.html` | 7-day recording history organized by date |

---

## User Flow

```
Dashboard (Home)
  ├── Record Button (FAB)
  │     └── Recording Screen
  │           └── Recording Details
  │                 ├── Transcript
  │                 ├── Summary
  │                 └── Key Points
  │
  └── Calendar
        └── Recording Details
```

---

## Features

### Recording Capabilities
- 🎙️ **Record Audio** — Tap the floating record button to start capturing
- ⏱️ **Real-time Timer** — MM:SS format with live updates
- 📊 **Waveform Visualization** — Animated bars showing audio levels during recording
- ⏸️ **Pause/Resume** — Pause recording and resume later
- 📝 **Auto-Generated Titles** — Automatically names recordings by date/time or customize manually

### AI Features (Mock Data)
- 📝 **Transcription** — Full text with speaker labels and timestamps
- 📄 **Summarization** — AI-generated 2-3 paragraph summary
- ✅ **Key Points** — Extracted main takeaways and action items
- 🏷️ **Action Items** — Highlighted tasks to complete

### Playback & Analysis
- 🎵 **Audio Player** — Play/pause, progress bar, time display
- 🔊 **Playback Speed** — 0.75x, 1x, 1.25x, 1.5x options
- 📋 **Searchable Content** — Copy transcripts and summaries
- 📅 **Activity Calendar** — Browse last 7 days of recordings
- ⬆️ **Export & Share** — Share recordings and export content

---

## Tech Stack

- Plain HTML, CSS, and vanilla JavaScript — no build step required
- [Tailwind CSS](https://tailwindcss.com/) via CDN for utility styling
- Native browser APIs: `MediaRecorder`, `AudioContext`, `FileReader`, `Web Audio API`

---

## Running Locally

No build step or server required. Simply open `index.html` in a browser:

```bash
# Clone/download the repo
cd meeting-recorder-ui-poc

# Open in browser (macOS)
open index.html

# Or open in browser (Windows)
start index.html
```

Or use a simple local server for the best results:

```bash
# Using Python 3
python3 -m http.server 8000

# Using Node/npx
npx serve .

# Then open http://localhost:8000 or http://localhost:3000
```

---

## POC Scope & Limitations

This is a static HTML prototype with mock data. The following will require real implementation in production:

| Feature | POC Behaviour | Production Requirement |
|---------|---------------|------------------------|
| Audio Recording | FileReader API with mock audio | Native `MediaRecorder` API with real audio blob |
| Transcription | Hardcoded mock transcript | OpenAI Whisper or Google Cloud Speech-to-Text API |
| Summarization | Mock text | OpenAI GPT-4 or similar LLM |
| Key Points | Static list | AI extraction from transcript |
| Data Storage | SessionStorage (lost on reload) | IndexedDB, Firebase, or backend API |
| Playback | Audio HTML element ready | Web Audio API visualization |
| User Auth | None (POC) | OAuth or JWT authentication |
| Cloud Storage | None | S3, Firebase Storage, or DigitalOcean Spaces |

See [docs/requirements.md](docs/requirements.md) for the full specification.

---

## File Structure

```
meeting-recorder-ui-poc/
├── index.html                    ← POC Navigator (jump between screens)
├── dashboard.html                ← Screen 1: Home with recent recordings
├── recording.html                ← Screen 2: Voice capture & controls
├── recording-detail.html         ← Screen 3: Transcript/Summary/Key Points
├── calendar.html                 ← Screen 4: 7-day recording history
├── VOICE_APP_PLAN.md             ← Implementation plan
└── docs/
    └── requirements.md           ← Full app specifications
```

---

## Key Components

### Dashboard
- Quick stats (recording count, total duration)
- Large "Record" button (FAB with pulse animation)
- Recent recordings list with previews
- Quick access to calendar

### Recording Screen
- Large red record button with recording state indicator
- Real-time timer (MM:SS)
- Animated waveform visualization
- Record/Pause/Resume/Stop controls
- Title input for custom naming
- Discard/Save options

### Recording Details
- **Audio Player**: Play/pause, progress bar, speed control
- **3 Analysis Tabs**:
  - **Transcript**: Full text with timestamps and speaker labels
  - **Summary**: AI-generated overview (2-3 paragraphs)
  - **Key Points**: Extracted takeaways and action items
- **Actions**: Edit title, share, delete, export

### Calendar
- 7-day view of all recordings
- Organized by date (Today, Yesterday, etc.)
- Shows recording title, duration, key points count
- Empty state for days with no recordings
- Click any recording to view details

---

## Color System

| Name | Hex | Usage |
|------|-----|-------|
| Brand 50 | `#f0f4ff` | Light backgrounds |
| Brand 100 | `#dce8ff` | Highlights |
| Brand 500 | `#4169e1` | Primary buttons & accents |
| Brand 600 | `#3457c8` | Gradients & hover states |
| Red 500 | `#ef4444` | Recording active state |
| Gray 50-800 | See specs | Text & borders |

---

## Browser Support

- iOS Safari 12+
- Chrome Mobile (Android 6+)
- Edge Mobile

---

## Next Steps (Optional Enhancements)

1. **Real Web Audio API**
   - Actual microphone recording
   - Real audio blob creation
   - Waveform visualization from audio context

2. **AI Integration**
   - Connect OpenAI Whisper for transcription
   - Use GPT-4 for summarization
   - Real-time processing indicators

3. **Data Persistence**
   - IndexedDB for local storage
   - Cloud backend integration
   - User authentication

4. **Advanced Features**
   - Speaker identification
   - Search across recordings
   - Export to PDF/TXT
   - Recording editing
   - Collaboration & sharing

---

*VoiceInsight v1.0 POC · February 2026*
