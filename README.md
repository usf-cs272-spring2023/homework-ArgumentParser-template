ArgumentParser
=================================================

![Points](../../blob/badges/points.svg)

For this homework, you will create a class to parse command-line arguments and store them in a map. For example, consider the following command-line arguments:

```
"-max", "false", "-min", "0", "-min", "-10", "hello", "-@debug", "-f", "output.txt", "-verbose"
```

In this case, `-max` `-min` `-@debug` `-f` and `-verbose` are all flags since they start with a `-` dash followed by at least 1 character that is not a digit or whitespace. The values are `false` `0` `hello` and `output.txt` since they do not start with a `-` dash character.

Note that `-10` is *not* a flag because the `-` dash is followed by a digit character. Instead it should be interpreted as a value representing a negative number.

Not all flags have values, not all values have associated flags, and values will be overwritten if there are repeated flags. For example, flag `-max` has value `false`. Flag `-min` has initial value `0`, but the value get replaced by the second occurrence of the `-min` flag with the value `-10` instead. The value `hello` has no associated flag and is ignored. The flags `-@debug` and `-verbose` have no associated value, but are still stored. The resulting map should look similar to:

```json
{
  "-max": "false",
  "-min": "-10",
  "-@debug": null,
  "-f": "output.txt",
  "-verbose": null
}
```

Avoid looping more often than necessary. For example, `numFlags()` should not require a loop.

## Hints ##

Below are some hints that may help with this homework assignment:

- The `@see` tag in the Javadoc comments often give hints on which methods are useful for implementing that method.

- Many methods may be implemented with one line of code if you are familiar with the methods in [HashMap](https://www.cs.usfca.edu/~cs272/javadoc/api/java.base/java/util/HashMap.html).

- The `parse(...)` method is easier if you use a traditional `for` loop instead of an enhanced `for` loop.

- To represent an individual character or symbol, use **code points** instead of the older and more limited `char` type. For example, use [`String.codePointAt(int)`](https://www.cs.usfca.edu/~cs272/javadoc/api/java.base/java/lang/String.html#codePointAt(int)) method when trying to access an individual character.

- To determine whether an individual character or symbol is a digit or whitespace, use the [Character.isDigit(int)](https://www.cs.usfca.edu/~cs272/javadoc/api/java.base/java/lang/Character.html#isDigit(int)) and [Character.isWhitespace(int)](https://www.cs.usfca.edu/~cs272/javadoc/api/java.base/java/lang/Character.html#isWhitespace(int)) methods. We will cover regular expressions later in the semester.

These hints are *optional*. There may be multiple approaches to solving this homework.

## Instructions ##

Use the "Tasks" view in Eclipse to find the `TODO` comments for what need to be implemented and the "Javadoc" view to see additional details.

The tests are provided in the `src/test/` directory; do not modify any of the files in that directory. Check the run details on GitHub Actions for how many points each test group is worth. 

See the [Homework Resources](https://usf-cs272-spring2023.github.io/resources/homework/) for additional details on homework requirements and submission.
