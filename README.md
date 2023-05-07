# ut_assert

[![license](https://img.shields.io/github/license/sfwgeek/ut_assert?style=plastic)](https://github.com/sfwgeek/ut_assert/blob/main/LICENSE)


Basic Python package wrapping [unittest](https://docs.python.org/3/library/unittest.html#module-unittest) module [assertions](https://docs.python.org/3/library/unittest.html#assert-methods).


# Features
**_TODO_** :memo: :hammer_and_pick: :construction:

1. Make unittest assertions without having to subclass unittest.TestCase


## Why
1. Easier to read.
1. Easier to analyse code by searching for `assert.are_equal ...`


# Dependencies
Python 3.11+
- unittest


# Installation
**_TODO_** :memo: :hammer_and_pick: :construction:

[PyPA » Python Packaging User Guide » Tutorials » Installing Packages](https://packaging.python.org/en/latest/tutorials/installing-packages/)


[PyPA » Python Packaging User Guide » Tutorials » Installing Packages » Installing from PyPI](https://packaging.python.org/en/latest/tutorials/installing-packages/#installing-from-pypi)


## Unix/macOS
```console
$ python3 -m pip install "TODO"
```

## Windows
```console
C:\> py -m pip install "TODO"
```


# Examples
Instead of:
```py
import unittest

class TestStringMethods(unittest.TestCase):

    def test_upper(self):
        self.assertEqual('foo'.upper(), 'FOO')

    def test_isupper(self):
        self.assertTrue('FOO'.isupper())
        self.assertFalse('Foo'.isupper())

    def test_split(self):
        s = 'hello world'
        self.assertEqual(s.split(), ['hello', 'world'])
        # check that s.split fails when the separator is not a string
        with self.assertRaises(TypeError):
            s.split(2)

if __name__ == '__main__':
    unittest.main()
```

Can be:
```py
from todo import Assert

class TestStringMethods(unittest.TestCase):
#class TestStringMethods(unittest.TestCase):

    def test_upper(self):
        Assert.are_equal('foo'.upper(), 'FOO')
        assert.are_equal('foo'.upper(), 'FOO')
        Assert().are_equal('foo'.upper(), 'FOO')

    def test_isupper(self):
        assert.is_true('FOO'.isupper())
        assert.is_false('Foo'.isupper())

    def test_split(self):
        s = 'hello world'
        assert.are_equal(s.split(), ['hello', 'world'])
        # check that s.split fails when the separator is not a string
        with assert.raises(TypeError):
            s.split(2)

if __name__ == '__main__':
    unittest.main()
```


# Name Background
## Problematic Names
1. assert
   - state a fact or belief confidently and forcefully
   - https://www.google.com/search?q=meaning+assert
   - name taken by bultin [assert statement](https://docs.python.org/3/reference/simple_stmts.html#the-assert-statement)
1. affrim
   - state emphatically or publicly.
   - https://www.google.com/search?q=meaning+affirm
   - PyPI: https://pypi.org/project/affirm
   - GitHub: https://github.com/elifiner/affirm
1. attest
   - declare to be correct, true or genuine.
   - https://www.google.com/search?q=meaning+attest
   - PyPI: https://pypi.org/project/Attest
   - GitHub: https://github.com/dag/attest

## Possible Names
1. unit_test
1. affirm2
1. ut_assert
1. utassert
1. uh_suht
   - sounds like assert.
   - https://www.google.com/search?q=pronouce+assert
1. yoo_nuht
   - sounds like unit.


# Visual Studio Code
https://code.visualstudio.com/docs/python/testing

**_TODO_** :memo: :hammer_and_pick: :construction:
1. Add settings to repo.


# Influenced By
## attest
[attest](https://github.com/dag/attest)


## pytest
[pytest](https://github.com/pytest-dev/pytest/)


## PytTruth
[PyTruth](https://github.com/google/pytruth)

```py
AssertThat(a).IsEqualTo(b)
AssertThat(c).IsTrue()
AssertThat(d).Contains(a)
AssertThat(d).ContainsAllOf(a, b)
AssertThat(d).ContainsAnyOf(a, b, c)
with AssertThat(Error).IsRaised():
  Explode()
```

## unittest
[unittest](https://github.com/python/cpython/tree/main/Lib/unittest)

```py
self.assertEqual(a, b)
self.assertTrue(c)
self.assertIn(a, d)
self.assertTrue(a in d and b in d)
self.assertTrue(a in d or b in d or c in d)
with self.assertRaises(Error):
  Explode()
```

## xUnit
[xUnit](https://en.wikipedia.org/wiki/XUnit)

## SUnit
[SUnit](https://en.wikipedia.org/wiki/SUnit)


## microsoft.visualstudio.testtools.unittesting.assert
[C# AreEqual(Object, Object, String)](https://learn.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.areequal?view=visualstudiosdk-2022#microsoft-visualstudio-testtools-unittesting-assert-areequal(system-object-system-object-system-string))


```cs
Assert.AreEqual(expected, actual);
```

# Other Language Comparison

## C#
[C# AreEqual(Object, Object, String)](https://learn.microsoft.com/en-us/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.areequal?view=visualstudiosdk-2022#microsoft-visualstudio-testtools-unittesting-assert-areequal(system-object-system-object-system-string))


## Go
https://go.dev/doc/tutorial/add-a-test


## Rust
https://doc.rust-lang.org/book/ch11-01-writing-tests.html
