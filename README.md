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

### Day 5 (Oct 24): Python loops, Excel GST, sort/filter, COUNTIFS and IF
- **Python:** re-read and revised Conditions (leap year from a blank file). Learned for/range, while, break, continue, and the sum, count and max patterns. Solved Sum of 1 to N and the multiplication table.
- **Excel:** GST with one absolute reference, price x rate grid (=$A2*B$1), sorting with headers, filter with COUNT vs SUBTOTAL, COUNTIFS, IF with AND/OR, IFERROR.
- Weak spots: $ goes on the part that stays, continue skipping the update in a while loop, range stop value, AND/OR over whole ranges.
- Open: SQL 5-question check (closes Day 3), moved to Oct 25 afternoon.
- Recall: for/range stop is excluded, so use n + 1; COUNT counts hidden rows but SUBTOTAL does not; AND/OR need single cells.

### Day 4 (Oct 23): Leap year, Excel references, first Git repo
- **Python:** wrote the even/odd/zero checker (zero is tested first because 0 % 2 == 0) and the leap year checker (400, then 100, then 4). Tested 0, 7, 10, -3 and 1900, 2000, 2024, 2023.
- **Excel:** learned relative, absolute and mixed references (=$A2*B$1), COUNT vs COUNTA, blank vs 0, COUNTIF, and SUMIF vs SUMIFS argument order.
- **Git:** learned config, init, add, commit -m, status, log --oneline and push. Made 3 commits and pushed to github.com/Swagat-97/git-practice.
- Weak spots: $ placement, SUMIF vs SUMIFS order, git commit without -m.
- Recall: relative references move, $ locks what follows it; add stages, commit saves a snapshot.

### Day 3 (Oct 22): Python conditions, CTEs, window functions
- **Python:** learned if/elif/else, and/or/not, nested conditions, and putting the strictest condition first. Solved 3 practice problems.
- **SQL:** learned CTEs (one statement only), RANK/DENSE_RANK/ROW_NUMBER, PARTITION BY, LAG, running totals, GROUP BY/HAVING. Did 3 practice problems, 1 right on the first try.
- **Git:** theory only (repository, staging, commit).
- Open: SQL 5-question check, moved to Oct 25.
- Recall: a CTE is lost after its statement; PARTITION BY keeps the rows while GROUP BY collapses them.

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
