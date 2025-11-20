---
icon: brackets-square
---

# Scala

## XML Parsing

Example code for parsing the XML data:

```scala
package dev.hiquality.xmlparsing

import scala.xml.XML

@main def main() =
  val body = """<a href="https://www.google.com">Google</a>"""
  val xml  = XML.loadString(body)
  // Getting the text content of the tag...
  val linkText = (xml \\ "a").text
  // And the value of the attribute
  val linkUrl = (xml \\ "a") \@ "href"
  println(s"$linkText → $linkUrl")
```

## Scala-CLI

### Specifying Scala Version

```scala
//> using scala 3.7.4
```

### Dependencies directives

```scala
//> using dep org.scala-lang.modules::scala-xml:2.4.0
```

### Adding dependencies from command line

From what I found this is the only way to add the dependencies in REPL.
The directives do not work.

```sh
scala-cli console --dep org.scala-lang.modules::scala-xml:2.4.0
```
