# Carify Card Integration Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add Carify branding and a working local privacy-policy link to the Carify project card.

**Architecture:** Keep the existing static portfolio. Update only the Carify card markup in `index.html` and add small, scoped styles in `style.css`, reusing the existing logo and policy page.

**Tech Stack:** HTML, CSS, Python standard library for a temporary markup/path smoke check.

**Spec:** [../specs/2026-11-23-carify-card-design.md](../specs/2026-11-23-carify-card-design.md)

## Global Constraints

- Add the existing `carify/branding/carify_logo.png` asset to the Carify card only.
- Link the card to the local `carify/privacy_policy.html` page.
- Keep the existing Play Store call to action and all other project cards unchanged.
- Keep the user-selected local README title (`# smahidev.github.io`) while integrating the existing policy-page commit onto `origin/master`.
- Commit and push the Carify card, logo, and relevant design notes to `master`.

## Review Focus

- The logo path must resolve from the portfolio root.
- The policy href must resolve to the existing local policy page.
- The logo must have descriptive alternative text.
- The policy link must be visibly labeled “Privacy Policy”.
- The Play Store action must remain present, and other cards must not gain Carify-specific content.

---

### Task 1: Add Carify branding and privacy access

**Files:**
- Modify: `index.html` (Carify project card only)
- Modify: `style.css` (scoped Carify card branding and action styles)

**Interfaces:**
- Consumes: `carify/branding/carify_logo.png`, `carify/privacy_policy.html`, existing `.card` and `.btn` styles.
- Produces: a `.card-brand` header containing the logo (`alt="Carify logo"`) and title, plus a `.card-actions` group containing the existing Play Store link and a “Privacy Policy” link to `carify/privacy_policy.html`.

- [x] **Step 1: Define and run a temporary smoke check**

Use a temporary Python standard-library check (do not add a test framework or permanent test file) that verifies the Carify markup contains `.card-brand`, the logo path and alt text, `.card-actions`, the exact local policy href and label, and the existing Play Store URL. Also assert that both referenced local files exist. Run it before implementation and confirm it fails because the new card markup is absent.

- [x] **Step 2: Update only the Carify card markup in `index.html`**

Wrap the Carify title and image in `.card-brand`. Group its Play Store CTA and the local policy link in `.card-actions`. Leave the Finio card unchanged.

- [x] **Step 3: Add scoped responsive styling in `style.css`**

Align the logo with the Carify title; size it compactly without distortion. Lay out the two actions with a gap and allow wrapping on narrow screens. Reuse existing color, border, and button tokens where possible.

- [x] **Step 4: Run the smoke check and inspect the rendered page**

Expected: all markup and path assertions pass; the Carify card displays the logo and both actions, the policy link opens the local policy page, and the Finio card is unchanged. Check desktop and narrow viewport layouts.

- [x] **Step 5: Review the final diff**

Run `git diff -- index.html style.css` and confirm only the intended card and related styles changed. Stage only `index.html`, `style.css`, `carify/branding/carify_logo.png`, and these design notes; do not include unrelated formatting-only changes to the policy page or other existing assets.
