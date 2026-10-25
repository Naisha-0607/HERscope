# Testing HERscope

This is a manual acceptance checklist for the current browser prototype. It is not a claim that all tests have already passed. Record the browser, date, result, and issue for each run. Use synthetic data only.

## Period tracking

- [ ] A valid period start date can be saved.
- [ ] A valid end date can be saved and is not before the start date.
- [ ] Multiple period records remain available after adding another period.
- [ ] Editing or deleting one record affects only that record.
- [ ] Refreshing the page preserves saved records in the same browser profile.
- [ ] Month/year boundaries and leap days do not shift dates.
- [ ] Cycle estimates are labelled as estimates and behave sensibly with missing/irregular history.

## Symptom journal

- [ ] An entry can be saved for a selected date.
- [ ] Multiple entries on one date work as intended.
- [ ] Edit and delete actions affect the correct entry.
- [ ] Empty notes and “no symptoms” work.
- [ ] Saved-entry counts and insights reflect stored entries.
- [ ] Refreshing the page preserves entries in the same browser profile.

## Profile and age guidance

- [ ] Age guidance updates when the age field changes.
- [ ] Guidance still updates after saving preferences and refreshing.
- [ ] Empty and out-of-range ages are handled clearly.
- [ ] Age guidance is educational and does not state that a condition is certain.

## Privacy and resilience

- [ ] Exported JSON parses and contains expected app data.
- [ ] No real health data is included in repository commits or screenshots.
- [ ] Reset/delete flows explain what is deleted and require confirmation.
- [ ] Storage-blocked or quota errors show a clear message and do not claim data was saved.
- [ ] App does not claim the demo account is real authentication or cloud sync.
- [ ] Keyboard navigation, visible focus, labels, contrast, and small-screen layout are checked.

## Reporting bugs

For each failure, note the steps to reproduce, expected behavior, actual behavior, browser/OS, and a screenshot with personal data removed.
