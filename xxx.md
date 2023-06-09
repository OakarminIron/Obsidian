# Markdown Cheat Sheet

Thanks for visiting [The Markdown Guide](https://www.markdownguide.org)!

This Markdown cheat sheet provides a quick overview of all the Markdown syntax elements. It can’t cover every edge case, so if you need more information about any of these elements, refer to the reference guides for [basic syntax](https://www.markdownguide.org/basic-syntax) and [extended syntax](https://www.markdownguide.org/extended-syntax).

## Basic Syntax

These are the elements outlined in John Gruber’s original design document. All Markdown applications support these elements.

### Heading

# H1  
## H2
### H3

### Bold

**bold text**

### Italic

*italicized text*

### Blockquote

> blockquote

### Ordered List

1. First item
2. Second item
3. Third item

### Unordered List

- First item
- Second item
- Third item


### Code `code`

### Horizontal Rule

---

### Link

[Markdown Guide](https://www.markdownguide.org)

## Extended Syntax

These elements extend the basic syntax by adding additional features. Not all Markdown applications support these elements.

### Table

| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |

### Fenced Code Block

```
{
  "firstName": "John",
  "lastName": "Smith",
  "age": 25
}
```

### Strikethrough
~~The world is flat.~~

### Task List

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media


(See also [Copying and Pasting Emoji](https://www.markdownguide.org/extended-syntax/#copying-and-pasting-emoji))

I need to highlight these ==very important words==.
This is an %%inline%% comment. 
%% 
This is a block comment. Block comments can span multiple lines.
%%

This is a simple footnote[^1].
[^1]: This is the referenced text. [^2]: Add 2 spaces at the start of each new line. This lets you write footnotes that span multiple lines. [^note]: Named footnotes still appears as numbers, but can make it easier to identify and link references.

### Image

![alt text](https://www.markdownguide.org/assets/images/tux.png)

YouTube link.   ![](https://www.youtube.com/watch?v=NnTvZWp5Q7o)


### Website   <iframe src="https://obsidian.md/"></iframe>

