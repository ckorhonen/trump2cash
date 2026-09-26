# Working on Trump2Cash

`analysis.py` finds companies and sentiment, `trading.py` chooses orders,
`twitter.py` streams/posts tweets, and `main.py` connects them. Adjacent
`*_tests.py` files include live-service tests; `market_data/` supports benchmarks.

Use an isolated Python environment and the historical `requirements.txt`.
Do not assume modern provider APIs still support this snapshot. The README test
command is `USE_REAL_MONEY=NO pytest *.py --verbose`, but that flag only disables
real-money orders: tests can still require credentials and contact Twitter,
Google, and brokerage services. Inspect the selected tests and mock external
clients before running a focused test. Syntax-only checks can use
`python -m py_compile <changed-python-files>` and do not prove behavior.

Do not run `main.py`, enable real-money mode, publish tweets, or run the benchmark
against providers without explicit task authorization. Keep financial credentials
and account identifiers out of output. No lint/typecheck/build task is declared.

## Completing changes

Follow existing patterns and carry authorized work through the relevant checks,
repairing failures caused by the change. Choose routine implementation details
directly; ask only when missing information materially changes scope or outcome.
For documentation-only edits, check the diff, referenced paths, and command
accuracy rather than starting application runtimes. If a prerequisite blocks a
check, report the exact blocker and continue independent authorized work. Close
with changed paths, checks actually run and results, and remaining unverified
behavior; distinguish commands inspected from commands executed.
