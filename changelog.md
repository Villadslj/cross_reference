# Changelog

## v2.1 (security & compatibility update)

- upgraded PDF.js from 1.10.81 to 3.11.174 and migrated to its current API; PDF JavaScript
evaluation is disabled (`isEvalSupported: false`) and the worker runs inside the dialog, so
document data never leaves the add-on
- upgraded jQuery from 1.9.1 to 3.7.1 (fixes known XSS vulnerabilities in old jQuery)
- all third-party scripts are now loaded over HTTPS with pinned versions and Subresource
Integrity hashes, so tampered files are rejected by the browser
- removed the unused Google Fonts import (one fewer external request)
- hardened the sidebar against DOM-based XSS (user-provided values are inserted as text,
not HTML)
- added an explicit `appsscript.json` manifest with the V8 runtime and least-privilege OAuth
scopes (current document only)
- fixed a `ReferenceError` in the test helpers that broke `runAllTests` on the V8 runtime

## v2

- capitalisation is left entirely to the user. When replacement text is lowercase, capitalisation is
based on the text being replaced.
- list of figures show the entire paragraph that contains the label
- support for suffixes