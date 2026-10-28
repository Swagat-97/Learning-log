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

### Day 7 (Oct 26): Lists, tuples and slicing, loops revision, git log
- **Python:** Loops: range step is added to the index and stop is excluded; update before continue; multiples of both 3 and 5 use the LCM 15; max pattern starts from marks[0] and I must not name a variable max. Lists: index is an offset, negative index becomes n + index, slicing [start:stop:step] with direction decided by the step; append, insert, remove and sort return None, pop returns the item, sorted builds a new list. Tuples: immutable (TypeError), single-item needs a comma, a tuple holding a list can still change inside the list.
- **Git:** git log shows committed history only; a commit ID identifies one exact commit.
- **Weak spots:** step wording, naming the exact error, saying stop is excluded, pop() takes from the end, in-place methods return None.
- **Open:** Retry the Day 7 practice. Commit with messages that say what changed, not "third commit".
- **Recall:** (1) range(start, stop, step) adds the step to the index and excludes stop; in a while loop the update i += 1 must come BEFORE continue or the loop never ends; for "divisible by 3 and 5" use i%15==0 because 15 is the LCM (4 and 6 give 12, not 24); the max pattern starts from marks[0], and naming a variable max replaces the built-in so max([1, 2]) later raises TypeError. (2) A negative index becomes n + index, a slice is [start:stop:step] with stop excluded and direction decided only by the step; append, sort, remove and insert change the list in place and return None, pop returns the removed item, sorted() builds a new list; a tuple is immutable (TypeError on item assignment), a single-item tuple needs a trailing comma, and a tuple holding a list can still change inside that list. (3) git log shows only committed history (staged files show in git status), a commit ID identifies one exact commit snapshot, and three commits named "third commit" make the log useless, so write what changed.

### Day 6 (Oct 25): Weekly test, business questions, how LLMs work
- **Weekly test:** Python (FizzBuzz plus sum, type predictions), Excel (SUMIFS, COUNTIFS, IF with AND, price x rate grid) and Git (first commit and push). Python passed; COUNTIFS and the Git push step were repeated and cleared.
- **Business:** turned "sales are falling" into which, where, since when and compared with what. Revenue = orders x items per order x average price per item. Wrote a 5-line investigation for "revenue dropped 10%".
- **AI Fluency:** an LLM predicts the next token and can hallucinate; it does not calculate. LLM is the model, a chatbot is the product. Verified an AI answer in Colab: partly right.
- Weak spots: COUNTIFS needs (range, "condition") pairs, git remote add origin, exact text with no extra spaces.
- Open: AI Skill Hour, moved to Oct 27 afternoon.
- Recall: COUNTIFS takes range and quoted condition; origin is only a nickname until you add it; always verify AI answers with a run or the docs.

### Day 5 (Oct 24): Python loops, Excel GST, sort/filter, COUNTIFS and IF
- **Python:** re-read and revised Conditions (leap year from a blank file). Learned for/range, while, break, continue, and the sum, count and max patterns. Solved Sum of 1 to N and the multiplication table.
- **Excel:** GST with one absolute reference, price x rate grid (=$A2*B$1), sorting with headers, filter with COUNT vs SUBTOTAL, COUNTIFS, IF with AND/OR, IFERROR.
- Weak spots: $ goes on the part that stays, continue skipping the update in a while loop, range stop value, AND/OR over whole ranges.
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
- SQL check: solved all 5 (top customers, best product per category, repeat customers, month-over-month growth, running total) from a blank cell on Oct 26.
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
