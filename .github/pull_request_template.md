## Pull Request Title

Use the following format for the PR title:

[Implemented | Improved | Fixed | Completed | Documented | Reverted]: short description (OFBIZ-XXXX)

Guidelines:
- Start with the appropriate change type
- Use imperative mood (e.g. "Fix bug", "Improve validation")
- Keep the title concise
- If a related Jira issue exists, include it at the end in parentheses

Example:

Fixed: Correct rounding issue in order calculation (OFBIZ-8091)


---

## Details

Describe what has been changed and why.

Please include:
- the problem addressed
- the rationale for the change
- relevant implementation details
- potential side effects or limitations

Example:

This change fixes an incorrect rounding behavior in order totals.

The previous implementation applied rounding multiple times during
calculation, which could produce incorrect totals in edge cases.
The fix ensures rounding occurs only once at the final stage.


---

## Testing

Describe how the change was tested.

Include:
- steps to reproduce the issue (if applicable)
- how the fix was verified
- any relevant test cases added or updated


---

## Thanks (optional)

If applicable, acknowledge contributors or people who helped identify the issue.

Example:

Thanks: John Doe for reporting the issue and providing the initial analysis.


---

## Additional Notes (optional)

Add any other information that may help reviewers understand the change.

## For more information

https://cwiki.apache.org/confluence/display/OFBIZ/OFBiz+commit+message+template