# SwiftGen-Case-Insensitive

This demonstrates https://github.com/SwiftGen/SwiftGen/issues/891.

Run `mint run swiftgen` multiple times. Note the difference in the output (re: Strings+Generated.swift):

```
$ mint run swiftgen
File written: Strings+Generated.swift
$ mint run swiftgen
File written: Strings+Generated.swift
$ mint run swiftgen
Not writing the file as content is unchanged
$ mint run swiftgen
Not writing the file as content is unchanged
```
