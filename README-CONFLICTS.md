This workspace includes a small Node.js + EJS demo to show how two machines (A and B) might create merge conflicts.

How this is set up:
- `app.js` — minimal Express server (renders EJS views).
- `views/contact.ejs` — intentionally contains two git conflict regions (header and form) showing differing edits from machine A (HEAD) and machine B (branch-B).

To reproduce a real Git conflict locally:
1. Initialize git and commit `views/contact.ejs` base version.
2. Create branch `A` and edit the header/form as desired, commit.
3. Create branch `B` and edit the same lines differently, commit.
4. Merge one into the other: `git checkout A && git merge B` — Git will produce conflict markers like the ones in `views/contact.ejs`.

The teacher will evaluate only the interface (views + CSS). The EJS files are the UI source (not plain .html), and CSS is the existing `tooplate_style.css`.
