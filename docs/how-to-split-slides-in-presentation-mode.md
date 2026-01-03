# How to Split Slides in Presentation Mode

This guide explains how to structure your Markdown documents for optimal presentation in **MarkView's Presentation Mode**.

## Overview

MarkView's Presentation Mode can automatically detect how to split your Markdown content into slides using three different strategies:

1. **Horizontal Rule Delimiter (`---`)** - Most common and recommended
2. **H1 Headings (`#`)** - Good for chapter-based presentations
3. **H2 Headings (`##`)** - Good for section-based presentations
4. **Auto (Single Slide)** - Fallback when no delimiters are found

## Method 1: Horizontal Rule Delimiter (Recommended)

The most flexible and widely-used method is to use horizontal rules (`---`) to separate slides.

### Example

```markdown
# Welcome to My Presentation

This is the first slide with an introduction.

---

## Slide 2: Key Points

- Point 1
- Point 2
- Point 3

---

## Thank You

Questions?
```

### Benefits

- ✅ Most explicit and clear
- ✅ Works with any heading level
- ✅ Easy to add/remove slides
- ✅ Compatible with most Markdown editors

### Tips

- Use exactly three dashes: `---`
- Add blank lines before and after the delimiter
- Each section between `---` becomes one slide

## Method 2: H1 Headings

If your document has multiple top-level headings (at least 3), MarkView will automatically split at each `#` heading.

### Example

```markdown
# Introduction

Welcome to the presentation!

# Problem Statement

What are we trying to solve?

# Solution

Here's our approach...

# Conclusion

Summary and next steps
```

### When to Use

- ✅ Chapter-based presentations
- ✅ High-level overview documents
- ✅ Already structured with H1 headings

### Limitations

- ⚠️ Requires at least 3 H1 headings
- ⚠️ Less flexible than `---`

## Method 3: H2 Headings

If you have multiple `##` headings (at least 3) but fewer than 3 `#` headings, MarkView will split at each H2.

### Example

```markdown
# My Presentation

## Section 1

Content for section 1

## Section 2

Content for section 2

## Section 3

Content for section 3

## Section 4

Content for section 4
```

### When to Use

- ✅ Section-based presentations
- ✅ Documents with one main title
- ✅ Subsection-focused content

### Limitations

- ⚠️ Requires at least 3 H2 headings
- ⚠️ H1 headings must be fewer than 3

## Common Issues and Solutions

### Issue: "No slide delimiters found"

- **Cause:** Document doesn't have enough headings or `---` delimiters.

- **Solution:** Add `---` between slides or increase the number of H1/H2 headings.

### Issue: "Large code blocks may not fit"

- **Cause:** Code blocks with more than 20 lines.

- **Solution 1:** Split into multiple slides

- **Solution 2:** Extract key snippets only

### Issue: "Document is very long"

- **Cause:** Document has more than 500 lines.

- **Solution:** Break into multiple presentations
  - Create separate files for each chapter/section
  - Link between presentations
  - Focus on key points only

## Quick Reference

| Strategy | Trigger | Example |
|----------|---------|---------|
| **Delimiter** | `---` present | `content\n---\ncontent` |
| **H1 Split** | ≥3 H1 headings | `# One\n# Two\n# Three` |
| **H2 Split** | ≥3 H2 headings | `## A\n## B\n## C` |
| **Auto** | None of above | Single slide |

## Template for New Presentations

```markdown
# [Presentation Title]

[Your name or subtitle]

---

## Agenda

1. Topic 1
2. Topic 2
3. Topic 3

---

## Topic 1

[Content]

---

## Topic 2

[Content]

---

## Topic 3

[Content]

---

## Summary

- Key takeaway 1
- Key takeaway 2
- Key takeaway 3

---

## Thank You

Questions?

[Contact information]
```

## Keyboard Shortcuts

Once in Presentation Mode:

- `→` / `Space` / `PageDown` - Next slide
- `←` / `Backspace` / `PageUp` - Previous slide
- `Home` / `End` - First/Last slide
- `1-9` - Jump to slide number
- `F` / `F11` - Fullscreen
- `P` - Auto-play toggle
- `?` - Show help
- `Esc` - Exit presentation
