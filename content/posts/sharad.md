+++
draft = true

title = "Sharad Ratatui, My Journey in Rust, AI & TUI RPGs"
date = "2025-09-21"
in_search_index = true
description="Sharad, a Cyberpunk Textual RPG in the terminal, written in Rust with Ratatui"
[taxonomies]

tags = ["project", "rust", "ratatui", "game-dev", "tui", "learning", "AI" ]
languages = ["en","ja"]
[extra]
og_image="/img/sharad/image-term.jpeg"
+++

![](/img/sharad/image-term.png)

---

## Draft Outline for Zola Post: “Sharad Ratatui — My Journey in Rust, AI & Terminal RPGs”

---

### Front Matter (Zola)

```md
+++
title = "Sharad Ratatui — My Journey in Rust, AI & Terminal RPGs"
date = 2025-09-XX
draft = false
tags = ["Rust","Game","Terminal UI","TUI","AI","Prompt Engineering","Software Engineering"]
+++
```

---

### 1. Introduction: Why Sharad Ratatui

- Hook: A short story or anecdote — maybe your first time trying Shadowrun (or tabletop RPGs), or when terminal UIs fascinated you.
- What _Sharad Ratatui_ is, in one-sentence: A text-based RPG built in Rust, using ratatui for the interface, with AI for the GM/narration.
- What inspired it: Shadowrun, desire to learn idiomatic Rust (ownership, lifetimes, modules), terminal UI, working with language models.
- What the article will cover: architecture, challenges, growth, technical decisions, future direction.

---

### 2. Project Overview & Key Features

- Repo stats / visibility
  - Number of commits (\~278) in the repository. ([GitHub][1])
  - Dual-license: Apache-2.0 + MIT. ([GitHub][1])

- Core features
  - Natural language input from the player, narrative generated in real-time with OpenAI. ([GitHub][1])
  - Character sheet, skills, inventory that persist and update.
  - Terminal UI via ratatui: menus, inputs, display of game screen, dialogue. ([GitHub][1])
  - Save / load functionality.
  - Audio cues / narration voices (styles) for immersion.

- Architecture / module breakdown (modules you have)
  - `ai.rs`: narrative flow + state updates. ([GitHub][1])
  - `game_state.rs`: structs and logic for world & character state. ([GitHub][1])
  - `character.rs`: attributes/skills/inventory. ([GitHub][1])
  - `settings.rs` / `settings_state.rs`: config, API key, audio etc. ([GitHub][1])
  - `ui/` directory: TUI components.
  - `main.rs`: entry point, initializing and glue.

- Tech stack & crates / external services
  - Rust + ratatui. ([GitHub][1])
  - OpenAI API for narrative.
  - Serialization / persistence (what you use: e.g. JSON, database, etc.).
  - Audio / voice (if using TTS or other crates).
  - Testing: `tests/` folder. ([GitHub][1])

---

### 3. Technical Challenges & How I Solved Them

For each of these, expand with what you did, code examples, what you learnt:

| Challenge                                           | What made it hard                                                                                                                     | Solution(s) / Trade-offs                                                                                                                                                                      | Key Takeaway                                                                                          |
| --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Rust’s ownership & borrowing**                    | Passing mutable state across TUI redraws, AI calls, UI components; managing lifetimes with asynchronous or callback-style flows.      | Refactored state into owned structs/enums; limited mutability; used borrowing patterns carefully; perhaps cloned when necessary but minimized; possibly refactored to reduce lifetime scopes. | Gained a stronger intuition for borrowing, lifetimes; reduced bugs/crashes; better maintainable code. |
| **Integrating with OpenAI / Prompt Engineering**    | Dealing with latency; inconsistent responses; ensuring story doesn’t drift; structuring prompts so state is kept.                     | Created structured assistant functions; build modules that summarize past state; regular checks / validation of AI output; fallback or error handling for bad AI outputs.                     | Better reliability; more control over AI narrative; better UX.                                        |
| **Terminal UI (ratatui): Layout, Input, Redrawing** | Redrawing efficiently; handling user input asynchronously; rendering character sheet vs dialogue; keeping UI clean under constraints. | Used ratatui layouts; optimized redraws; separated UI logic from state logic; tested with slow AI responses; show placeholders (“loading…”).                                                  | Learned UI-flow; better performance; UI feels responsive.                                             |
| **State Persistence / Save-Load & Versioning**      | Ensuring saves don’t break when you change structs; serializing state fully; handling corrupted or missing data; migrations.          | Defined stable serialization formats; versioned save schema; wrote load functions that check for missing fields; fallback defaults.                                                           | Safer persistence; options to evolve features without losing user data.                               |
| **Error handling, unexpected input, robustness**    | Players may type anything; AI might return something unexpected; network/API errors; TTS failures; terminal resizing etc.             | Broad error enums; using `Result`/`thiserror` or similar; recovering from failure (retries, fallbacks); input sanitization; defensive coding.                                                 | Reduced crashes; increased stability; better user trust.                                              |

---

### 4. Concrete Skills Demonstrated

Organize by skill areas. For each, tie to a specific module / code sample in your repo.

- **Rust fundamentals**
  - Ownership & borrowing: examples from `game_state.rs` or how `character.rs` references UI state without excessive cloning.
  - Enums, pattern matching, traits: maybe in AI module when matching commands, or when matching AI responses / assistant functions.

- **Async & I/O / API integration**
  - How you invoke OpenAI API, how you deal with latency, wrapper functions, error handling.
  - If there’s any asynchronous code, or if you simulate async (e.g. threadpool) for AI calls.

- **Terminal UI / Ratatui mastery**
  - Layouts: how you structure UI across panes (dialogue, commands, character sheet).
  - Input handling: mapping keyboard input to commands; prompts; switching menus.
  - Redraw & performance: how you avoid flicker; how you display loading states.

- **State management & persistence**
  - The save/load system.
  - Serializing state: struct design so that it's versionable / backward compatible.

- **Error handling & robustness**
  - The custom error types.
  - Handling missing API keys, rate limits, malformed AI output.

- **Prompt engineering & AI workflow**
  - The “assistant functions” structure you have (in ai_structure.md / code).
  - How you keep narrative coherence across prompts; summarizing state; avoiding drift or hallucination.

- **Code hygiene & tooling**
  - Testing: what tests you have, what behavior you check.
  - Documentation: README, ai_structure.md, module comments.
  - Git workflow, refactoring, perhaps CI (if any).

---

### 5. Results / What Worked Well

- List of things that are stable / polished in Sharad now: e.g. character sheet display, inventory updates, dialogue flows, save/load, audio cues.
- Maybe share performance observations: typical latency, UI responsiveness, resource usage (if known).
- Feedback (if you got any) or your own sense: what users (if any) liked.
- Before/after: e.g. prior to refactor X it was messy / bug-prone; after, simpler flows, fewer bugs.

---

### 6. Limitations & What’s Left to Improve

- Things you still want but haven’t fully implemented: a deterministic/offline mode; more robust intent parsing; better voice/narration styles; better tests; better error reporting; perhaps mobile / non-terminal front ends.
- Known limitations: latency with AI calls; prompt drift or occasional AI errors; dependency on external API; difficulty adding new content; serialization versioning caveats.

---

### 7. Future Work & Vision

- Upcoming features / module ideas: e.g. voice styles, multiple AI agents, non-terminal UI, audio integration improvements, offline fallback.
- Long-term potential: maybe shipping a web version, GUI, packaging, community contributions.
- How this project reflects your growth path: what you want to learn next (e.g. more about concurrency / async, embedding / WASM, performance tuning, better UI/UX, maybe Dioxus/web front-ends).

---

### 8. What I Learned & My Growth as a Rust Developer

- Key “Aha!” moments: e.g. when you finally understood lifetime issues; when an architecture refactor cleaned things up; when prompt engineering improved drastically.
- Practices you adopted: modular design; separating concerns; writing tests; resilient error handling; thinking about UX even in terminal; balancing speed vs correctness.
- Soft skills: perseverance, refactoring legacy code, learning from mistakes, reading documentation / libraries (ratatui, serde, etc.), learning to reason about AI-assisted systems.

---

### 9. Conclusion & Takeaways for Recruiters

- Recap: Why _Sharad Ratatui_ is more than a hobby project — it shows you can build real software, plan architecture, deal with complexity, learn new tools, integrate with AI, ensure robustness.
- What a team hiring you would gain: someone who can pick up Rust, build solid systems, write maintainable code, tackle tricky problems, iterate.
- Invitation: “If you’d like to see the source, try the game, or talk about how I solved X or Y, feel free to browse the repo / reach out.”

---

### 10. Appendices / Extras (if appropriate)

- Screenshots of the TUI in action (dialogue + character sheet + inventory).
- Possibly diagrams: module tree; data flow (user input → AI → state → UI).
- Code snippets: before/after of a refactor.
- Git stats (lines of code, commits).
- Links to issues / pull requests that show complexity or improvements.

---

## Suggestions for Zola Specifics (Markdown / Multilingual)

- Use two versions: English and Japanese; possibly share same structure, translating key technical terms carefully.
- Use Zola shortcodes for code blocks, images. Include syntax highlighting for Rust code.
- Embed images (terminal screenshots) via `static/` directory. Maybe light/dark terminal theme.
- If applicable, use Zola’s taxonomies to tag with skills (Rust, AI, TUI) so it shows up in those categories.
- Use relative/permalink links: link to modules in GitHub via stable paths; to ai_structure.md; to tests folder, etc.

---

This outline plus contents should give you a solid scaffolding. If you want, I can also mock up a couple of paragraphs (introduction + one challenge section) in both English & Japanese to get you started. Do you want me to do that?

[1]: https://github.com/prohaller/sharad_ratatui/?utm_source=chatgpt.com "ProHaller/sharad_ratatui: A ratatui porting of my little game."
