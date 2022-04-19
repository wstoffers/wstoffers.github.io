<head>
    <link rel="stylesheet" href="styles.css">
</head>

<h1 align="center">A Wicked PyTest Crash Course For Bootcampers (under construction)</h1>

- background/intro

```python
from platform import python_version
print(python_version())
```
That reads <c-s>3.7.9</c-s> in the environment I currently have loaded, and <c-s>3.7.13</c-s> in Google Colab.

- should have tests as requirements
- benefit: cya
- often that doesn't happen
- example of first couple english requirements
- discuss directory structure, naming convention
- visualize directory structure
```bash
myProject/
|---src/
|   |---__init__.py
|   |---code/
|       |---__init__.py
|       |---source.py
|---tests/
    |---__init__.py
    |---integration/
    |---src/
        |---__init__.py
        |---code/
            |---__init__.py
            |---source_test.py
```
- code/link to code that will create directory structure

```python
#source.py inside myProject/src/code/

def functionName():
    pass
```
- first function, single assert
```python
#source_test.py inside myProject/tests/src/code/

import pytest
import code.source
from pytest_mock import mocker

def test_functionName():
    assert code.source.functionName()
```
- simple code example of a unit test that represents first english requirement
- simple code example of empty function
- how to execute pytest, what failed test looks like
```bash
$ cd myProject/src;python -m pytest ../tests/src --cov=.. --cov-report=term:skip-covered -vv --disable-warnings --maxfail=2
```
- code example of completed source that passes test

- first method, multiple asserts
- more complicated english requirements that suggest source class
- code example pytest to represent english, multiple asserts
- code example of empty class? how to execute pytest w/ additional flag? show test failure?
- code example of completed source that passes test

- function, two tests due to if
- simple code example of a unit test that represents english requirements
- simple code example of empty function
- how to execute pytest, what failed test looks like
- code example of completed source that passes test, but usees if
- second test for other path through code

- method, two tests due to exception, use fixture
- english requirements that suggest exception
- code example of two tests
- code example of empty class? how to execute pytest w/ additional flag? show test failure?
- code example of source that correctly raises exception, passes both tests

- function, first mock

- method, mock and parameterize?

- functions, repeatability with CPU pinning?