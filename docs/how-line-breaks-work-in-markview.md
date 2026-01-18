# How Line Breaks Work in MarkView

This guide explains how **MarkView** handles line breaks in Markdown content and how to create intentional line breaks when needed.

## Overview

MarkView follows the **CommonMark standard** for line breaks, ***which matches GitHub's behavior***. Understanding how line breaks work is essential for formatting content correctly.

---

## How Line Breaks Work

To create line breaks, you need:

- **Two trailing spaces + newline, OR**
- **Explicit `<br>` tag, OR**
- **Double newline (blank line) to create a new paragraph**

---

### Test Case 1: Single Newlines (No trailing spaces)

- **Input**

```text
This is the first line.
This is the second line.
This is the third line.
```

- **Result**

This is the first line.
This is the second line.
This is the third line.

- **Expected**: All three lines should appear as one continuous line (spaces between them).

---

### Test Case 2: Double Newlines (Paragraph Break)

- **Input**

```text
This is paragraph one.

This is paragraph two.

This is paragraph three.
```

- **Result**

This is paragraph one.

This is paragraph two.

This is paragraph three.

- **Expected**: Creates separate paragraphs with proper spacing.

---

### Test Case 3: Two Trailing Spaces + Newline

- **Input**

```text
This is the first line with two spaces. * *  
This is the second line with two spaces. * *  
This is the third line.
```

> NOTE: Replace ** with actual spaces.

- **Result**

This is the first line with two spaces.  
This is the second line with two spaces.  
This is the third line.

- **Expected**: Creates hard line breaks between each line.

---

### Test Case 4: Explicit `<br>` Tags

- **Input**

```text
This is the first line.<br>
This is the second line.<br>
This is the third line.
```

- **Result**

This is the first line.<br>
This is the second line.<br>
This is the third line.

- **Expected**: Creates hard line breaks between each line.

---

### Test Case 5: Mixed Scenarios

- **Input**

```text
Here's a complex example:
Line 1 - single newline
Line 2 - single newline * *  
Line 3 - two trailing spaces

Line 4 - after blank line<br>
Line 5 - after br tag
```

> NOTE: Replace ** with actual spaces.

- **Result**

Here's a complex example:
Line 1 - single newline
Line 2 - single newline  
Line 3 - two trailing spaces

Line 4 - after blank line<br>
Line 5 - after br tag

**Expected**:

- Lines 1 and 2 merge together (single newlines become spaces)
- Line 3 has a break before it (due to trailing spaces on line 2)
- Line 4 starts a new paragraph (blank line creates paragraph break)
- Line 5 has a break before it (due to br tag)

---

### Test Case 6: Poetry/Lyrics (Common Use Case)

#### Without Hard Breaks

- **Input**

```text
Roses are red,
Violets are blue,
Sugar is sweet,
And so are you.
```

- **Result**

Roses are red,
Violets are blue,
Sugar is sweet,
And so are you.

#### With Trailing Spaces (Hard Breaks)

- **Input**

```text
Roses are red, * *
Violets are blue, * *
Sugar is sweet, * *
And so are you.
```

> NOTE: Replace ** with actual spaces.

- **Result**

Roses are red,  
Violets are blue,  
Sugar is sweet,  
And so are you.

#### With Explicit BR Tags

- **Input**

```text
Roses are red,<br>
Violets are blue,<br>
Sugar is sweet,<br>
And so are you.
```

- **Result**

Roses are red,<br>
Violets are blue,<br>
Sugar is sweet,<br>
And so are you.

> [!TIP]
> In MarkView, the first version appears as a single line. Use trailing spaces or `<br>` tags for poetry formatting.

---

### Test Case 7: Code Blocks (Should Not Be Affected)

```
Line 1
Line 2
Line 3
```

**Expected**: Line breaks in code blocks are always preserved.

---

### Test Case 8: Lists

Unordered list:

- Item 1
- Item 2
- Item 3

Ordered list:

1. First item
2. Second item
3. Third item

**Expected**: Lists always work correctly with proper line breaks.

---

## Related Documentation

- [CommonMark Specification](https://spec.commonmark.org/) - Official standard
- [GitHub Flavored Markdown](https://github.github.com/gfm/) - GitHub's extensions

## Related Issues

- [GitHub Issue #4](https://github.com/markview-app/support/issues/4) - Line breaks in blockquotes

---

## Summary

| Scenario | MarkView Behavior |
|----------|------------------|
| Single newline | Converted to space |
| Double newline (blank line) | New paragraph (`<p>`) |
| Two trailing spaces + newline | Creates `<br>` |
| Explicit `<br>` tag | Creates `<br>` |
| Code blocks | Line breaks preserved |
| Lists | Line breaks preserved |
