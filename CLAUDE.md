# CLAUDE.md - BloodLink (CPSC 335 Final Project)

Instructions for any AI assistant (Claude Code or similar) working in this repo. Read this whole file before doing anything.

## Project

- Course: CPSC 335 Algorithm Engineering, CSUF (Dr. Syed Hassan Shah). Worth 20 points.
- Project: **BloodLink**, a regional blood-unit sharing planner built in Streamlit.
- Project folder: `CPSC335_Final_Project/BloodLink/`
- Full requirements: `Final_Project_Instructions.pdf` (repo root).
- Task list: `TODO.md` (repo root).
- AI log: `AI_LOG.md` (repo root). **Required, see below.**

## Team and ownership

| Person | Role | Owns |
|---|---|---|
| Kien | Student A (data and text) | Part 1 `build_index`, Part 2 `merge_sort` + `lower_bound`, Part 3 `MinHeap`, Part 7 `kmp_search` |
| Bryan | Student B (decisions and routes) | Part 4 `greedy_select`, Part 5 `dp_select`, Part 6 `bfs_reachable` + `dijkstra` + `mst_kruskal` |
| Both | Together | Part 8 `tour_brute_force` + `tour_heuristic`, report, deployment, presentation |

Rules for the AI about ownership:
- Find out who you are working with at the start of a session. If it is not clear, ask: "Are you Kien or Bryan?"
- Only change the parts the person you are working with owns (or shared Part 8 / report / deployment work). If they ask you to edit the other partner's part, point that out and confirm before editing.
- Each student must be able to explain every line of their own parts in the live presentation. Code they cannot explain gets no credit. So explain what you write, keep it simple, and prefer guiding over dumping full solutions when the student wants to learn it.

## AI log (REQUIRED)

Every AI session that changes files, writes code, or gives substantial help **must append an entry to `AI_LOG.md`** before the session ends. Never edit or delete earlier entries. Use this format:

```
## YYYY-MM-DD - <Kien | Bryan | Both>
- Requested by: <name of the person who asked>
- AI tool / model: <e.g. Claude Code, Opus 5.5>
- Parts / files touched: <e.g. Part 3 MinHeap in core.py>
- What was done: <1-4 bullets, plain words>
- Written by AI vs. student: <which code the AI wrote, which the student wrote or rewrote>
- Tests: <check_project.py result or "not run">
```

Add the newest entry at the bottom. If you only answered a question and changed no files, still log it in one line if the help shaped the code.

## Hard rules for `core.py` (a part that breaks these earns 0)

- **Banned inside core.py:** `sorted()`, `.sort()`, `heapq`, `bisect`, `re`, `str.find()`, `str.index()`, `str.count()`, `.rfind()`, and `in` used to search inside a string.
- The checker flags *any* method named `sort`, `find`, `index`, `count` or `rfind`, so do not call `list.index()` or `list.count()` either.
- **Allowed:** `dict`, `set`, `list`, `collections.deque`, `itertools.permutations`, and the functions marked GIVEN (`path_to`, `tour_cost`, `time_it`).
- Do not rename functions or change their inputs/outputs. Follow each docstring exactly.
- `greedy_select` and `mst_kruskal` must use our own `merge_sort`. `dijkstra` must use our own `MinHeap`.
- Only `core.py` is required. `app.py` may be restyled, but every tab must keep working. Do not edit `theme.py`, `glue.py`, `main.py`, `check_project.py`, `tests/`, or `data/` (the data may not be changed).
- Code quality is graded: clear names, short comments.

## Commands (run from `CPSC335_Final_Project/BloodLink/`)

```
pip install -r requirements.txt
streamlit run app.py            # or: python -m streamlit run app.py
python check_project.py         # parts passed + rules check
python main.py --demo           # every part printed in the terminal
python -m pytest tests          # public tests
```

Run `python check_project.py` after every change to `core.py`. The instructor's tests have more cases than the checker, so also test edge cases: empty lists, ties, unreachable nodes, empty pattern, no stops.

## BloodLink data notes

- 31 blood units, 18 places (root `N00` = Regional Blood Center), 37 courier links, 14 label messages, 2 recall keywords (`LOT A7731`, `LOT C1209`).
- One duplicate barcode exists (`BU-39612`), so `build_index` must report it.
- Heap priority (from theme.py): fewest hours until expiry, then O-negative first, then more patients helped. Priorities are tuples, and the heap must break ties by insertion order (the counter).
- Knapsack: weight = `cooler_slots`, value = `patients_helped`, cooler capacity 4-40 slots (default 18).

## Git

- One shared GitHub repo, commit often under your own name. Do not commit `venv/`, `.venv/`, or `__pycache__/`.
- Do not commit or push unless the student asks.
