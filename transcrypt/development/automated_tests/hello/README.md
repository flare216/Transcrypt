# Transcrypt Autotester Demo

## Comparisons Versus Assertions

(Just in case you wonder where the test assertions are hidden)

<<<<<<< HEAD
Transcrypt's autotest framework verifies that the JS generated by Transcrypt on one hand, and CPython on the other, generate equal results at runtime.

So rather than matching JS output against hardcoded assertions, Transcrypt's autotest framework simply *generates* those assertions - by running the testlets within *CPython* (-r switch), recording the results, then within a Javascript runtime (e.g. your browser), comparing to the previous Python output.
=======
Transcrypt's autotest framework verifies the JS and Python runtimes generate equal results.

So rather matching JS output against hardcoded assertions, Transcrypt's autotest framework simply *generates* those assertions - by running the testlets within *Python* (-r switch), recording the results, then within a Javascript runtime (e.g. your browser), comparing to the previous Python output.
>>>>>>> b5e9a118d3581b9b396f614aa519e10b3340e1e7

## Usage

`autotest.py` and the testlets, by design, see above, can only run code which is within the supported transpilable set.

E.g. an `import sys` (without any exclusion pragmas) will break the test.

<<<<<<< HEAD
See the chapter *Autotesting Trancsrypt code* in the docs for a motivation and some more explanation.
=======
Thats why you have to add the current working directory to have `autotest.py`
find the testlets *outside* the Python runtime, not within, via `sys.path.insert`.

On POSIX systems this is the standard way: `export PYTHONPATH=".:$PYTHONPATH"`
>>>>>>> b5e9a118d3581b9b396f614aa519e10b3340e1e7