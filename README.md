# AI-Glossary
AI Glossary list that grows and updates as per industry.
From the Turing Test to Model Context Protocol — every era of AI, explained at your level.

The AI Glossary is a browser-based reference tool covering 60 terms across 70+ years of AI history — with every definition written twice: once for beginners, once for practitioners. No jargon walls. No assuming you already know what a Transformer is.

No install. No API. Just open the file.

Why This Exists

Most AI glossaries are written for one audience — either too simplified to be useful, or too technical for anyone who didn't already know the terms. This one switches on demand.

Every entry has:

A plain-English definition — no assumed knowledge
A technical definition — for practitioners who want precision
A real-world example — grounding the concept in something concrete
An era tag — so you know when this idea emerged
A category tag — so you can filter by topic
A difficulty dot — beginner, practitioner, or expert at a glance
Features
Two-mode toggle — switch between Beginner and Practitioner+ definitions for every card simultaneously
Live search — filters cards as you type, matching against term name and both definition layers
Auto-narrowing filters — when a search matches terms in only one era or category, those filters set themselves automatically; cleared when the search box is empty
Era filter — browse by historical period (Foundations → Agentic Era)
Category filter — filter by topic (Core Concepts, Architectures, Safety, Infrastructure, etc.)
Live result count — shows how many terms are visible out of the total, with a note when filters were auto-set
Empty state with personality — six witty, on-theme messages when no results match (randomly picked at transition, not on every keystroke)
Clear search & filters button — resets everything and returns focus to the search input
Card hover lift — subtle translateY(-2px) + border accent on hover
Mobile responsive — filter row stacks vertically at 600px
Content Coverage

60 terms across 7 eras — a sample preview of 400+ planned entries.

Era	Period	Example Terms
Foundations	1950s–1980s	Turing Test, Perceptron, Expert System
ML Rise	1980s–2000s	Supervised Learning, Backpropagation, Overfitting
Deep Learning	2006–2016	CNN, GPU Acceleration, Transfer Learning
Transformer Era	2017–2021	Transformer, Attention Mechanism, BERT, GPT
GenAI Boom	2022–2024	Hallucination, RAG, RLHF, Context Window
Agentic Era	2024–2026	MCP, Tool Use, Reasoning Model, Multi-Agent
Cross-cutting	—	Alignment, AI Safety, Prompt, Token, API

Categories covered: Core Concepts · Architectures · Training Methods · Models · Techniques · Infrastructure · Safety · Limitations · Usage

Difficulty levels:

🟢 Beginner — no prior AI knowledge assumed
🟡 Practitioner — assumes basic ML familiarity
🟤 Expert — deep technical detail, historical context
Tech Stack
Layer	What's used
Markup	HTML5
Styling	CSS (custom properties, grid, animations)
Logic	Vanilla JavaScript — no libraries, no framework
Fonts	System font stack (-apple-system, BlinkMacSystemFont, Inter, Roboto)

No npm install. No build step. No .env. No external requests beyond the browser's own font stack. The entire app is one .html file.

Running It
bash
# Option 1 — just open it
open ai_glossary_prototype.html

# Option 2 — serve locally
npx serve .
# or
python3 -m http.server 8080

Open http://localhost:8080 in your browser.

Customizing

All content and configuration lives in the <script> block at the bottom of the file.

Add a new term

Find the const TERMS = [ array and add an entry:

js
{
  term: "Your Term",
  era: "Agentic Era",          // must match one of the ERAS values
  cat: "Core Concepts",        // must match one of the existing categories
  level: "beginner",           // "beginner" | "practitioner" | "expert"
  beginner: "Plain-English definition here.",
  technical: "Technical definition for practitioners here.",
  example: "A real-world example of this in action."
}

Longer multi-word phrases work — entries are rendered in the order they appear in the array.

Add a new era or category

Eras are defined in const ERAS = [...]. Categories are derived automatically from the cat field across all terms — add a new cat value to any entry and it appears in the filter automatically.

Change the color palette

All colors are CSS custom properties in :root. Difficulty-level dot colors are:

css
--lvl-beginner: #8fc4a7;       /* light green */
--lvl-practitioner: #4d7c63;   /* mid green (matches accent) */
--lvl-expert: #2f5844;         /* dark green */
--accent: #4d7c63;             /* primary accent — buttons, borders, focus */

Add or edit empty-state messages

Find const EMPTY_QUIPS = [...] and add objects with a title and sub field. A random one is chosen each time results drop to zero — not on every keystroke.

How Filtering Works
Search input matches against term, beginner, and technical fields (case-insensitive, substring)
Era and category chips filter independently on top of the search results
autoAdjustFilters() runs on every keystroke: if matches land in exactly one era, that era chip activates; if they span several, "All" is restored — same logic for category
The stats line reflects auto-narrowing with a · filters auto-set from your search note
Resetting clears query, both filters, and refocuses the search input
Roadmap
 Expand to 400+ planned terms
 Keyboard navigation through cards
 Bookmark / save terms across sessions
 Printable / exportable cheat sheet
 Inline "related terms" links between cards
 Dark/light mode toggle (currently dark only)
Built By

Soundarya Alagesan — designer with a machine learning engineering background, building AI-forward products for people who don't fit the defaults.

→  GitHub · TinyTutor · LinkedIn

a living reference that keeps pace with the field.
