# PathReview Contribution Journal

## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/157

**Issue title:** Relevance scorer “partial overlap” test fixture actually has full query overlap

**Tier:** [x] Tier 1  [ ] Tier 2  [ ] Tier 3

**Problem summary:**
The relevance scorer unit test intended to verify partial query overlap currently uses a chunk containing every meaningful term from the query. Because the fixture actually represents full overlap, the scorer correctly returns a score of 1.0 even though the test expects a value below 0.9. This affects the relevance scorer tests in `tests/unit/test_relevance_scorer.py`, rather than indicating a defect in the scorer itself. A successful fix will update the fixture so that it contains only some of the query terms and accurately tests partial overlap behavior.

**Selection notes:**
I selected this issue because it has a clearly defined failure, a focused reproduction command, and a narrow scope appropriate for a first contribution to a large codebase. The issue appears limited to correcting a unit-test fixture rather than changing production scoring behavior. The affected test file and expected outcome are identified, and the fix can be verified by running the focused relevance scorer test suite. I do not expect the issue to require database migrations, API changes, frontend changes, or broad architectural modifications.

**Branch name:** test/157-partial-overlap-fixture

**Setup confirmation:** [x] App runs locally at localhost:5173

**Cohort ledger:** [ ] Issue added to cohort ledger
