# Verification

Run from this repository root:

```sh
python -m pip install -r requirements-dev.txt
python -m playwright install chromium
python -m pytest tests/test_examples.py -q
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
