# Verification

Run from this repository root:

```sh
python -m pip install -r requirements-dev.txt
python -m playwright install chromium
python -m pytest tests -q
```

Tests use HTTP, not file URLs. They check every included example for text editing, table or slide structure changes, undo, HTML download, reopening, PDF page count, and browser JavaScript errors. Set CRAFT_BROWSER to an existing Chrome or Edge executable to use that browser instead.

The HTML examples contain the editor. No Python installation is required to open and edit them. Python is used when creating new HTML files and running these development checks.

The gallery screenshots show actual example HTML. Editor screenshots show temporary edits and selections made for demonstration. Screenshots of the artwork hide editor controls; the downloaded examples retain those controls.

## v0.2.0 baseline, checked on 2026-09-20

Windows 11, Python 3.14.2, Chrome. All 4 examples passed browser editing, save/reopen, undo, no external resource requests, and PDF page checks. Worksheets printed as one A4 page each; slide examples printed as three 16:9 pages each. Formula/graph tests verify fraction markup, source preservation and three calculated points. Shared editor integration tests: 9 passed.

Claude upload ZIP: one skill root, SKILL.md, relative references, bundled Python helper and MIT license. The helper was executed after extracting each ZIP to an isolated directory. Packaging follows the linked official Claude documentation. Actual generation inside Claude or Claude Code has not been tested in this release. Browser-dependent checks in a Claude environment remain conditional on available tools.

## v0.3.0 gallery expansion, checked on 2026-09-20

Two new examples in this repository passed browser edit, structure change, undo, HTML download/reopen, no external resource requests and PDF page checks. New worksheets print as one A4 page each; new slide examples print as three pages each. Previously published examples are unchanged and were not retested in this update. Both updated Claude ZIP helpers passed isolated extraction/execution checks.

## v0.4.0 reference gallery, checked on 2026-09-20

Six new examples in this repository were verified in Chrome over HTTP for editing, structure change, undo, saving/reopening, no external resource requests and PDF page counts. Across the two repositories, 12 targeted tests passed (11 prior examples deselected). The Cobalt Grid worksheet also checks formula source and calculated points. The Notebook Tabs worksheet checks navigation to the third activity; its final stage-label presentation was rechecked after the visual adjustment. Worksheets produce one A4 page each; slide decks produce three 16:9 pages each. Prior examples were preserved without rerunning the old engine suite. Claude ZIP extraction and bundled helper execution were verified.

## v0.5.0 white-paper layouts, checked on 2026-09-20

All 15 worksheet examples passed editing, saving/reopening, table structure changes and undo, external-resource checks, and A4 single-page output. Browser assertions verify white or transparent CSS backgrounds throughout worksheet content. Three same-topic layouts were added: magazine columns, inquiry map and work notebook. Their printed pages were visually inspected. Existing decorative panel backgrounds were removed; meaningful illustration colours, graph strokes and ruled answer lines remain. Slide examples were not changed or retested in this update. The Claude ZIP extracted helper passed its execution check.

## v0.6.0 basic layouts and compact headers, checked on 2026-09-21

Two basic worksheet compositions were added before the magazine, inquiry-map and work-notebook examples. All 17 gallery headers now fit in 20.0 to 24.5 mm, compared with 42.9 to 57.1 mm for the prior 15 examples. Measurements use Chrome print media; the top page margin is not included in header height. See headers-before.json and headers-after.json for individual values. No fixed header height or clipping is used. Title font controls remain editable; a browser test changes and restores the basic example title size.

All worksheet examples were checked for white backgrounds, editing, table changes/undo, saved-file reopening and one-page A4 PDF output. Basic sequential, basic record and work-notebook printed pages were visually inspected. Slide examples were unchanged. The updated Claude ZIP helper was verified after isolated extraction.

## v0.7.0 reviewed table header, checked on 2026-09-21

Applied the approved subject/lesson line above the title table to all 17 worksheet examples. Titles are centred in a merged first row; class/number/name (or workshop affiliation/group/name) follow in the second row. Body-table column headings use pale shading; page and answer backgrounds remain white.

All 17 browser tests passed. A targeted follow-up also verified lesson and name edits survive saving/reopening. Checks cover external metadata placement, centred titles, background/shading scope, body-table changes/undo and A4 one-page printing. Body text outside headers matches the preceding committed version in all 17 files. Headers measure 35.1 mm including the subject/lesson line and instruction; individual values are in headers-table.json. Printed magazine, inquiry-map and workshop pages were visually inspected. Slides were unchanged. Claude ZIP extraction/helper execution was verified.

### Writing-space allocation and empty-field correction

After reviewing excess lower-page whitespace, authored answer and sketch regions were enlarged in proportion to their existing dimensions. Print measurement leaves about 12-15 mm below the footer without shrinking any writing region or changing body text. All 17 worksheet tests passed again, now including a lower-page whitespace assertion. The shared editor passed 10 integration tests, including a regression proving an authored empty sketch area retains its minimum height in edit and preview modes. The empty-field fallback CSS previously overrode equally specific authored styles; it now has zero selector specificity. New printed inquiry-map, work-notebook and poster-draft pages were visually checked.

## v0.8.0 mathematics and science examples, checked on 2026-09-21

Three new examples passed browser checks for header placement, shading/white areas, lower-page whitespace, editing, structure changes/undo, saving/reopening and one-page A4 output. The two-series temperature chart was checked against its source data at all 10 points. Mathematical conditions in the money and rectangle problems were checked for consistent positive solutions. Previously published examples were unchanged and not retested in this update.

The mathematics sheet follows one middle-school linear-equation lesson: basic checks, guided modelling and independent application with verification. Scientific examples provide an experimental record and a fictional-data interpretation task. Runtime code was unchanged. Claude ZIP extraction and bundled helper execution were verified; model-generated output inside Claude remains untested.

### Expanded inquiry set

Three further examples (geometry, statistics and observation) passed targeted browser tests; there are six newly verified math/science examples in total. Geometry tests calculate all three angles from the actual SVG vertices. Statistics tests check means and medians from the displayed data. The new pages were visually inspected and all produce one-page A4 output with usable response areas and lower-page margins. Existing 17 examples were unchanged and were not rerun.

## Offline KaTeX editing, checked on 2026-09-21

The editor includes KaTeX 0.18.7, embedded WOFF2 fonts, a LaTeX editor with live preview, templates, apply/cancel, inline insertion and block equations. The bundle preserves KaTeX MIT notices and does not require a CDN, npm or Node in generated documents.

Validation: 13 focused development integration tests passed, covering existing editing behaviour plus invalid-input cancellation, undo/redo, copy, inline insertion, supported math variants, blocked external resources, editor refresh and offline saved-file editing. Four existing math lesson/deck examples passed real-browser edit/save/print tests after KaTeX conversion. The shipped formula demo passed its own offline browser test in each public repository (2 tests). Screenshots and a one-page PDF containing nine rendered math examples were visually inspected. Cobalt Grid header specificity was corrected while checking the converted worksheet so the approved title-table typography is retained.

The demo test is tests/test_math_editor.py. Prior non-math layout variants were not exhaustively retested in this update. The installation ZIPs were extracted and their bundled Python attachment helper executed. Generation inside the Claude service itself remains untested.
