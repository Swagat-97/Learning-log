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

### Day 23 (Nov 12): Files, modules, chart, conditional formatting, validation
- Learned: FileNotFoundError (child of OSError); with closes the file even when an error occurs, and the error continues; f.write adds no newline; modes r, w (erases on open) and a; readlines() returns a list with "\n" kept; strip() removes whitespace at both ends and split(",") cuts at commas; header row raises ValueError (int("marks")); next(f) discards the header; header-only file gives total 0 and an empty file raises StopIteration; math.sqrt always returns a float; round half to even; randint includes both ends; date minus date is a timedelta (.days is an int); Excel: sorted pivot column chart, Bottom 10% rule, data validation list from a range
- Built: write 5 lines and read back with readlines (5); names-from-CSV loop; days-left-to-Dec-31 (49 on Nov 12)
- Key idea: with and a typed range keep things in one place; read the exact function before answering, because randint is not range
- Interview edge: date.today() in Colab is usually UTC; floor goes toward negative infinity; Bottom 10% is a rank rule, so 5 cells is too coarse
- Weak spots: indentation errors (5, 6, 7 spaces); wrote randint endpoints as 4, 5; said ValueError for a TypeError case once; said StopIteration for a header-only file; no prediction before running (many times)
- Open: Descriptive statistics, Text and date functions, Marks analyzer, Git conflict redo, README/.gitignore, Day 22 and Day 23 PDFs
- Recall: w erases on open, a appends, next(f) discards the header; randint includes both ends, date minus date is timedelta; bar chart for unordered regions, Bottom 10% is by rank, range list lives in one place

### Day 22 (Nov 11): Narrow except, grade_counts helper, input loop, else clause
- Learned: narrow except ZeroDivisionError means a TypeError is not caught and leaves the function; ZeroDivisionError also covers 10 / 0.0, 10 % 0 and 10 // 0; else runs only when the try finishes with no error and is skipped when except runs; an error raised inside else is not caught by the except above it; int(" 7 ") and int("-3") work, int("12.5") and int("") raise ValueError
- Built: safe_divide retest (pass); grade_counts split into a grade_of helper (pass, boundary-tested); ask_number with while True, try/except ValueError, in two versions (return in try, return in else)
- Key idea: keep the try block to the risky line; code that depends on it succeeding goes in else
- Interview edge: dict counting has shorter forms (dict.get(key, 0) + 1, collections.Counter); an error inside else stays visible
- Weak spots: said ValueError for safe_divide(10, "a") (it raises TypeError); described the first-time step as "if the dict is empty" instead of "if the grade is not a key"; did not write predictions before running (3 times); vague reasons like "cannot convert string to int"
- Open: FileNotFoundError, modules (import, math, random, datetime), Practice 3 (days left to Dec 31), README/.gitignore, Files and CSV, retest of the TypeError vs ValueError naming
- Recall: safe_divide with a narrow except raises TypeError for a string; grade_counts calls the helper per mark with a first-time step and an update; ask_number loops until int() succeeds, return ends it, else runs on success

### Day 21 (Nov 9): Exceptions and try/except basics
- Learned: unhandled error stops the program with a traceback; try/except ZeroDivisionError; except name must match the raised error; after the first error Python jumps to the matching except and skips the rest of the try; ValueError (int("abc"), int("12.5"), int("")) vs TypeError (int(None), 10 + "a"); except ValueError as e gives the message and e is deleted after the except block; bare except hides every bug
- Built: safe_divide(a, b) with except ZeroDivisionError returning None (finished Nov 10 night)
- Key idea: catch the narrowest error you can name; an error that reaches the traceback is a bug you can see
- Interview edge: except Exception is almost a bare except; it makes safe_divide(10, "a") return None and hides the TypeError
- Weak spots: used except Exception where the spec needed ZeroDivisionError only; answered for my old code instead of the version asked; skipped the first check when tracing an if/elif chain (<= 74 gap with 74.5)
- Open: else clause, FileNotFoundError, modules, Practice 2 (valid number loop), Practice 3 (days left to Dec 31), README/.gitignore, grade_counts split into grade_of helper, safe_divide retest
- Recall: unhandled error stops with a traceback and except must match; ValueError bad content vs TypeError wrong type; bare except hides bugs, catch the narrowest error

### Day 20 (Sun, 8 Nov 2026): Functions, is_prime, modulo and grade counts
- Learned: % gives the remainder (12 = 2 x 5 + 2); n % 2 == 0 tests even; range stop is excluded; a prime is greater than 1 with no divisor from 2 to its square root.
- Built: is_prime(n) with the n < 2 guard, range(2, int(n ** 0.5) + 1), return False inside the if and return True after the loop; six assert tests (-5, 1, 2, 4, 9, 97); grade_counts(marks) giving {'A': 3, 'C': 2, 'B': 1} for [85, 42, 67, 91, 30, 75].
- Key idea: one number in every divisor pair is at most the square root, so test only up to int(n ** 0.5) + 1; range accepts only integers; the update in the dict counting engine runs for every item.
- Interview edge: without + 1 the function is wrong for 4, 6, 8, 9, 15, 25, 35, 49 (below 100); without the guard 0 and 1 give True and negatives raise TypeError; dicts keep insertion order; in checks keys on a dict and values on a list.
- Weak spots: single words instead of exact statements; print instead of return True; wrote in marks instead of in result; said update runs only for repeated grades; said an empty range gives False; mixed up which bug breaks 6 and 8; wrote =< instead of <=.
- Open: split grade_counts into a grade_of helper; redo the first-time step and update on a new problem; retest the empty range and the bug-to-test mapping.
- Recall: why stop at the square root and why + 1; what each return does; first-time step versus update.

### Day 19 (Sat, 7 Nov 2026): Text vs real dates, and Python functions
- Learned: real dates are numbers (3 Nov 2026 = 46329); text dates sort alphabetically; ISTEXT and ISNUMBER tell them apart; DATEVALUE converts text but depends on the regional day/month order.
- Python functions: def, parameter vs argument, return vs print, no return gives None, return outside a function raises SyntaxError, code after return never runs.
- Key idea: an empty-list average raises ZeroDivisionError; return None, not 0, and the caller checks is None. Defaults live in def; keyword arguments live in the call and match by name; positional first, then keyword.
- Interview edge: SyntaxError stops the whole file before any line runs; mutable default argument trap (items=[]); ^ is XOR in Python, ** is power; use is None, not == None.
- Weak spots: wrote ISDATE (does not exist); mixed up print and return; confused default, keyword and mixed calls; gave TypeError instead of SyntaxError for argument order; keyword arguments match by name, not order (corrected three times).
- Open: finish Functions (is_prime, grade counts function); retest profit-case lines 4 and 5.
- Recall: text vs real dates and the check formulas; return vs print vs no return; default vs keyword arguments.

### Day 18 (Fri, 6 Nov 2026): Pivot tables, monthly trend and top 5 customers
- Learned: four pivot areas (Rows, Columns, Filters, Values); Values can do Sum, Count, Average, Max, Min; real dates group by month, text months sort alphabetically.
- Built: monthly revenue pivot with a line chart using MonthSort (202608 etc.) and Month in Rows (Aug 120,500; Sep 96,500; Oct 81,500; Nov 35,500; total 334,000) and a top 5 customers pivot with a bar chart (Bina 89,500, Dev 62,500, Hari 54,000, Anil 41,000, Esha 32,000).
- Key idea: line chart for ordered time, bar chart for comparing categories. A numeric MonthSort key forces the right month order. Top 5 comes from Value Filters > Top 10 > Top 5 by Sum of Revenue.
- Interview edge: after a Top N filter, the Grand Total shows only the visible rows (279,000 vs 334,000). Nov is a partial month (only Nov 1 and Nov 3), so it cannot be compared with full months.
- Weak spots: reason for the line chart was circular; recall did not name the helper-field method I used; confused sorting with the Top N filter; missed Count/Average/Max/Min, filter scope, pivot chart, source range and Refresh in first recall.
- Open: optional rebuild of the monthly chart by grouping Order Date directly; redo the hardest pivot problem from a blank sheet.
- Recall: four areas; why a text month sorts wrongly and the fix; why the Grand Total is not company revenue after Top 5.

### Day 17 (Nov 5, 2026): No study session, planning and Day 16 close

- Planning: Reviewed the college timetable (classes 9:30-4:30, Saturday holiday) and planned Nov 6 to Nov 8 around it. Merged overlapping tasks: Functions lesson first, README/.gitignore as a first lesson, one AI skill hour (Sunday).
- College: Finished a college task. Slept in the evening from tiredness.
- Python / Excel / SQL / Git: No new topic. Nothing to revise.

Weak spots: Evening lost; Day 16 recall and close done after midnight.
Open: Pivot hands-on (monthly trend, top 5 customers), Functions lesson, README/.gitignore lesson, Git conflict redo, AI skill hour, profit-case retest. All moved into Nov 6 to Nov 8.
Recall: None today, no study session.

### Day 16 (Nov 4, 2026): Business metrics practice and the profit case

- Business: KPI parts (name, formula, period, target, owner). Leading vs lagging against a named outcome. Metric vs dimension, and fields that can be both. Vanity metrics vs AOV and repeat purchase rate. Profit case: orders up, profit down, split into volume effect (+Rs 20,000) and margin effect (-Rs 40,000) using profit per order and margin %.

Weak spots: Wrong formulas in recall (profit = revenue - cost, margin = profit / revenue x 100). Discount named as a cause of higher cost per order. Recommendation repeated a check. Orders called leading and lagging without naming the outcome.
Open: Profit-case retest (lines 4 and 5). Not done from the Nov 4 plan: Functions, is_prime, average(list), grade counts, AI skill hour, Git conflict redo.
Recall:
- Profit case: check profit per order and cost per order first. An unchanged AOV can still hide a fall in profit if cost per order rises.
- Volume effect is extra orders x old profit per order. Margin is profit / revenue x 100, the share of revenue left as profit.
- A metric can be summed, averaged or counted. A dimension is grouped by. A KPI is a goal-based, actionable, time-bound metric. Age can be both: average age is a metric, age bands are a dimension.

### Day 15 (Nov 3, 2026): Pivot tables, Git revision, AI prompting, business metrics

- Excel: Pivot table areas (Rows, Columns, Values, Filters). Sum to Average via Value Field Settings. Pivot chart follows its pivot. Top seller = Value Filters > Top 10 > Top 1 by Sum, not Max. Source range: Ctrl+T or PivotTable Analyze > Change Data Source, then Refresh.
- Git: Parent counts (root 0, normal 1, merge 2). Fast-forward vs merge commit. clone vs init. Conflict markers, resolve with edit, add, commit, status.
- AI Fluency: Clear instructions, few-shot (consistent Input/Output pairs), iteration. Fix the instruction first, then the examples. Reusable prompt library.
- Business: Metric vs dimension, KPI, conversion rate, leading vs lagging.
- Python: Retake of the pass-count dict (records of student, subject, mark). Passed with guidance. Fix: first-time step and update as two separate ifs.

Weak spots: Parent counts (A and D wrong). Merge commit parents (B and D, not A). "Git cannot combine" instead of "cannot fast-forward" (wrong 5 times). Few-shot examples not Input/Output pairs. Max vs Top 1 by Sum. Forgot Refresh in recall.
Open: Build the pivot practically (category x region, group dates by month). Clone to another folder and a conflict from a blank folder. Business practice feedback and the profit case. AI Fluency part C.
Recall:
- Pivot source range: the pivot reads only its selected range. Ctrl+T makes the source grow, or use Change Data Source. Refresh is still needed.
- Git: root commit 0 parents, normal 1, merge commit 2. Fast-forward when main has no new commit since the branch was created. Merge commit when both branches have new commits.
- Few-shot prompting: give a few Input/Output examples in the style you want so the AI copies the pattern.

### Day 14 (Nov 2): Git and Excel retest, recalls, Python dict fix session
- Git: retest of three cases: different files on both branches = merge commit (diverged), same line = conflict, no new commit on main = fast-forward; --ff-only refuses anything but a fast-forward, --no-ff forces a merge commit
- Excel: IFNA vs IFERROR retest passed; IFERROR catches #N/A, #DIV/0!, #REF!, #VALUE!, #NAME?, #NUM!, #NULL!
- Python: recalls on Lists and tuples and Dicts and sets, all six answers correct (append and sort return None, sorted() makes a new list, data[0][1] = 85 raises TypeError, get() default, KeyError, set removes duplicates, a - b, a & b)
- Python fix: one engine for dict problems: the key, the first-time branch, the update (add 1, add the value, or compare and replace); three versions solved: best score from tuples, longest word per first letter (> keeps the first on a tie), count per size band (15 and above is large); found the bug `if v not in dict` (checked the score, so the elif never ran, and the elif kept the lower mark); never name a variable dict
- Weak spots: output right by coincidence (test with reversed order); ties with > vs >=; boundary 15; exact Python error messages and the words raise vs print
- Open: Python retake on Nov 3 afternoon; business topic, AI Fluency, AI skill hour; Functions lesson and is_prime moved to Nov 4; clone and conflict practice on Nov 3
- Recall: fixed the merge types by cause (diverged, same line, no new commit on main); sort returns None, get() returns None or the default, a set drops duplicates; the dict bug was `v not in dict` checking the score.

### Day 13 (Nov 1): Weekly test (taken late, after midnight)
- Python: Problem 1 (tuples inside a list, best score per student with a dict, plus slicing and tuple assignment) not solved after 25 minutes; Dicts and sets and Lists and tuples repeat; fix is to find the key, what happens when the key is missing, and the update line
- Excel: INDEX+MATCH (=INDEX(B2:B5, MATCH("A103", A2:A5, 0)) gives Bag), XLOOKUP 4th argument if_not_found, plain MATCH on a missing ID gives #N/A; wrong reasoning on IFNA (wrapped around the whole formula it catches the MATCH error); IFERROR hides #REF!, #VALUE!, #NULL!, #NAME?, #DIV/0! as well
- Git: diverged merge with different files gave a merge commit (Merge made by the 'ort' strategy, 2 parents); clone and pull explained wrongly in the test
- Weak spots: carrying a known pattern into a new problem shape; IFNA vs IFERROR reasoning; merge commit comes from diverged branches, not from different files; clone vs pull
- Open: business topic, AI Fluency and AI skill hour moved to Nov 3 and Nov 4; Python retake on a new problem
- Recall: stuck on a new dict shape, fix = key, missing key, update line; IFNA fixes only #N/A, IFERROR hides real mistakes; clone copies a repository with history, pull = fetch + merge.

### Day 12 (Oct 31): Dicts and sets, INDEX+MATCH, XLOOKUP missing-ID message
- Python: parallel lists break silently if one is reordered; list.index() gives the first match, ValueError if missing; a dict looks up by key (KeyError if the key is missing); get(key, default) stores nothing and returns the default; counting: counts[w] = counts.get(w, 0) + 1 (counts[w] += 1 gives KeyError on a new key); items() gives (key, value) tuples, unpacked in the loop; a plain loop over a dict gives keys; a set is unordered unique items, no indexing (TypeError), & | - give intersection, union, difference, and counts and order are lost; word count with split() and lower(); topper with > keeps the first on a tie, >= lets the last win; common elements with sorted(set(l1) & set(l2))
- Excel: INDEX+MATCH: MATCH gives the position inside the range (not the sheet row), INDEX reads that position, =INDEX(B2:B5, MATCH("P103", A2:A5, 0)) returns 120; XLOOKUP 4th argument is if_not_found; a missing ID gives #N/A; IFERROR hides every error, IFNA only #N/A; recalls on $ and SUMIFS passed
- Loops: recall passed (update line before continue, range stop excluded)
- Weak spots: giving reason with the value; get() reads and stores nothing; keys are case-sensitive; position inside a range vs sheet row; a - b direction; fast-forward vs merge commit (diverged branches force a merge commit, not "different files")
- Open: hardest-problem redo from a blank file (lists/tuples and dicts/sets); word counter handles only commas; push from Colab with a token not retested
- Recall: 1. Python: get(key, default) returns the value if the key exists, else the default, and stores nothing, because a dict looks up by key. Counting: counts[w] = counts.get(w, 0) + 1, so ["I", "am", "I"] gives {'I': 2, 'am': 1}.
2. Python: a set is an unordered collection of unique items, so s[0] raises TypeError: 'set' object is not subscriptable, because there is no position. & is intersection, | is union, - is difference.
3. Excel: XLOOKUP returns the matching item from the return array, exact match by default, and its 4th argument shows a message instead of #N/A. INDEX+MATCH: =INDEX(B2:B5, MATCH("P103", A2:A5, 0)), because MATCH gives position 3 and INDEX reads 120.

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
