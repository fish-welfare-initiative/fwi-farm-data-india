# Changelog

All notable changes to this dataset are documented here.

## [3.0.0] - 2026-08-07

### Changed — breaking

**Pond identifiers now use an `ara2_` prefix and have been regenerated.**

Earlier releases used `pond_` followed by eight hex characters. Identifiers
from different releases were therefore indistinguishable by inspection, so a
cross-release join would partially match instead of failing. The distinct
prefix makes that mismatch visible.

Any analysis joining on identifiers from an earlier release will not match.

### Removed

- Free-text notes containing sale prices, seed costs or earnings (92 notes in
  `stocking_harvest.csv`). The structured INR columns were dropped in 2.0.1,
  but the same figures had been entered as prose, so the stated exclusion of
  financial data was not actually in effect.

  Some of those notes were the only record of a harvest weight. Where
  `Fish harvested (total, in kg)` is empty for a harvest event, the weight is
  unrecorded rather than zero.

### Fixed

- `.gitignore` rewritten as an allow-list. It previously named specific files
  to exclude while leaving the build's input directory untracked-but-not-
  ignored; a single `git add -A` could have published the raw exports.
- Data dictionary reconciled with the files: removed two documented columns
  that exist in none of them, documented two that were present but undefined,
  listed the columns that are empty in every row, and flagged that
  `Date of data collection` means different things in different files.

## [2.0.1] - 2026-08-07

### Fixed

- Removed three references to non-public pond codes that appeared in free-text
  notes in `stocking_harvest.csv`
- Removed a village name from a note in `stocking_harvest.csv`; village names
  are excluded from this dataset
- Dropped two empty columns for amounts paid and earnings from
  `stocking_harvest.csv`. They held no values, but their presence contradicted
  the stated exclusion of financial figures.

No measurement values changed. Pond identifiers are unchanged from 2.0.0.

## [2.0.0] - 2026-08-07

### Changed — breaking

**Pond identifiers have been regenerated and do not match earlier releases.**

Identifiers are now randomly generated and derived from no farm attribute.
They were previously derived from internal records; that approach was replaced
to strengthen anonymisation. Any analysis joining on identifiers from the
January 2026 release will not match this data.

Researchers who need to reconcile work built on the earlier release should
contact us at [fwi.fish/contact](https://fwi.fish/contact).

### Added

- Coverage extended from 31 January 2026 to 6 August 2026
- 114 additional pond registrations and 34 additional dropout records
- 2,134 additional water quality measurements and 235 stocking/harvest events

### Changed

- `Fish source` generalised from free-text supplier names to categories. A
  named local supplier can identify an individual farm.
- `Sr. No` removed — an internal row counter with no analytical value
- Free-text notes reviewed; identifying references removed, and references to
  other ponds rewritten to use published identifiers
- `enrolled_ponds_2026-02-02.csv` renamed to `enrolled_ponds.csv`
- README corrected: the citation URL in the January release pointed at a
  repository that did not exist, and one record count did not match its file

### Coverage

- 323 ponds across Eluru (260) and Nellore (63)
- 19 June 2021 to 6 August 2026

## [1.0.0] - 2026-02-02

Initial public release, covering June 2021 to January 2026.
