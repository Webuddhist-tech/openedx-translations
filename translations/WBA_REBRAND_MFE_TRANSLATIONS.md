# WBA MFE rebrand translation additions

The JSON translation catalogs cannot contain comments or named sections without
creating invalid data for Atlas/Transifex. For that reason, the WBA-owned
entries below are kept as the final property block in both the source catalog
(`transifex_input.json`) and each matching WBA locale JSON file. A blank line
separates that final block from the standard Open edX catalog entries.

This document is the label for that JSON block and the migration checklist for
future Tutor/Open edX updates. Do not add a marker key to a translation JSON
file: it would be treated as a real, user-visible translation message.

## WBA-owned message IDs

### Account copy overrides

- `account.settings.section.linked.accounts.description`
- `account.settings.section.social.media.description`

### Authentication branding

- `authn.brand.learn`
- `authn.brand.practice`
- `authn.brand.connect`
- `authn.brand.tagline`
- `login.continue.practice`

### Learner dashboard wording

- `learnerVariantDashboard.course` (`Courses` -> `Dashboard`)

### Header rebrand and navigation

- `header.links.courses` (`Courses` -> `Dashboard`)
- `header.user.menu.logout` (`Logout` -> `Sign Out`)
- `header.user.menu.login` (`Login` -> `Sign in`)
- `header.user.menu.register` (`Sign Up` -> `Register for free`)
- `header.user.menu.studio.maintenance`
- `header.label.language.menu`
- `header.label.language.heading`
- `header.label.brand.home`

### SherabAI course-authoring feature

All message IDs beginning with:

```text
course-authoring.ai-course-creator.
```

There are currently 48 of these IDs. They include the SherabAI course creator
and section editor UI.

## Future Tutor update workflow

1. Refresh the standard Open edX translation catalogs from the new Tutor/Open
   edX version.
2. Keep or restore the final WBA block in the relevant MFE source and locale
   JSON files.
3. Ensure every listed ID still matches the corresponding message ID used by
   the MFE source code.
4. Validate with `jq empty` before committing.

Other newly added MFE IDs in this release are standard Open edX catalog
updates or missing-string translations. They intentionally remain outside the
WBA block, so a future merge can distinguish them from WBA-specific work.
