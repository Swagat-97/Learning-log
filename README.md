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

### Day 11 (Oct 30): Conditions and lists/tuples recall, Git branch and merge practice
- Python: if/elif/else runs only the first True branch; separate ifs are each checked; else pairs with the nearest if at the same indentation; a failed outer if skips the inner condition; "and" needs two full comparisons (SyntaxError otherwise), 30 <= marks < 40 also works; sort() returns None, sorted() returns a new list, pop() returns the removed item; (5) is int, (5,) is tuple; a tuple slot cannot be reassigned (TypeError) but a list inside can change (num[1].append(3)); slices clip, a single index gives IndexError; the step sign sets the direction
- Excel: retest of IF/AND boundary rows (>= vs >) and missing $ (valid formula, wrong numbers, no error)
- Git: branch, commit, switch, merge as fast-forward (no new commit on main) and as merge commit (both branches have new commits, 2 parents, "Merge made by the 'ort' strategy"); git log --oneline --graph --all; > overwrites, >> appends
- Weak spots: reason not just output; exact names (None, TypeError, AttributeError, SyntaxError); "nested" and "loop" used correctly; tracing the exact line; a merge commit comes from diverged branches, not from typing a message; merge commit has 2 parents
- Open: hardest-problem redo from a blank file not done; git push from Colab with a token not retested; $ rule needs one more retest
- Recall: tuple slot fixed but inner list can change; fast-forward vs merge commit; missing $ gives silent wrong numbers

### Day 10 (Oct 29): Excel sales check recall, Status column, Git branches, merge, conflict, clone and pull
- **Excel:** Recalled SUMIFS, COUNTIFS, XLOOKUP (separate lookup and return ranges, exact match by default), pivot source range (extend it or use an Excel Table, then Refresh) and #N/A checks (LEN, TRIM, SUBSTITUTE with CHAR(160)). Status column =IF(AND(B2>1000,C2>100),"High","Low") with boundary rows O2 and O3 staying Low; COUNTIFS pairs gave the same 3 rows; "at least" flips O2 and O3 (count 5). Revised $E$1 in a tax formula: without the $, D4 reads E3 (empty) and silently gives 600 instead of 708.
- **Git:** A branch is a separate line of commits and main is one branch. git switch -c makes a branch; git branch shows names with * on the current one. A fast-forward merge only moves a label; merging diverged branches makes a merge commit with 2 parents. A conflict needs the same lines of the same file changed on both sides; I fix it by editing the file to delete the three markers, then git add, then git commit. git clone <URL> gives the files, the full history and origin; git fetch downloads without touching my files; git pull is fetch plus merge.
- **Weak spots:** #N/A checks (LEN, TRIM, CHAR(160), not EXACT), pivot source range, fast-forward vs merge commit, conflict = same lines of the same file, fetch vs pull, exact error names.
- **Open:** git push from Colab not retested (needs a token). Commit the Day 9 and Day 10 entries as separate commits. Oct 30 tasks next.
- **Recall:** (1) IF(AND(...)) uses plain comparisons on single cells and COUNTIFS pairs give the same rows; boundary rows like exactly 1000 stay Low, and "at least" flips them; a missing $ on the tax rate makes D4 read the empty E3 and silently gives 600; Refresh does not pick up rows outside a pivot's source range, so extend it or use an Excel Table; for #N/A compare LEN, then TRIM, then SUBSTITUTE(A2,CHAR(160),"") for the non-breaking space. (2) A branch is a separate line of commits (main is just one); a fast-forward merge only moves a label and makes no commit, while merging diverged branches makes a merge commit with 2 parents; a conflict needs the same lines of the same file changed on both sides, and I fix it by deleting the three markers, then git add, then git commit. (3) git clone <URL> copies the files, the full history and sets origin; git fetch downloads new commits without touching my files and git pull is fetch plus merge, so it can conflict; cloning again does not update, it makes a new separate copy.

### Day 9 (Oct 28): Lists len and looping, average, second largest, recall of Oct 20-21, git remote revise
- **Python:** len() counts list items and the last index is len - 1; looping by value (for m in marks) vs by index (for i in range(len(marks))); n = n * 10 inside a loop only repoints the name n, so the list is unchanged, and assigning nums[i] = ... is what changes items. Average = sum(marks) / len(marks) (a float; empty list gives ZeroDivisionError). Second largest: list(set(nums)) to drop duplicates, unique.sort() with brackets, guard len(unique) >= 2, then unique[-2].
- **Git:** Practised init, branch -M main, add, commit, remote add origin, remote -v. origin is the nickname for the GitHub URL; main vs master is the separate branch name. The push was not retested today (proven earlier on git-practice).
- **Weak spots:** missing () is a silent bug (unique.sort); blending two reasons (immutability vs str + int); naming the exact error; // rounds down; origin vs main.
- **Open:** Retry the Day 9 practice. Retest git push from Colab with a token when needed.
- **Recall:** (1) len(list) counts items (for a string it counts characters, so len(" ") is 1); for m in marks gives each value and for i in range(len(marks)) gives indexes 0 to len - 1; n = n * 10 only points the name n at a new number, so to change items I write nums[i] = nums[i] * 10. (2) Average is sum(marks) / len(marks) and returns a float; second largest is list(set(nums)), then unique.sort() WITH brackets (without them nothing sorts and no error shows), guarded by len(unique) >= 2, then unique[-2]. (3) "5" + 3 is a TypeError because + cannot mix str and int (not because of immutability), s[0] = "j" is a TypeError because strings are immutable, // rounds down (-7 // 2 = -4), and origin is only a nickname for the GitHub URL that has nothing to do with the branch name main.

### Day 8 (Oct 27): Excel references, SUMIFS/COUNTIFS/IF/IFERROR practice, Git push steps
- **Excel:** Recalled references: down changes only the row, across only the column, a diagonal drag does both; $ goes on the part that stays (=B2*$E$1). Offset rule: row 2 to row 4 is +2, so E1 becomes E3. SUMIFS per category with locked ranges and an unlocked criteria cell (totals 1620, 2170, 1830, cross-checked against 5620). COUNTIFS for West above 500 gave 3, at least 500 gave 5. IF with AND uses plain comparisons, ties need >=. IFERROR(...,0) hides real errors and the 0 counts in AVERAGE.
- **Git:** add, commit, push in that order; git add needs a file name or dot; after add the file is staged, after commit it is in git log; status shows current files, log shows commits only.
- **Weak spots:** counting the exact offset, > versus >= from the wording, AND syntax (comparisons, not range pairs), IFERROR risks, staged versus committed.
- **Open:** Re-test the weak spots in the Oct 29 recall. Write commit messages that say what changed.
- **Recall:** (1) Down changes the row and across changes the column; $ goes on the part that stays; a reference shifts by the exact distance moved, so E1 becomes E3 after +2 rows. (2) SUMIFS has the sum range first; COUNTIFS pairs work as AND and need equal-size ranges (19 vs 18 rows gives #VALUE!); read the wording for > versus >=; AND takes plain comparisons; IFERROR(...,0) hides errors and the 0 counts in AVERAGE. (3) Git: add, commit, push; add needs a path; after add the file is staged, after commit it shows in git log; status is current files, log is commit history only.



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
