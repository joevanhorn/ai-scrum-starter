# ABOUTME: A filled-in Issue Report from an Engineer sub-agent hitting a real failure
# ABOUTME: Doubles as the handout worked-example and the fixture SM scenarios dispatch against

# Issue Report

## Backlog item
Participant intake survey form (intake.db write path + validation)

## What I was trying to do
Make the blank-field validation test pass: submitting the form with a
blank name should return an error and write nothing to intake.db.

## What I expected
test_submit_blank_name.py asserts intake.db row count is unchanged after
a POST with a blank name. I expected it to pass once validation rejected
empty strings.

## What actually happened (verbatim)
    FAILED tests/test_submit_blank_name.py::test_blank_name_no_write
    assert 1 == 0
     +  where 1 = row_count('intake.db')
    A row was written despite the blank name.

The validation check fires and returns the error to the user, but a row
still lands in the database.

## Reproduction (minimal steps)
1. Start the app, POST name="" with the other two fields populated
2. Observe the error response is returned to the client
3. Query intake.db - one row was written anyway
4. test_submit_blank_name.py reproduces this directly

## Possible explanations (ranked)
1. (most likely) The DB write happens before validation runs - the insert
   and the validation check are in the wrong order in the request handler.
   Supports: the error IS returned, so validation runs; but the row exists,
   so the write already happened.
2. Validation rejects the response but a separate code path commits the
   transaction regardless. Less likely - there's only one write call.
3. Test isolation problem - a row from a prior test leaked in. Checked:
   the test sets up a fresh DB; row count starts at 0. Doubt this.

## What I did NOT do
I did not reorder the handler, change the validation, or modify the test.
The code is exactly as it was when the failure surfaced. I have a one-line
hypothesis (move the write below the validation gate) but did not apply it,
because confirming the handler's intended contract is a PO/Architect call,
not mine.

## What I need from PO
Confirm the intended contract: should validation always gate the write
(my read of the acceptance criteria), or is there a reason the write
precedes it? If the former, I'll move the insert below the validation
check and re-run. Awaiting your go-ahead.
