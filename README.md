# Learning Log

Daily log of my data analytics journey. Started Oct 19, 2026.

**Goal:** Entry-level data analyst, using Python, Excel, SQL and Power BI, with real projects on GitHub.

## Progress

| Skill | Status | Started |
|---|---|---|
| Python | In progress | Oct 19, 2026 |
| Excel | In progress | Oct 20, 2026 |
| SQL | In progress | Oct 22, 2026 |
| Power BI | Planned | Feb 2027 |

---

## Daily Log

### Day 4 - Oct 23, 2026
Python: even/odd/zero checker (zero tested first, 0 % 2 == 0 is True), leap year (400, then 100, then 4, strictest first). Tested 0, 7, 10, -3 and 1900, 2000, 2024, 2023.
Excel: relative, absolute and mixed references, =$A2*B$1 grid, COUNT vs COUNTA, blank vs 0, COUNTIF, SUMIF vs SUMIFS argument order.
Git: config, init, add, commit -m, status, log --oneline, branch -M main, remote add, push -u. Made 3 commits and pushed to github.com/Swagat-97/git-practice.
Weak spots: $ placement, SUMIF vs SUMIFS order, git commit without -m.
Recall: relative moves, $ locks what follows it; zero goes before even because 0 % 2 is 0; add stages, commit saves a snapshot.

### Day 3 - Oct 22, 2026
Python: if/elif/else, and/or/not, nesting, strictest condition first, ties need >=.
SQL: CTE (one statement only, vs temp table), RANK/DENSE_RANK/ROW_NUMBER, PARTITION BY, LAG, running total, GROUP BY/HAVING. Practice: 3 problems, 1 right first try.
Git: theory only (practical done Day 4).
Open: SQL 5-question check on Colab data.
Weak spots: colon plus indent, plain if vs elif, window function before FROM, commas, alias.
Recall: conditions go strictest first; a CTE is lost after its statement; PARTITION BY keeps rows, GROUP BY collapses them.

### Day 2 (Oct 21): Python strings, Excel sales data

- **Excel:** finished the sales data check. Learned how XLOOKUP works, pivot tables and other formulas.
- **Python:** learned strings, some string methods, input(), and joining text.
- Learned indexing and slicing.
- Solved 3 practice problems on my own.

### Day 1 (Oct 19 to 20): Python variables, types, operators

- Learned what a variable is: a name that points to (references) a value.
- Explored types (int, float, str) and input(), and how they work.
- Learned operators, including floor division (//).
- Float fact: computers store decimals in binary, so some values come out ugly (like 0.1 + 0.2 giving 0.30000000000000004). For money I use round().
- Solved 3 practice problems on my own to test my understanding.
