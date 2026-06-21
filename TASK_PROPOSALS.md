# Codebase Issue Triage: Proposed Fix Tasks

## 1) Typo fix task
**Issue found:** `README.md` contains typos in the last bullet under "issues" ("differerent" and "paces").

**Proposed task:**
- Correct the sentence to: "I have three categories of posts with slightly different formatting, so changing sizing requires edits in multiple places."
- Do a quick typo pass over `README.md` for similar mistakes.

**Why this matters:** Typos reduce readability and make maintenance notes look less reliable.

---

## 2) Bug fix task
**Issue found:** `_layouts/default.html` nests `<li>` elements directly inside a `<p>` element in the Education section, which is invalid HTML and can cause inconsistent rendering across browsers.

**Proposed task:**
- Replace the `<p>` wrapper around the education bullets with a semantic `<ul>`.
- Keep existing visual spacing by moving inline spacing styles to `<ul>` / `<li>` as needed.

**Why this matters:** Valid HTML improves rendering consistency, accessibility tooling behavior, and future maintainability.

---

## 3) Documentation discrepancy task
**Issue found:** `README.md` says there are "three categories of post with slightly differerent formatting," but `_layouts/default.html` has the Intel section fully commented out, so the page currently renders only two visible sections (Research and Projects).

**Proposed task:**
- Update `README.md` to reflect current behavior (2 visible sections), or
- Re-enable the Intel section in `_layouts/default.html` if 3 sections are still intended.
- Add one sentence in README clarifying whether Intel entries are intentionally hidden.

**Why this matters:** Keeping docs aligned with actual behavior prevents confusion for future updates.

---

## 4) Test improvement task
**Issue found:** There is no automated check to catch template/markdown build regressions.

**Proposed task:**
- Add a minimal CI workflow that runs `bundle exec jekyll build` on push/PR.
- Optionally add a second step for HTML/link checking (`htmlproofer`) scoped to local links.

**Why this matters:** A basic build check catches template/front matter breakage early and reduces manual verification.
