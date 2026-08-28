# Advanced Text Analyzer

A powerful, feature-rich web-based text analysis tool that works with multiple writing systems and alphabets. Analyze text for character and word frequency, reading time, and other useful metrics.

## Features

- **Multi-language Support**: Analyze text in various writing systems including:
  - Latin (English, Spanish, French, etc.)
  - Cyrillic (Russian, Ukrainian, etc.)
  - Chinese, Japanese, Korean
  - Arabic and Hebrew (right-to-left scripts)
  - Devanagari (Hindi, Sanskrit)
  - Greek, Thai, and others

- **Comprehensive Text Analysis**:
  - Character count (with and without spaces)
  - Word count and unique words
  - Sentence and paragraph detection
  - Average word length
  - Estimated reading time
  - Word frequency analysis
  - Character distribution statistics

- **Advanced Sorting Options**:
  - Sort words alphabetically (A-Z or Z-A)
  - Sort by frequency (most common or least common)
  - Sort by word length (longest or shortest)
  - Toggle between ascending and descending order

- **Data Export**:
  - Export all analysis results to CSV
  - Timestamped filenames for easy reference
  - Includes comprehensive statistics and frequency data
  - UTF-8 BOM included so Excel renders non-Latin scripts correctly
  - Formula-injection guard for cells starting with `=`, `+`, `-`, `@`

- **Visual Themes**:
  - Light and dark mode support
  - User preference saved between visits
  - Modern, clean interface with responsive design

- **Accessibility & UX**:
  - Full keyboard support (tabs and sortable columns via Enter/Space, `Ctrl+Enter` to analyze)
  - `aria` attributes, `aria-sort` on columns, and RTL layout for Arabic/Hebrew
  - No artificial row limit on the frequency table (all unique words shown)
  - Code-point aware counting: emoji and astral-plane characters count once
  - Sample text loader and one-click clear

## How to Use

1. Select the language/writing system of your text
2. Enter or paste your text in the input field
3. Click "Analyze Text" to generate statistics
4. Use the sorting buttons to organize word frequency data
5. Download a CSV export with the "Save to CSV" button
6. Toggle between light and dark mode with the theme button

## Technical Information

This tool runs entirely in your browser - no server processing is required, ensuring your text remains private. The analyzer uses modern JavaScript to process text and perform statistical analysis based on the selected language system.

Language detection algorithms are tailored to handle different writing systems appropriately, including languages without clear word boundaries like Chinese and Japanese.

## Development

This project is open source and hosted on GitHub. Contributions, bug reports, and feature requests are welcome.

### Recent Updates

- Removed the 50-row limit on the word frequency table; all unique words are rendered (2026-08-28)
- Fixed XSS: table rows are built with `textContent` instead of `innerHTML` (2026-08-28)
- Code-point aware character counting (emoji and astral characters count once) (2026-08-28)
- Unicode-aware tokenizer: keeps `don't` and `well-known` together, strips surrounding punctuation (2026-08-28)
- Consistent percentage denominators across word frequency and character distribution (2026-08-28)
- CSV export now uses a Blob with UTF-8 BOM and guards against spreadsheet formula injection (2026-08-28)
- Language-aware reading time (words/min for spaced scripts, chars/min for CJK/Thai) (2026-08-28)
- Proper collation per language when sorting (locale-aware `localeCompare`) (2026-08-28)
- RTL layout automatically enabled for Arabic and Hebrew (2026-08-28)
- Keyboard accessibility: tabs, sortable headers, `Ctrl+Enter` to analyze, `aria-sort` (2026-08-28)
- Empty-file uploads are rejected instead of producing bogus stats (2026-08-28)
- Added Load Sample / Clear buttons (2026-08-28)
- Added dark mode support (2025-04-05)
- Implemented multi-language support for various writing systems
- Added bidirectional sorting capabilities (ascending/descending)
- Enhanced CSV export with comprehensive data
- Improved word frequency table with additional metrics

## License

MIT License - Feel free to use, modify, and distribute this code.
