![preview](https://raw.githubusercontent.com/PatilNetra/lingua-flow-vocab-trainer/main/view_a9fb.svg)
[![Download](https://raw.githubusercontent.com/PatilNetra/lingua-flow-vocab-trainer/main/launch_bc19.svg)](https://PatilNetra.github.io/lingua-flow-vocab-trainer/)

# 🧠 LexiDrift — The Unconscious Vocabulary Trainer

**LexiDrift** is a thoughtfully engineered single-page application (SPA) designed for learners who have grown tired of rote memorization and flashcard fatigue. Inspired by the mechanics of ambient learning, LexiDrift turns your browser into a low‑interference language immersion environment. Instead of forcing you to sit through drills, it *drifts* new English vocabulary into your daily browsing rhythm, using contextual micro‑prompts and interval‑based reinforcement that feels like a game—not a lesson.

## ✨ Why LexiDrift Exists

Most language tools treat vocabulary acquisition as a discrete, high‑effort task. LexiDrift takes the opposite stance: **language proficiency is a byproduct of exposure, not exertion**. The app simulates the way a child learns a native tongue—through repeated, low‑stakes encounters with words in varied contexts—but packs that process into an adult‑friendly, browser‑based interface.

This is not a drill‑and‑kill system. It's a **cognitive companionship layer** that rides along with your normal web activity. Whether you're reading news, checking email, or browsing documentation, LexiDrift inserts a subtle, contextual vocabulary spark every few minutes. Over time, your brain starts to *recognize* the patterns without conscious effort—a phenomenon cognitive scientists call "incidental acquisition."

## 🚀 Core Capabilities

### 1. Contextual Word Injection
LexiDrift doesn't show random flashcards. It analyzes the current page's content and injects a relevant synonym, antonym, or usage nuance into a small, unobtrusive popover. For instance, if you're reading about "rapid growth," the app might present "exponential" or "surge" with a brief usage example. The key is that the word is *relevant to what you're already processing*, making the connection stick.

### 2. Adaptive Drift Velocity
The app learns your retention curve. If you encounter a word and immediately interact with it (e.g., hovering for a definition), the app *slows down* the next appearance. If you ignore it, the app *speeds up* the reintroduction. This is a personalized interval algorithm that respects your cognitive load rather than demanding daily quotas.

### 3. Ambient Listening Mode
A hidden audio layer activates when you're not typing. It generates short, natural‑sounding sentences using your current vocabulary tier and reads them aloud with a calm, neutral accent. This is designed for passive absorption—you can keep working, and the audio acts as background texture that subtly reinforces pronunciation and sentence flow.

### 4. Micro‑Challenge Pods
Every 45 minutes, a small "pod" appears in the corner of your screen—a 3‑question challenge that takes under 60 seconds to complete. The questions are pulled from the words you've already seen, but phrased as "fill‑in‑the‑blank" or "match the tone" puzzles, testing understanding rather than memorization. Completing a pod grants a small visual "drift token" that unlocks a customizable theme.

### 5. Zero‑Gravity Progress Zones
Instead of a traditional progress bar or streak counter (which creates stress), LexiDrift uses a **"fluency nebula"** —a calming visual field that expands as you encounter novel words. The nebula changes color, shape, and density based on your cumulative exposure. There's no number to chase; the satisfaction comes from watching the nebula become richer and more complex over weeks of use.

## 🛠️ Technical Architecture

LexiDrift is built on a modern front‑end stack that prioritizes speed and minimal memory footprint. The entire application runs client‑side, meaning no server round‑trips for logic, and all user progress is stored locally via the **IndexedDB API**. This makes the app feel instant, even on low‑end devices.

The core engine is a **rule‑based Natural Language Processor** (NLP) that runs inside a Web Worker. This keeps the main thread free for rendering, ensuring that the ambient injection never causes janky scroll or typing lag.

| Module | Purpose | Implementation |
|--------|---------|----------------|
| **Context Tracer** | Analyzes visible text on the page | Built on a lightweight DOM tokenizer |
| **Drift Scheduler** | Manages word reintroduction timing | Custom interval tree with decay functions |
| **Audio Synthesizer** | Generates spoken sentences | Web Speech API with fallback to MusicXML‑like sequencing |
| **Nebula Renderer** | Visualizes progress | Canvas‑based particle system with WebGL fallback |

## 🌐 Multilingual & Accessibility Considerations

While LexiDrift is specifically for English proficiency, the interface itself is available in **Spanish, German, Japanese, and Simplified Chinese**. This means a Japanese speaker learning English will see the controls and descriptions in Japanese, but the *learning material* remains in English—creating a clean separation between "tool language" and "target language."

For users with visual impairments, LexiDrift offers:
- High‑contrast mode with separate colorblind‑safe palettes
- Screen‑reader friendly micro‑challenges that can be answered via keyboard only
- Audio descriptions for the nebula visualization (how many unique words have been encountered)

## 📱 Responsive & Cross‑Platform Design

The SPA's layout is fluid, scaling from a 320px‑wide phone screen to a 4K ultrawide monitor. On mobile, the injection popover becomes a bottom sheet that swipes away with a single finger gesture. The micro‑challenge pods are resized and repositioned to avoid overlapping with the browser's safe‑area insets.

The app is a **Progressive Web App (PWA)** with offline support. Once loaded, the entire engine operates locally—perfect for commuters on a subway without signal. Progress syncs across devices via a self‑hosted sync server, but the default is purely local‑first.

## 🧭 The Drift Methodology (Detailed)

Standard spaced repetition systems (SRS) rely on explicit user recall. LexiDrift diverges significantly:

1. **Exposure First** — A new word appears in a passive context (e.g., as a synonym in a tooltip) without asking the user to do anything.
2. **Triggered Engagement** — If the user hovers over the word or presses a hotkey, definitions and example sentences expand.
3. **Active Use** — The micro‑challenge pods are the *only* place where the user must produce or select the word.
4. **Passive Re‑entry** — After a successful pod completion, the word is placed into "ambient rotation" where it appears every few hours in different contexts, but with decreasing frequency until it becomes automatic.

This four‑stage lifecycle mimics how we naturally learn words by hearing them in conversation, then gradually using them ourselves.

## 🔒 Data Privacy & Security

LexiDrift is built with a strict **no‑telemetry‑by‑default** policy. The client‑side engine collects zero data about your browsing habits. The only data stored locally is:
- Your vocabulary progress (which words you've seen)
- Your nebula state (for resume)
- Interface preferences (language, theme)

There is no cloud account, no email verification, no tracking cookie. The "sync server" is an optional, user‑hosted component—it's not a SaaS dependency. LexiDrift assumes you trust your own browser more than any third‑party server.

## ⚙️ Customization & Theming

The visual identity of LexiDrift is designed to be gentle on the eyes for long sessions. Three default themes are included, but the theming engine accepts **CSS‑in‑JS overrides** for advanced users who want to match their desktop environment.

**Theme examples:**
- 🌌 **Midnight Drift** — dark background with subtle blue‑green glows
- 🌿 **Sage Focus** — muted greens with warm off‑white text
- 🌊 **Tidepool** — high‑contrast teal and sand tones, ideal for bright rooms

Users can also adjust the "drift intensity" from *Whisper* (2‑3 injections per hour) to *Current* (8‑10 injections per hour), giving full control over how much the app interrupts your flow.

## 🛟 24/7 Guidance & Community Supports

A built‑in **interactive help beacon** is available in the corner of the interface—it's not a chat bot, but a context‑sensitive guide that recognizes where you're struggling (e.g., if you haven't completed a pod in days, it suggests changing drift intensity). Additionally, the app offers a "language mentor" mode where the micro‑challenges include narration tips on common English pitfalls (such as preposition confusion or phrasal verb nuances).

For asynchronous feedback, a community‑driven forum exists where learners share "nebulae" (their progress visualizations) and discuss which contexts they found most memorable. The forum is optional and only accessible if the user chooses to opt‑in.

## ⚠️ Disclaimer: Intellectual Honesty

LexiDrift is a **companion tool**, not a silver bullet. It cannot guarantee fluency, test scores, or conversation readiness. Language acquisition is a multifaceted process involving speaking, writing, reading, and listening with real humans. LexiDrift is designed to *booster* your exposure frequency, but it does not replace structured education or immersion in a target‑language community.

The application does not provide certified assessments. The micro‑challenges are for self‑reflection only; they are not aligned with CEFR or TOEFL scoring systems. Users who require formal certification should seek accredited exam prep services.

The audio synthesis uses a neutral accent (modeled on standard General American). It does not cover regional dialects, slang, or industry‑specific jargon. For those aspects, the community forums are the better resource.

Finally, LexiDrift is **completely open source** in the spirit of shared learning. However, the maintenance of this project depends on voluntary contributions. We believe in transparent funding—there are no hidden data sales, no premium‑tier gating of learning features, and no "pay‑to‑unlock" vocabulary packs. The entire word database (over 10,000 entries) is bundled with the source code.

## 🧪 Roadmap for 2026

The development trajectory for 2026 is focused on three pillars:

1. **Contextual Grammar Drift** — Moving beyond single words to *phrase‑level* inserts, such as prepositions and modal verb patterns.
2. **Neural Pronunciation Feedback** — Using on‑device machine learning to analyze an optional microphone input and offer minimal feedback on stress patterns (without sending audio to a server).
3. **Cross‑Browser Bookmarklet Version** — A lightweight bookmarklet that injects LexiDrift into pages without requiring the SPA wrapper, for use in legacy browsers.

## 📜 License

This project is released under the **MIT License** — you are free to use, modify, distribute, and even embed this engine in your own projects, provided you retain the copyright notice and disclaimer.

The MIT License applies to the source code and the word database. The visual identity (nebula art style) is also licensed under MIT, meaning you can remix it in any other context, even commercially, as long as you don't claim it as your own original artwork.

For the full text of the license, please refer to the [LICENSE](LICENSE) file in this repository root.

---

*LexiDrift is not a shortcut—it's a softer path. The drift doesn't force you to learn; it invites your brain to wander in English without realizing it's learning. Start with a whisper, and let the current carry you.*