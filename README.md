# Hamza El Madani

**Informatikstudent im letzten Semester an der TH Brandenburg** · Lokale LLMs, RAG und LLM-gesteuerte Robotik

Ich bringe Open-Source-Modelle lokal zum Laufen und baue darauf Anwendungen, die
man messen kann: einen RAG-Chatbot mit Quellenangaben, einen Modell-Benchmark
für den konkreten Anwendungsfall und ein ROS-2-Robotersystem, in dem ein lokales
LLM per MCP Werkzeuge steuert. Mich interessiert, wie die Modelle unter der
Haube funktionieren und wie man sie stabil betreibt.

*Final-year Computer Science student. I run open-source LLMs locally, put them
behind clean APIs, and measure which model fits which job.*

---

## Projekte

### [THB StudentAssist](https://github.com/ICHBINMINIDA/THB-StudentAssist): RAG-Chatbot, Docker, LiteLLM, Benchmark

Mehrsprachiger Chatbot (DE/EN/AR) für Studierende, vollständig lokal.

- **Hybrid Retrieval** (Vektor + BM25, Reciprocal Rank Fusion), Antworten mit nummerierten Quellen und einem festen „Weiß ich nicht“, statt zu halluzinieren
- **Docker Compose** mit **LiteLLM** als OpenAI-kompatiblem Gateway vor **Ollama**, optional **vLLM** auf NVIDIA-GPU und **Open WebUI**
- **Modell-Benchmark** auf der echten Aufgabe: Quellentreue, korrektes Ablehnen, Sprache, Time-to-first-Token, Tokens/s, VRAM. Ergebnis: gemma3:4b schlägt gemma3:27b bei einem Sechstel des Speichers, das größte Modell ist hier nicht das beste
- FastAPI mit Streaming und Rate Limiting, Tests in CI

### [LLM + MCP Robot Navigation](https://github.com/ICHBINMINIDA/llm-mcp-robot-navigation): kontrolliertes Experiment, fünf Architekturen

Wie viel Kontrolle sollte ein LLM über einen Roboter bekommen? Fünf Architekturen,
von zeitgesteuerten Bewegungsprimitiven bis zu Skills, die das LLM nur plant,
alle über **MCP** angebunden und mit identischer Wahrnehmung, Kinematik und
Sicherheitsschicht, sodass nur die Rolle des LLM variiert.

- Messung pro Lauf als JSONL: Erfolgsrate, Zeit bis zum Ziel, LLM-Aufrufe, Anteil der Wartezeit auf das Modell, JSON-Reparaturen
- Drei unabhängige Not-Halt-Ebenen, davon ein verriegelnder Stop-Flag, den das LLM nicht aufheben kann
- Tests ohne ROS in CI (Python 3.10)

### [AI-Powered Autonomous Robot Navigation](https://github.com/ICHBINMINIDA/AI-Powered-Autonomous-Robot-Navigation): ROS 2, lokales LLM, Sprache, Vision

Sprachgesteuerter Roboter (TurtleBot3, ROS 2 Humble): Wake-Word und Spracherkennung
offline mit VOSK, Zielextraktion mit einem lokalen LLM über Ollama,
Objektsegmentierung mit SAM, reaktive Navigation. [Demo-Video im README](https://github.com/ICHBINMINIDA/AI-Powered-Autonomous-Robot-Navigation#-project-demonstration).

---

## Technologien

| Bereich | |
|---|---|
| **LLM-Betrieb** | Ollama, LiteLLM, OpenAI-kompatible APIs, Modell-Benchmarking |
| **LLM-Anwendungen** | RAG, LangChain, Chroma, Embeddings, MCP (Model Context Protocol), Prompting für strukturiertes JSON |
| **Infrastruktur** | Linux, Docker, Docker Compose, Bash, GitHub Actions |
| **Backend** | Python, FastAPI, REST/Streaming |
| **Robotik und Vision** | ROS 2 Humble, OpenCV, SAM, VOSK |
| **Sprachen** | Python, C, C++, Java, SQL |

**Arabisch** (Muttersprache) · **Deutsch** (C1, verhandlungssicher) · **Englisch** (Fachdokumentation)

---

[LinkedIn](https://www.linkedin.com/in/hamza-el-madani-263a09385/) · [GitHub](https://github.com/ICHBINMINIDA)
