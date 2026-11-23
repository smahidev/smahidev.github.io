# Carify Card Design

## Intent and goals

Make the Carify project card on the portfolio recognizable and give visitors a direct way to read its existing privacy policy.

## Scope and constraints

- Add the existing `carify/branding/carify_logo.png` asset to the Carify card only.
- Link the card to the local `carify/privacy_policy.html` page.
- Keep the existing Play Store call to action and all other project cards unchanged.
- The user chose to keep the local README title (`# smahidev.github.io`) while integrating the existing policy-page commit onto `origin/master`.
- Commit and push the Carify card, logo, and relevant design notes to `master`.

## Approaches

- **Use the existing logo and local policy link (selected):** adds clear Carify branding and a direct, same-site policy route with no duplicated content.
- **Embed the policy in the card:** rejected because the long policy would dominate the project listing.
- **Link to an external policy:** rejected because the policy already exists in this site and an external dependency is unnecessary.

## Design

Add a compact logo beside the Carify title and include a clearly labeled “Privacy Policy” link alongside the existing Play Store action. Keep the existing portfolio card styling, with responsive sizing and descriptive alternative text for the logo. The policy link opens the local page in the same tab.

## Non-goals

Do not redesign the project grid, change the privacy policy content, modify the Carify app itself, or resolve unrelated repository state.
