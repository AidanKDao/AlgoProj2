# AI Log

Every AI session that writes code, changes files, or gives substantial help adds an entry here (format in `CLAUDE.md`). Newest at the bottom. Never edit or delete old entries.

## 2026-11-19 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: project setup only (no core.py code)
- What was done:
  - Compared the three project options; team chose BloodLink
  - Deleted the GridRestore and ShipSmart starter folders
  - Created `CLAUDE.md`, `TODO.md`, and this `AI_LOG.md`
- Written by AI vs. student: all three files written by AI from Kien's instructions
- Tests: not run

## 2026-11-23 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: `CLAUDE.md`, `TODO.md` (docs only, no core.py code)
- What was done:
  - Read the codebase and summarized how the parts depend on each other and what the checker tests
  - Fixed the project folder path from `CPSC335_Final_Project/BloodLink/` to `BloodLink/`
  - Suggested an order for Kien's parts (Part 2, then 3, then 1, then 7)
- Written by AI vs. student: path edits made by AI; no algorithm code written
- Tests: check_project.py run, 0 of 8 parts pass (nothing implemented yet), rules OK

## 2026-11-23 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: Part 1 `build_index` and Part 2 `merge_sort` in core.py (reviewed only, AI made no edits)
- What was done:
  - Ran `pip install -r requirements.txt`
  - Explained build_index and merge_sort step by step (base case, split + recursion, merge, leftovers, what `key` is)
  - Reviewed Kien's code and pointed out bugs (bare `return`, `<=` vs `<` in the loop, `key[...]` vs `key(...)`, `[::half]` slice)
- Written by AI vs. student: Kien wrote all code in build_index and merge_sort; AI only explained and reviewed
- Tests: check_project.py: Part 1 PASS; merge_sort correct on edge cases + 200 random lists; Part 2 waits on lower_bound

## 2026-11-23 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: Part 2 `lower_bound` in core.py (reviewed only, AI made no edits)
- What was done:
  - Explained lower_bound step by step (lo/hi pointers, why `lo = mid + 1` and `hi = mid`)
  - Reviewed Kien's code: pointed out the missing `return` and the `left = half` infinite loop
- Written by AI vs. student: Kien wrote all of lower_bound; AI only explained and reviewed
- Tests: check_project.py 2 of 8 pass (Parts 1, 2), rules OK; lower_bound matched expected results on 500 random cases
