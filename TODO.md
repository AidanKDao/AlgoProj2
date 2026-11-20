# BloodLink TODO

Check items off with `[x]` as you go. Due dates are on Canvas. Rules and commands are in `CLAUDE.md`.

## Phase 0: Setup (first 2 days, both)
- [ ] Kien: install requirements and run `streamlit run app.py` in `CPSC335_Final_Project/BloodLink/`
- [ ] Bryan: same as above
- [ ] Screenshot of the app running, submit "Project Choice & Setup Check" on Canvas (5 pts)
- [ ] Create public GitHub repo (e.g. `bloodlink-cpsc335`), add both partners

## Phase 1: Core parts (next 4-5 days)

Do Part 2 (merge sort) and Part 3 (MinHeap) **first**. Bryan's greedy and Kruskal need merge_sort, and Dijkstra needs MinHeap.

### Kien (Student A)
- [ ] **Part 2** `merge_sort`: stable, returns a new list, O(n log n)
- [ ] **Part 2** `lower_bound`: first index with key >= target, O(log n)
- [ ] **Part 3** `MinHeap.push`, `peek`, `pop`: (priority, counter, item) entries, IndexError when empty, O(log n)
- [ ] **Part 1** `build_index`: keep the FIRST record, list duplicates in order found, O(n)
- [ ] **Part 7** `kmp_search`: failure table + one pass, overlapping matches, empty pattern returns `[]`, O(n + m)
- [ ] Edge cases: empty list, one item, all equal keys, tuple priorities, pattern longer than text

### Bryan (Student B)
- [ ] **Part 4** `greedy_select`: sort by value/weight with OUR merge_sort, take what fits, O(n log n)
- [ ] **Part 5** `dp_select`: 0/1 knapsack table + walk back, ids in original item order, O(n * capacity)
- [ ] **Part 6** `bfs_reachable`: deque, hop counts, respect `blocked_edge` in both directions, O(V + E)
- [ ] **Part 6** `dijkstra`: OUR MinHeap, return (dist, prev), only reachable nodes, O((V + E) log V)
- [ ] **Part 6** `mst_kruskal`: OUR merge_sort + union-find, edges in order added, O(E log E)
- [ ] Edge cases: capacity 0, item heavier than capacity, ties in ratio, unreachable nodes, blocked edge

### After each part
- [ ] `python check_project.py` passes that part and shows "Rules check: OK"
- [ ] Add an entry to `AI_LOG.md` if AI helped
- [ ] Commit under your own name

## Phase 2: Part 8 and deploy (next 2-3 days, both)
- [ ] **Part 8** `tour_brute_force`: permutations, start first, `([start], 0)` when no stops
- [ ] **Part 8** `tour_heuristic`: nearest neighbor + 2-opt (i >= 1 so start stays first)
- [ ] `check_project.py` shows **8 of 8** and "Rules check: OK"
- [ ] Every app tab works locally
- [ ] Deploy on share.streamlit.io (main file `app.py`), test the link in a private window
- [ ] README: short description + screenshot; live link in the repo "About" box

## Phase 3: Report (last 2 days, both)
Fill `CPSC335_Final_Project/BloodLink/REPORT_TEMPLATE.md`, export as `Report_BloodLink_<LastName1>_<LastName2>.pdf`.
- [ ] 1. Team, project, why we chose BloodLink
- [ ] 2. Live app + GitHub links
- [ ] 3. `check_project.py` screenshot
- [ ] 4. Big-O table with a reason for every function
- [ ] 5. Two doubling tests (Speed report tab) with ratios vs Big-O
- [ ] 6. Greedy vs DP: real numbers from the app where greedy loses (Bryan leads)
- [ ] 7. NP-hard: max stops brute force finishes in < 5 s, heuristic gap, why not 50 stops
- [ ] 8. Two limitations
- [ ] 9. Contributions: Kien and Bryan each write 2-3 sentences

## Phase 4: Presentation (8 min: ~6 demo + 2 Q&A, both must speak)
- [ ] Why BloodLink (30 s)
- [ ] App tour in tab order: Kien presents Parts 1, 2, 3, 7; Bryan presents Parts 4, 5, 6
- [ ] Greedy-vs-DP moment: a cooler setting where greedy loses, and why
- [ ] NP-hard moment: brute force vs heuristic as stops grow
- [ ] One doubling-test result and what it says about Big-O
- [ ] Open the live link, name one limitation
- [ ] Practice likely questions ("Why is Dijkstra O((V+E) log V)?", "What breaks without the heap counter?")
- [ ] Rehearse once under 8 minutes

## Submit (one per pair, on Canvas)
- [ ] Zip `BloodLink_<LastName1>_<LastName2>.zip` (no `venv`, `.venv`, `__pycache__`)
- [ ] Report PDF
- [ ] Live Streamlit link + GitHub link in the submission comment
- [ ] Final pushed version matches the submission
