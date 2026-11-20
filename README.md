# 🌱 GreenFuture Python Quiz Application

A robust, beginner-friendly Python software application designed to replace manual grading with an automated utility. It handles topic-wise quiz creation, real-time answer scoring, performance analytics, defensive input validation, local data persistence (JSON & CSV), and multi-format report exports.

---

## 🌟 Key Features

* **Dual Interface Options**:
  * **Interactive Terminal Interface**: Menu-driven command prompt with ANSI formatting, defensive validation wrappers, fixed-width tables, and pagination breaks.
  * **Modern Streamlit Web GUI**: Clean visual dashboard with progress tracking, interactive radio options, KPI scorecards, and Matplotlib chart embeds.
* **Core Business Logic Engine**:
  * Topic-wise quiz selection, randomized question order, real-time score computation, and answer feedback explanations.
  * Search and category/keyword query filters.
* **Defensive Input Validation**:
  * Centralized input wrappers with range and type checks to prevent program crashes from bad, blank, or out-of-bounds user inputs.
* **Local Data Persistence & Auto-Recovery**:
  * Automatic JSON and CSV record reading/writing.
  * Encapsulated `try-except` blocks catching missing or corrupted files (`FileNotFoundError`, `JSONDecodeError`) to auto-repair data templates with seed records.
* **Executive Summary & Analytics**:
  * Performance metrics computing overall averages, unique learner counts, and pass rates.
  * **Threshold Warning Indicators**: Automatic alerts flagging topics with performance falling below the **60% mastery threshold**.
* **Visual Data Plotting**:
  * Matplotlib integration generating accuracy distribution bar charts and historical performance sequence trend graphs.
* **Multi-Format Summary Export & Bulk Import**:
  * Export structured **Markdown (`.md`)** reports, plain-text **Audit Logs (`.txt`)**, and **CSV** dataset logs.
  * Ingest legacy CSV question datasets with row-by-row format validation and detailed error logging.

---

## 📁 Repository Structure

```text
greenfuture_quiz_app/
├── README.md               # Project documentation & mentor guide overview
├── requirements.txt        # Python library dependencies
├── main.py                 # Application launcher (CLI or Streamlit)
├── app.py                  # Streamlit Web GUI application
├── config.py               # Path configurations & threshold parameters
├── data/                   # Local persistent storage directory
│   ├── questions.json      # Structured question database (JSON)
│   ├── questions.csv       # Mirrored question database (CSV)
│   ├── attempts.json       # Learner attempt history (JSON)
│   └── attempts.csv        # Mirrored attempt history (CSV)
├── exports/                # Output directory for exported reports & charts
├── src/                    # Modular backend implementation
│   ├── __init__.py
│   ├── models.py           # Dataclasses (Question, QuizAttempt, ExecutiveSummary)
│   ├── storage.py          # Persistence, seeding & corrupted file recovery handlers
│   ├── quiz_engine.py      # Quiz logic, search engine & input validation wrappers
│   ├── analytics.py        # Metrics aggregator & Matplotlib chart generator
│   ├── export_import.py    # Markdown/Text exporters & Bulk CSV uploader
│   └── cli.py              # Menu-driven Terminal Interface
└── tests/
    └── test_quiz_app.py    # Unit test suite verifying core features & persistence
```

---

## 🛠️ Quick Start & Installation

1. **Navigate to the Project Directory**:
   ```bash
   cd greenfuture_quiz_app
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Launch the Application**:
   - **Main Launcher**:
     ```bash
     python main.py
     ```
   - **Direct Terminal CLI Mode**:
     ```bash
     python src/cli.py
     ```
   - **Direct Streamlit GUI Mode**:
     ```bash
     streamlit run app.py
     ```

4. **Run Unit Tests**:
   ```bash
   pytest tests/
   # or
   python -m unittest tests/test_quiz_app.py
   ```

---

## 🏆 Hackathon Live Demo Walkthrough Guide

1. **Launch**: Run `python main.py` in the terminal and showcase the branded welcome screen.
2. **Defensive Validation Demo**: Attempt entering blank values, letters, or out-of-range choices in the CLI prompts to demonstrate automatic error catching and graceful reprompting.
3. **Take a Quiz**: Select "Python Programming" or "Renewable Energy", answer questions, and view immediate answer feedback and mastery celebration/warning flags.
4. **Analytics & Warning Flags**: View the Executive Analytics dashboard to show aggregated averages, pass/fail ratios, and automatic threshold warning alerts for weak topics.
5. **Data Persistence Verification**: Close the app, relaunch it, and verify that past attempts and custom added questions persist intact across restarts.
6. **Multi-Format Export**: Execute report export and inspect the generated Markdown report, text audit log, and Matplotlib chart images in the `exports/` folder.
