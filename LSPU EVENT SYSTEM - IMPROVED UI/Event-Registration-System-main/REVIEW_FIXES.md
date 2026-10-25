# Review fixes

This copy includes targeted fixes based on the classmate's submitted ZIP.

- Replaced the unexplained `LS` placeholder shown for a featured event without a photo with a deliberate event-spotlight placeholder.
- Corrected password-reset wording: OTPs are displayed in the Flask terminal for this demo; they are not emailed.
- Improved OTP generation using Python's `secrets` module.
- Added a 10-minute OTP expiration and a five-attempt limit.
- Enforced a minimum 12-character password in the OTP reset route.
- Clears OTP data after successful reset, expiration, or too many incorrect attempts.
- Added startup schema checks to add OTP expiration/attempt columns to an existing SQLite or MySQL database.
- Updated the unused accounts template to remove edit/delete actions and remain read-only.
- Updated the README to document the terminal-based OTP demo.

## Verification

- Python syntax compilation passed.
- All four existing DSA unit tests passed.
- A live Flask/database smoke test could not be run in this environment because Flask is not installed here. Please run the app locally and test OTP reset against your own development database before submitting.
