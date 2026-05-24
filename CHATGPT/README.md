# XURMATILLO — ChatGPT Custom GPT Edition

The ChatGPT (GPT-5.5) deployment of the XURMATILLO Universal Cognitive Operating System.

**Founder:** Xurmatillo Oxunov

---

## What this folder is

A complete, self-contained drop-in for ChatGPT's Custom GPT builder. Everything needed to spin up a top-tier ChatGPT GPT in under 10 minutes:

- 1 master instruction (compressed to fit ChatGPT's 8,000-character Instructions field).
- 10 knowledge files (identical to the Gemini Gem edition — platform-agnostic).
- Conversation starters (Uzbek / Russian / English).
- GPT profile description copy.
- Step-by-step setup guide with verification tests.

---

## Quick start

1. Read `CHATGPT_SETUP_GUIDE.md` end to end.
2. Open ChatGPT → Explore GPTs → Create → Configure tab.
3. Paste `XURMATILLO_GPT_INSTRUCTION.md` into Instructions.
4. Upload all `KB_01_*.md` through `KB_10_*.md` into Knowledge.
5. Enable all four capabilities: Web Search, Canvas, Image Generation, Code Interpreter & Data Analysis.
6. Set Recommended Model = GPT-5.5.
7. Paste conversation starters from `CONVERSATION_STARTERS.md`.
8. Save and run the verification tests in the setup guide.

---

## File map

```
CHATGPT/
├── README.md                              ← you are here
├── CHATGPT_SETUP_GUIDE.md                 ← full deployment instructions + verification tests
├── DESCRIPTION.md                         ← short and long descriptions for the GPT profile
├── CONVERSATION_STARTERS.md               ← 4 starters in Uzbek/Russian/English
├── XURMATILLO_GPT_INSTRUCTION.md          ← master instruction (~7,942 chars, fits 8,000 limit)
├── KB_01_REASONING_COGNITION.md
├── KB_02_BUSINESS_ECONOMICS.md
├── KB_03_PSYCHOLOGY_BEHAVIOR.md
├── KB_04_TECHNOLOGY_AI_ENGINEERING.md
├── KB_05_SCIENCE_PHYSICS_CHEMISTRY.md
├── KB_06_MEDICINE_NEUROSCIENCE_HEALTH.md
├── KB_07_HISTORY_GOVERNANCE_LAW_ETHICS.md
├── KB_08_LANGUAGES_ARTS_COMMUNICATION.md
├── KB_09_SELF_MASTERY_STRATEGY_FUTURE.md
└── KB_10_META_INTEGRATION_WISDOM.md
```

---

## Design notes

### Why the instruction is compressed
ChatGPT's GPT Instructions field has an 8,000-character limit. The Gemini Gem version of XURMATILLO uses a ~21,000-character master instruction. For ChatGPT we re-engineered it down to ~7,942 characters while preserving:

- All 14 sections
- 7-level Truth Filter
- 9-layer thinking model
- File processing protocol
- Native tool activation map (Web Search, Canvas, Image Gen, Code Interpreter)
- 10 KB activation map
- All ethical prohibitions
- Architecture privacy + founder rule
- No-loop discipline

### Why the KBs are unchanged
The 10 knowledge files are domain-knowledge content (reasoning, business, psychology, etc.) and are platform-agnostic. They work identically in Gemini and ChatGPT, retrieved via each platform's RAG layer. No rewrite needed.

### Why all four capabilities must be enabled
Section VIII of the instruction explicitly maps user intents to specific ChatGPT tools. Disabling any of the four will leave that branch of the instruction inert and degrade the system's promise of grounding answers in real data and real artifacts.

---

## Cross-platform parity

| Feature | Gemini Gem | ChatGPT GPT |
|---------|-----------|-------------|
| 10 KBs | Identical | Identical |
| Truth Filter (7-level) | Yes | Yes |
| 9-layer thinking | Yes | Yes |
| Multilingual (Uzbek / Russian / English) | Yes | Yes |
| Architecture privacy | Yes | Yes |
| Founder rule | Yes | Yes |
| File processing protocol | Yes | Yes |
| Image generation | Nano Banana / Imagen | Native ChatGPT image gen |
| AI watermark detection | SynthID native | None native — external tools recommended |
| Code execution | Gemini Code Execution | Code Interpreter (Python sandbox) |
| Long-form workspace | Workspace integration | Canvas |
| Real-time grounding | Google Search | Web Search |
| Reasoning mode | Extended Thinking | GPT-5.5 Extra High |

---

## License

See repository root LICENSE.

---

*Maximum capability. Maximum integrity. Maximum precision. This is XURMATILLO.*
