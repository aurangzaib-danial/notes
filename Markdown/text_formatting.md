
# Text Formatting

## Emphasis

### Italicize

We can make text italic by wrapping the text with one underscore on both sides

```md
  This is _some_ text. 
```

### Bold

Wrap text with two stars(*) on both sides

```md
  My name is **Sunny**.
```

**We can combine italicize and bold**

Just wrap the text with stars or underscores but in a way in which each can find its pair.

Order of stars or underscores do not matter.

But, better to keep bold signs out as to make it legible(clear enough to read).

```md
  **_sunny_**
```

### Strike through

Strike through a text by wrapping it with tildes(~).

```md
  ~~Scratch this~~
```

## Paragraphs

Everyline that has no formatting is considered as a paragraph.

We have to manually break lines for a newline in a paragraph, otherwise everything will be stacked.

## Line Breaks

We have to explicity create breaks inside a paragraph.

```md
  This is a paragraph.
  This is a new line but it will appear as part of the paragraph still.
  This allows us to keep our paragraph organized in our markdown file.
```

### Hard Breaks

Explicity creating a line break between two paragraphs

```md
  This is paragraph 1

  This is paragraph 2
```

### Soft Breaks

Add two spaces at the end of the first paragraph.

```md
 This is paragraph 1..
 This is paragraph 2
```
Replace dots with spaces. The extra spaces result in breaks between paragraphs. 

## Headers

Create different levels of headings for a document. 

Max six level of headings. According to the level of heading, prefix hashes.

Can't make headers bold because already bold but can italicize

```md
  # Heading 1
  ## _Heading 2_
  ### Heading 3
```

## Blockquotes

Quotes are great for referencing some one's saying. 

Prefix greater than sign > on the front of the saying.

```md
  > Markdown is great

```

Group multiple lines in a quote block by prefixing > on each line. 
Also on empty lines so it can know that the quote is continued, empty lines help us to create room.

```md
  > This is a quote
  >
  > This is the quote continued

```

## Horizontal rule or a line

We can create horizontal lines for separating sections.

Line breaks should be placed before and after the dashes(-).

```md
  Paragraph 1

  ---

  Paragraph 2
```



 
