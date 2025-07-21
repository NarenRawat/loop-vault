# <center>Markdown — A Markup Language</center>

Markdown, created by John Gruber, is a **lightweight markup language** used to create formatted text using a plain-text editor such as Notepad, VSCode, etc.
It’s a bit ironic that _Markdown_ is actually a _markup_ language — so let’s unpack that term first.

---

# What is a Markup language?

A **markup language** defines the **structure and presentation** of a document using **tags**, **symbols**, or **special syntax**. It is not a programming language — it has no variables or logic — but rather a way to annotate content.

## Examples of Markup Languages

- **HTML** – Hyper Text Markup Language (used to create websites)
- **XML** – Extensible Markup Language (used for structured data)
- **Markdown** – Minimal syntax for formatted plain text
- **LaTeX** – A powerful markup and typesetting system used in academia and research
>  **Note:** LaTeX is often considered both a *markup language* and a *programming language*, due to its extensibility via macros and TeX scripting.

---

# What is Markdown?

Markdown was created in **2004** by John Gruber. It was designed to be as readable as plain text, while still allowing rich formatting such as **bold text**, *italic text*, links, images, and code blocks.

It is not a **WYSIWYG** (What You See Is What You Get) editor, like Microsoft Word, where formatting is applied through buttons and menus and the changes are visible immediately. Instead, it's a **WYSIWYM** (What You See Is What You Mean) language. For example, to make text bold, you type `**bold**` rather than clicking a bold button. This keeps your focus on content, not presentation.

Markdown is **stored as plain text** in files with a `.md` or `.markdown` extension. It is easily converted to HTML, making it ideal for web publishing and documentation workflows.

# Why Markdown?

- **Human-Readable**: Markdown files are clean and easy to read, even without being converted — no messy code or cluttered formatting.
- **Works Everywhere**: Since Markdown is just plain text, it's compatible with any computer, device, or platform.
- **Easy to Learn**: The syntax is straightforward — no complex tags or clunky formatting tools to slow you down.
- **Fast Writing**: Format text quickly without taking your hands off the keyboard.
- **Great with Version Control**: Works seamlessly with Git, making it easy to track changes and collaborate.
- **Converts to Other Formats**: Easily convert Markdown to HTML, PDF, LaTeX, EPUB, and more using tools like Pandoc.
- **Widely Supported**: Used by platforms like GitHub, Reddit, Discord, Obsidian, and many blogging tools.
- **Popular Across the Web**: Ideal for _documentation_, _blogs_, _wikis_, and _static site generators_ such as Jekyll, Hugo, and Docusaurus.

Markdown is a fast, flexible way to take notes, write web content, and create print-ready documents. It’s quick to learn and widely usable — from emails and documentation to websites and grocery lists.

# Markdown Editors

A **Markdown editor** is a text editor specifically designed to **write and preview Markdown**. These can include dedicated applications or general programs that support Markdown formatting.

The following websites are great for using Markdown online:
- [Dillinger](https://dillinger.io)
- [StackEdit](https://stackedit.io)

The following programs supports Markdown:
- VS Code
- Discord
- Obsidian
- Reddit

The [Markdown Guide](https://markdownguide.org) provides a more comprehensive [list of programs](https://www.markdownguide.org/tools/) that support Markdown.

# CommonMark Spec

The **CommonMark** is a formal specification — a strongly defined, and highly compatible, standardized version of Markdown.
Before **CommonMark**, the original Markdown lacked a formal specification. This led to many ambiguities and inconsistencies, causing different editors to parse the same Markdown text in different ways.

# Basic Syntax

## Headings

Heading are used to create titles and subtitles in a document.
There are 6 levels of headings supported by Markdown.

| Markdown | Output |
| :------- | :----- |
| \# Heading level 1 | <h1>Heading level 1</h1> |
| \## Heading level 2 | <h2>Heading level 2</h2> |
| \### Heading level 3 | <h3>Heading level 3</h3> |
| \#### Heading level 4 | <h4>Heading level 4</h4> |
| \##### Heading level 5 | <h5>Heading level 5</h5> |
| \###### Heading level 6 | <h6>Heading level 6</h6> |

Alternate syntax for H1 and H2:

| Markdown | Output |
| :------- | :----- |
| Heading level 1<br>=== | <h1>Heading level 1</h1> |
| Heading level 2<br>---- | <h2>Heading level 2</h2> |

**Note:**
* Number of == and -- does not matter
* Always put a space between the # symbol and the heading.
* Always put a blank line before and after a heading

## Paragraphs

Separate each paragraph with a blank line.

| Markdown | Output |
| :------- | :----- |
| This is paragraph one.<br><br>This is paragraph two.| <p>This is paragraph one.</p><p> This is paragraph two. |


**Note:** 
- Adding more than one blank line add any more than one blank line in the final output.
- Don't indent your paragraphs.
- To add more than one line, use `<br>` tag if your Markdown editor supports HTML, otherwise, you can put two trailing spaces or a `\`  at the end of a line to create a new line.

## HTML Character Entities

Reserved characters of HTML are known as HTML Character Entities.

| HTML Character Entities | Output |
| :-------: | :-----: |
| `&lt;` | &lt; |
| `&gt;` | &gt; |
| `&amp;` | &amp; |
| `Non-Breaking &nbsp;&nbsp; Space` | Non-Breaking&nbsp;&nbsp;Space |

## Bold

| Markdown | Output |
| :------- | :----- |
| This is \**bold** | This is **bold** |
| This is \__bold__ | This is __bold__ |
| This\**is**bold | This**is**bold |

**Note:**
- Don't do `This__is__bold`. Instead, use `This**is**bold` for compatibility reasons.

## Italics

| Markdown | Output |
| :------- | :----- |
| This is \*italics* | This is *italics* |
| This is \_italics_ | This is _italics_ |
| This\*is*italics | This*is*italics |

**Note:**
- Don't do `This_is_italics`. Instead, use `This*is*italics` for compatibility reasons.
- For using both, **bold** and *italics* at the same time, combine the markdown of both, like this:
    - **Markdown:** `This is ***bold and italics***`
    - **Output:** This is ***bold and italics***.

## Underline

Markdown does not officially support underlining a text. But if your Markdown editor supports HTML, you can use the `<u>` HTML tag for underline.

| Markdown | Output |
| :------- | :----- |
| This is `<u>`underline`</u>` | This is <u>underline</u> |

## Subscript and Superscript

Similar, to underline, you have to use HTML, tag to using subscript and superscript.

| Markdown | Output |
| :------- | :----- |
| `H<sub>2</sub>O` | H<sub>2</sub>O |
| `2<sup>10</sup> is 1024` | 2<sup>10</sup> is 1024 |

## Blockquote

Create a blockquote, by adding &gt; in front of a paragraph.

1. **Markdown:**
`> This is a Blockquote`
**Output:**
> This is a Blockquote

2. **Markdown:**
`> This is a Blockquote`
`>`
`> With multiple paragraph`
**Output:**
> This is a Blockquote
>
> With multiple paragraph

3. **Markdown:**
`> This is a Blockquote`
`>> With a nested Blockquote`
**Output:**
> This is a Blockquote
>> With a nested Blockquote

**Note:**
* You can also use other Markdown elements inside a blockquote

## Horizontal Rule

| Markdown | Output |
| :-------: | :-----: |
| `***` | <hr> |
| `___` | <hr> |
| `---` | <hr> |

## Ordered List

| Markdown | Output |
| :------- | :-----: |
| 1. First item<br>2. Second item<br>3. Third item<br>4. Fourth item | <ol><li>First item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ol> |
| <ol><li>First item</li><li>Second item</li><li>Third item<ol><li>Indented item</li><li>Indented item</li></ol></li><li>Fourth item</li></ol> | <ol><li>First item</li><li>Second item</li><li>Third item<ol><li>Indented item</li><li>Indented item</li></ol></li><li>Fourth item</li></ol> |

**Note:**
* You can use either dot "." or right parenthesis ")" as an ordered list marker like this, `1.` or `1)`
* Use minimum of two spaces for each indentation level.

## Unordered List

| Markdown | Output |
| :------- | :-----: |
| - First item<br>- Second item<br>- Third item<br>- Fourth item | <ul><li>Firs[]()t item</li><li>Second item</li><li>Third item</li><li>Fourth item</li></ul> |
| - First item<br>- Second item<br>- Third item<br>    - Indented item<br>    - Indented item<br>- Fourth item | <ul><li>First item</li><li>Second item</li><li>Third item<ul><li>Indented item</li><li>Indented item</li></ul></li><li>Fourth item</li></ul> |

**Note:**
- You can use either asterisk (\*), hyphen (-), or plus(+) as an unordered list marker.

## Links

| Link Type | Markdown | Output |
| :-------: | :------- | :----: |
| **Inline** | `[Click here](https://google.com)` | [Click here](https://google.com) |
| **Reference** | [Click here][google]<br>$\vdots$<br>[google]: https://google.com | [Click here](https://google.com) |

**Note:**
- URLs may not become links in some Markdown editors until enclosed in `<` and `>`.
- Some editors also support title for links which can be written inside quotations marks after the URL after one space.
    - `[Click here](https://google.com "google")`

## Images

You can insert images in your documents using an image URL.
The syntax is similar to link with just an exclamation mark (!) at the start.

| Markdown                                                                                                                                                               |                                                            Output                                                            |
| :--------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------: |
| `![Alt Text](https://upload.wikimedia.org/wikipedia/commons/thumb/`<br>`4/48/Markdown-mark.svg/263px-Markdown-mark.svg.png "Title")`                                   | ![Alt Text](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/263px-Markdown-mark.svg.png "Title") |
| `![Alt Text][md_img]`<br>$\vdots$<br>`[md_img]: https://upload.wikimedia.org/wikipedia/commons/thumb/`<br>`4/48/Markdown-mark.svg/263px-Markdown-mark.svg.png "Title"` | ![Alt Text](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Markdown-mark.svg/263px-Markdown-mark.svg.png "Title") |

**Note:**
- `Alt Text` is the text which will be displayed if for some reason the image is unable to load.


## Tables

Not one of the strongest feature of markdown, but you can make basic tables in Markdown.

**Markdown:**
```
| Header 1 | Header 2 | Header 3 |
| --- | --- | --- |
| Item 1 | Item 2 | Item 3 |
| Item 1 | Item 2 | Item 3 |
| Item 1 | Item 2 | Item 3 |
```

**Output:**

| Header 1 | Header 2 | Header 3 |
| --- | --- | --- |
| Item 1 | Item 2 | Item 3 |
| Item 1 | Item 2 | Item 3 |
| Item 1 | Item 2 | Item 3 |

**Alignment:** You can change alignment of columns by adding colons (:) around hyphens (-) in second row.

**Markdown:**
```
| Left Aligned | Center Aligned | Right aligned |
| :--- | :---: | ---: |
| Item 1 | Item 2 | Item 3 |
| Item 1 | Item 2 | Item 3 |
| Item 1 | Item 2 | Item 3 |
```

**Output:**

| Left Aligned | Center Aligned | Right aligned |
| :--- | :---: | ---: |
| Item 1 | Item 2 | Item 3 |
| Item 1 | Item 2 | Item 3 |
| Item 1 | Item 2 | Item 3 |

**Note:**
- Number of hyphens (-) does not matter.
- Creating tables in Markdown can be tedious, you can use [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) to create the table using GUI and then copying the Markdown formatted text into your document.

## Code

### Code Span

To display a text as a code, enclose it in backticks (`).

**Markdown:**

To check if gcc is installed properly, type \`gcc --version\` on the terminal and press \`Enter\`.

**Output:**

To check if gcc is installed properly, type `gcc --version` on the terminal and press `Enter`.

### Code Block or Fenced Code Block

If you want to add a code snippet inside your document, you can enclose the snippet inside three backticks (\`\`\`).

**Markdown:**

\`\`\`
\#include <stdio.h>

int main(void) {
&nbsp;&nbsp;&nbsp;&nbsp;printf("Hello, world\n");
&nbsp;&nbsp;&nbsp;&nbsp;return 0;
}
\`\`\`

**Output:**

```
#include <stdio.h>

int main(void) {
	printf("Hello, world\n");
	return 0;
}
```

**Syntax Highlighting:** Some Markdown editors also supports syntax highlighting for codes. You can use syntax highlighting by writing the name of the language used inside the code block after the starting three backticks (\`\`\`).

\`\`\`c
\#include <stdio.h>

int main(void) {
&nbsp;&nbsp;&nbsp;&nbsp;printf("Hello, world\n");
&nbsp;&nbsp;&nbsp;&nbsp;return 0;
}
\`\`\`

**Output:**

```c
#include <stdio.h>

int main(void) {
	printf("Hello, world\n");
	return 0;
}
```

### Indented Code Block

You can also start a code block by indenting the line with four spaces.

**Markdown:**
&nbsp;&nbsp;&nbsp;&nbsp;INPUT A;
&nbsp;&nbsp;&nbsp;&nbsp;IF (A MOD 2 EQUALS 0) THEN
&nbsp;&nbsp;&nbsp;&nbsp;OUTPUT "Even";
&nbsp;&nbsp;&nbsp;&nbsp;ELSE
&nbsp;&nbsp;&nbsp;&nbsp;OUTPUT "Odd";
&nbsp;&nbsp;&nbsp;&nbsp;ENDIF;

**Output:**

    INPUT A;
    IF (A MOD 2 EQUALS 0) THEN
    OUTPUT "Even";
    ELSE
    OUTPUT "Odd";
    ENDIF;


## Checklist or Task lists

Task lists (also referred to as _checklists_ and _todo_ lists) allow you to create a list of items with checkboxes. In Markdown applications that support task lists, checkboxes will be displayed next to the content. To create a task list, add dashes (`-`) and brackets with a space (`[ ]`) in front of task list items. To select a checkbox, add an `x` in between the brackets (`[x]`).

**Markdown:**

```
- [x] Task 1
- [ ] Task 2
- [ ] Task 3
```

**Output:**

- [x] Task 1
- [ ] Task 2
- [ ] Task 3

# Flavors of Markdown

The original Markdown, which was created by John Gruber was quite simple and minimal, offering only a limited features. As the Markdown grew in popularity, various platforms, tools, and developers created their own extended versions to support more features, these versions of Markdown are called *flavors*.
There are various Markdown flavors, so, it's your job to learn the whatever flavor of Markdown your application is using.

Here's a list of some Markdown flavors:

- **CommonMark:** Standard spec supported by many
- **GitHub Flavored Markdown (GFM):** Used by GitHub
- **Discord Markdown:** Used by Discord, chat-focused
- **Obsidian Markdown:** Used by Obsidian, support internal wikilinks, etc.


---

###  Recommended Resources

- [Gruber's Original Markdown Spec](https://daringfireball.net/projects/markdown/  ) — the canonical reference
- [The Markdown Guide](https://www.markdownguide.org/) — a modern, user-friendly reference
- [CommonMark Spec](https://spec.commonmark.org/) — the formal Markdown standard specification
- [Awesome Markdown](https://github.com/mundimark/awesome-markdown)  — A GitHub repository containing list of various tools and learning resources
- [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)