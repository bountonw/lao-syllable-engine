# Lao Syllable Engine

> ⚠️ This project is in its early stages. The goal is to develop a rule-based Lao syllable segmentation
> engine that can support text segmentation, typesetting, spellchecking, and other NLP applications.
> The outline below represents a planned framework for syllable classification based on phonotactic
> structure, vowel behavior, and consonant clustering. It does not yet reflect a complete implementation
> and will continue to evolve.

## Overview

A linguistically accurate Lao syllable segmentation engine. This library parses unsegmented Lao text into valid syllables using rule-based phonotactic logic, with optional dictionary enhancement. It is designed to be modular, portable, and embeddable in larger pipelines for typesetting, spellchecking, translation, and natural language processing (NLP).

---

## 🔍 Purpose

Lao does not use spaces between words. To break lines correctly or process text linguistically, software must recognize **legal syllable boundaries**. This engine:

* Validates individual syllables using character-level phonotactic rules
# Lao Syllable Engine

A linguistically accurate Lao syllable segmentation engine. This library parses unsegmented Lao text into valid syllables using rule-based phonotactic logic, with optional dictionary enhancement. It is designed to be modular, portable, and embeddable in larger pipelines for typesetting, spellchecking, translation, and natural language processing (NLP).

---

## 🔍 Purpose

Lao does not use spaces between words. To break lines correctly or process text linguistically, software must recognize **legal syllable boundaries**. This engine:

* Validates individual syllables using character-level phonotactic rules
* Segments strings into syllables using longest-match-first logic
* Supports real-world edge cases (clusters, tonal forms, AM, short vowels, etc.)
* Can be used for word segmentation, typesetting, and spellchecking

---

## 📦 Features

* Accurate syllable validation
* Rule-based engine (not regex spaghetti)
* Optional dictionary-based lookup for maximal matching
* Designed in Python for performance and future Elixir porting
* Modular 

---

## 📂 Project Structure

```
lao-syllable-engine/
├── py/
│   └── syllable_engine/
│       ├── validate.py
│       └── ...
├── elixir/
├── rust/
├── docs/                     # ← Human-readable rule documentation
│   ├── syllable_structure.md
│   ├── cluster_rules.md
│   └── vowel_system.md
├── data/                     # ← Machine-readable language files
│   ├── lao_syllables.txt
│   ├── lao_dictionary.tsv
│   ├── fallback_rules.json
│   └── segmentation_tests.txt
├── README.md
├── LICENSE
```

---

## 🚀 Usage (Python)

```python
from syllable_engine import segment, validate

syllables = segment("\u0e84\u0ebb\u0ab9\u0ea5\u0eb2\u0ea7\u0ea1\u0eb1\u0e81\u0ead\u0ec8\u0eb2\u0ab9\u0ebb\u0ec8")
# → ['ຄົહ', 'ລາວ', 'ມັກ', 'ອ່າહ', 'ົ່']

is_valid = validate("\u0e97\u0eb3")  # → True
```

---

## 📚 Goals

* 💡 Provide a standalone, linguistically grounded Lao syllable parser
* ⚡ Port to Elixir for scalable, high-performance use
* 💪 Serve as a foundation for spellcheckers, NLP tools, and TeXLive enhancements
* ↻ Integrate into Markdown → PDF/HTML/EPUB/LaTeX pipelines

---

## 🤝 Contributing

We welcome linguists, developers, and native Lao speakers interested in improving syllable parsing, dictionary accuracy, or rule refinement. See `tests/` for guidance.

---

## 📜 License

MIT — free for personal, academic, and commercial use.
* Segments strings into syllables using longest-match-first logic
* Supports real-world edge cases (clusters, tonal forms, AM, short vowels, etc.)
* Can be used for word segmentation, typesetting, and spellchecking

---

## 📦 Features

* Accurate syllable validation (ຄົહ, ກະ, ທຳ, จະ, ເຫົ້າ)
* Rule-based engine (not regex spaghetti)
* Optional dictionary-based lookup for maximal matching
* Designed for performance and future Elixir porting
* Modular — can be called from Markdown → TeX, HTML, EPUB, DOCX, etc.

---

## 📂 Project Structure

```
syllable_engine/
├── __init__.py
├── segment.py         # longest-match-first segmentation logic
├── validate.py        # is_valid_syllable(), rule enforcement
├── constants.py       # V_PRE_SET, C_BASE_SET, clusters, tone marks, etc.
├── rules.py           # phonotactic model (syllable types)
└── tests/
    └── test_engine.py
```

---

## 🚀 Usage (Python)

```python
from syllable_engine import segment, validate

syllables = segment("\u0e84\u0ebb\u0ab9\u0ea5\u0eb2\u0ea7\u0ea1\u0eb1\u0e81\u0ead\u0ec8\u0eb2\u0ab9\u0ebb\u0ec8")
# → ['ຄົહ', 'ລາວ', 'ມັກ', 'ອ່າહ', 'ົ່']

is_valid = validate("\u0e97\u0eb3")  # → True
```

---

## 📚 Goals

* 💡 Provide a standalone, linguistically grounded Lao syllable parser
* ⚡ Port to Elixir for scalable, high-performance use
* 💪 Serve as a foundation for spellcheckers, NLP tools, and TeXLive enhancements
* ↻ Integrate into Markdown → PDF/HTML/EPUB/LaTeX pipelines

---

## 🤝 Contributing

We welcome linguists, developers, and native Lao speakers interested in improving syllable parsing, dictionary accuracy, or rule refinement. See `tests/` for guidance.

---

## 📜 License

MIT — free for personal, academic, and commercial use.

