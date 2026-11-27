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

## 2026-11-26 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: Part 3 `MinHeap` in core.py (explained only, AI made no edits)
- What was done:
  - Explained where MinHeap is used (Part 3 tab, app pools, Bryan's dijkstra) and what check_project.py tests
  - Explained the heap array layout, the (priority, counter, item) entry, bubble up, bubble down, and the empty-heap IndexError
  - Gave pseudocode-level steps and common pitfalls; no finished code
- Written by AI vs. student: no code written by AI; Kien to write push, peek, pop
- Tests: not run (Part 3 not written yet)

## 2026-11-26 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: Part 3 `MinHeap.push` in core.py (explained only, AI made no edits)
- What was done: walked through push with a traced example and a fill-in-the-blanks outline
- Written by AI vs. student: no code written by AI; Kien to write push
- Tests: not run

## 2026-11-26 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: Part 3 `MinHeap.push` and `MinHeap.peek` in core.py (reviewed only, AI made no edits)
- What was done:
  - Reviewed push: pointed out `append` given 3 arguments (needs one tuple), `i = len(self._a)` one past the end, comment typo `2*1`, and that a tie never moves the new entry up (it has the biggest counter)
  - Reviewed peek: empty check is right, but it returns the whole (priority, counter, item) entry instead of (priority, item)
- Written by AI vs. student: Kien wrote all of push and peek; AI only reviewed
- Tests: not run (pop not written yet, push bugs still open)

## 2026-11-26 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: Part 3 `MinHeap.push` and `MinHeap.peek` in core.py (re-reviewed only, AI made no edits)
- What was done:
  - push unchanged in the saved file: `append` with 3 args and `i = len(self._a)` still open
  - peek now returns `self._a[0][1][3]`: explained that chained `[ ][ ]` digs into the counter (an int) and crashes, that tuples start at index 0, and that it must build a new (priority, item) tuple
- Written by AI vs. student: Kien wrote all of push and peek; AI only reviewed
- Tests: not run (pop not finished)

## 2026-11-26 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: Part 3 `MinHeap.push` and `MinHeap.peek` in core.py (re-reviewed only, AI made no edits)
- What was done:
  - Confirmed Kien fixed push (`append` of one tuple, `i = len - 1`) and peek (returns `(priority, item)`)
  - Pointed out unfinished `pop` (`self._a[0] =` at line 200) is a SyntaxError that stops core.py from importing
- Written by AI vs. student: Kien wrote all of push and peek; AI only reviewed and tested
- Tests: push/peek tested on a scratch copy of the class: heap rule holds after 200 random pushes, peek gives min, tuple ties OK, dict items OK, empty peek raises IndexError. check_project.py not run (core.py does not import until pop is fixed)

## 2026-11-26 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: Part 3 `MinHeap.pop` in core.py (explained only, AI made no edits)
- What was done: walked through pop step by step (empty check, save top, move last to top, bubble down with child bounds and picking the smaller child) with a traced example and a fill-in-the-blanks outline
- Written by AI vs. student: no code written by AI; Kien to write pop (started with save-top and return lines)
- Tests: not run (pop unfinished)

## 2026-11-26 - Kien
- Requested by: Kien
- AI tool / model: Claude Code, Opus 5.5
- Parts / files touched: Part 3 `MinHeap.pop` in core.py (reviewed only, AI made no edits)
- What was done:
  - Reviewed Kien's pop: logic correct (empty check, one-entry case, bounds checks, right child compared to smallest, swap and descend)
  - Drew ASCII trees tracing a pop step by step
  - Suggested cleanup: remove commented-out old attempts and `raise` line, fix the "both sides are smaller" comment
- Written by AI vs. student: Kien wrote all of pop; AI only reviewed and drew diagrams
- Tests: check_project.py 3 of 8 pass (Parts 1, 2, 3), rules OK; extra edge cases OK (pop of single entry leaves len 0, equal priorities pop in push order, dict items)
