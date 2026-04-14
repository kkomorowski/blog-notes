---
description: 'Link to official documentation: https://docs.asciidoctor.org/asciidoc/latest/'
icon: font-case
---

# AsciiDoc

## Table without borders

```adoc
[frame=none,grid=none]
|===
|Column 1 | Column 2
|Value 1 | Value 2
|Value 3 | Value 4
|===
```

## Table content formatting

### Center Text in a Single Cell

```adoc
|===
| Left column | Centered column
| Left-aligned text
^| Centered text
|===
```

### Formatting for each column

```adoc
[cols="^,<,>"]
|===
| Centered | Left | Right
| Mid      | Left | Right 
|===
```

### Center and span two columns

```adoc
|===
2+^| Centered and spans two columns
|===
```

### Code samples

```adoc
[source,bash]
----
asciidoctor tools/pass.adoc
----
```
