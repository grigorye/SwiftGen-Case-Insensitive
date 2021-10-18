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

```
$ git diff
diff --git a/Strings+Generated.swift b/Strings+Generated.swift
index 915326b..f3891dd 100644
--- a/Strings+Generated.swift
+++ b/Strings+Generated.swift
@@ -10,12 +10,12 @@ import Foundation
 // swiftlint:disable explicit_type_interface function_parameter_count identifier_name line_length
 // swiftlint:disable nesting type_body_length type_name vertical_whitespace_opening_braces
 internal enum L10n {
-  /// Foo
-  internal static let a = L10n.tr("Localizable", "A")
   /// Bar %s
   internal static func a(_ p1: UnsafePointer<CChar>) -> String {
     return L10n.tr("Localizable", "a", p1)
   }
+  /// Foo
+  internal static let a = L10n.tr("Localizable", "A")
 }
 // swiftlint:enable explicit_type_interface function_parameter_count identifier_name line_length
 // swiftlint:enable nesting type_body_length type_name vertical_whitespace_opening_braces
```
