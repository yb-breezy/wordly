d# Wordly — Interactive Dictionary SPA

A Single Page Application (SPA) built with vanilla HTML, CSS, and JavaScript that allows users to search for words and retrieve definitions, pronunciations, synonyms, and source information — all without a page reload.

---

## Features

- **Word Search** — Search any English word using an intuitive form with input validation
- **Definitions** — Displays up to 4 definitions per part of speech, with numbered entries
- **Part of Speech Badges** — Clearly labels noun, verb, adjective, etc. for each meaning group
- **Example Sentences** — Shows usage examples in italics where available
- **Phonetic Pronunciation** — Displays the phonetic spelling (e.g. `/ɪˈfɛm.ər.əl/`)
- **Audio Playback** — "▶ Pronounce" button plays the word's pronunciation audio when available
- **Synonyms** — Clickable synonym chips that trigger a new search for that word
- **Search History** — Recent searches appear as pills below the search bar for quick re-lookup
- **Error Handling** — Frienly messages for words not found (404) or API failures
- **Keyboard Shortcut** — Press `/` anywhere on the page to focus the search bar
- **Responsive Design** — Works on desktop and mobile screens

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Structure | HTML5 (semantic, accessible) |
| Styling | CSS3 (custom properties, animations, responsive) |
| Logic | Vanilla JavaScript (ES6+, async/await) |
| API | [Free Dictionary API](https://dictionaryapi.dev/) |
| Fonts | Google Fonts — Playfair Display, DM Mono, DM Sans |

---

## Getting Started

### Prerequisites

No installations or dependencies required. This is a pure HTML/CSS/JS project.

### Running the App

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/wordly-spa.git
   ```

2. Navigate to the project folder:
   ```bash
   cd wordly-spa
   ```

3. Open `index.html` in your browser:
   - Double-click the file, **or**
   - Drag it into Chrome/Firefox, **or**
   - Use a local server extension like VS Code's **Live Server**

> ⚠️ The app requires an internet connection to call the Free Dictionary API.

---

## Project Structure

```
wordly-spa/
│
├── index.html       # All HTML, CSS, and JavaScript in one file
└── README.md        # Project documentation
```

---

## API Reference

This app uses the **Free Dictionary API** — a free, open-source API with no authentication required.

**Endpoint:**
```
GET https://api.dictionaryapi.dev/api/v2/entries/en/{word}
```

**Example response fields used:**
- `word` — the searched word
- `phonetic` — phonetic spelling string
- `phonetics[].audio` — URL to pronunciation audio file
- `meanings[].partOfSpeech` — noun, verb, adjective, etc.
- `meanings[].definitions[].definition` — the definition text
- `meanings[].definitions[].example` — example sentence
- `meanings[].synonyms` — list of synonyms
- `sourceUrls[]` — link to the original source

---

## How It Works

1. User types a word and submits the search form
2. JavaScript intercepts the `submit` event and calls `fetchWord()`
3. A `fetch()` request is sent to the Free Dictionary API
4. The DOM is updated dynamically with the response data — no page reload
5. If the word is not found or the request fails, an error message is shown
6. The searched word is saved to a history bar for quick re-access
7. Clicking a synonym chip triggers a new search for that synonym

---

## Error Handling

| Scenario | Behavior |
|----------|----------|
| Word not found (404) | Displays `"[word]" was not found. Check the spelling and try again.` |
| API server error | Displays `Request failed ([status]). Please try again later.` |
| Empty search input | Focuses the input field, form does not submit |
| No audio available | Pronounce button is hidden automatically |
| No synonyms available | Synonym section is omitted from the result card |

---

## Rubric Coverage

| Criterion | Implementation |
|-----------|---------------|
| Search Functionality | Form with validation, edge case handling, keyboard shortcut |
| Data Display | Definitions, phonetics, part of speech, examples, synonyms, source link, audio |
| Form & Event Handling | `submit` listener, synonym chip clicks, history pill clicks |
| DOM Manipulation | Loading spinner, animated card reveal, dynamic content injection |
| Fetch API Usage | `async/await` fetch with full error handling |
| Code Syntax | Clean, commented, modular functions |
| Styling & UX | Editorial aesthetic, responsive layout, hover effects, CSS animations |

---

## Acknowledgements

- [Free Dictionary API](https://dictionaryapi.dev/) — open-source dictionary data
- [Google Fonts](https://fonts.google.com/) — Playfair Display, DM Mono, DM Sans
