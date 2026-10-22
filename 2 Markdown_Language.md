# Markdown Language

**Used by developers for documentation and comments.**

**File Extension:** `file_name.md`

**Where Markdown is used:**
- `README.md` files on GitHub
- **Markdown cells** in Jupyter Notebooks (`.ipynb`)
- Documentation, notes, blogs, and comments
- Chat apps and forums (GitHub issues, Discord, Reddit, Stack Overflow)

## Table of Content
- [Markdown Language](#markdown-language)
  - [Table of Content](#table-of-content)
  - [Preview Markdown in VS Code](#preview-markdown-in-vs-code)
  - [Headings](#headings)
  - [Paragraphs and Line Breaks](#paragraphs-and-line-breaks)
  - [Text Formatting](#text-formatting)
  - [Blockquotes](#blockquotes)
  - [Lists](#lists)
    - [Bullet List](#bullet-list)
    - [Bullet \& Numbered List](#bullet--numbered-list)
    - [Checkbox](#checkbox)
  - [Links](#links)
    - [Table of Content](#table-of-content-1)
    - [Links to Other Files](#links-to-other-files)
  - [Images](#images)
  - [Code](#code)
    - [Inline Code](#inline-code)
    - [Code Block](#code-block)
  - [Tables](#tables)
  - [Escaping Special Characters](#escaping-special-characters)
  - [Math Equations (LaTeX)](#math-equations-latex)
  - [GitHub Alerts](#github-alerts)
  - [Diagrams (Mermaid)](#diagrams-mermaid)
  - [Footnotes](#footnotes)
  - [Emoji](#emoji)
  - [Markdown in Jupyter Notebooks](#markdown-in-jupyter-notebooks)
  - [Create a Table of Content Automatically](#create-a-table-of-content-automatically)
    - [Author](#author)

---

## Preview Markdown in VS Code

| Shortcut | Action |
|---|---|
| `Ctrl + Shift + V` | Open preview in a new tab |
| `Ctrl + K` then `V` | Open preview **side by side** (live update while typing) |

---

## Headings

Use `#` followed by a **space**. More `#` = smaller heading (6 levels).

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```


## Paragraphs and Line Breaks

- A **blank line** starts a new paragraph.
- Pressing `Enter` once does **not** create a new line in the output.

For a **line break** (new line without a new paragraph), use one of these:

| Method | Write |
|---|---|
| Backslash at the end of the line | `Line 1\` |
| Two spaces at the end of the line | `Line 1␣␣` |

```text
Line 1\
Line 2
```

Result:

Line 1\
Line 2

---

## Text Formatting

| Style | Write | Result |
|---|---|---|
| Bold | `**Text**` or `__Text__` | **Text** |
| Italic | `*Text*` or `_Text_` | *Text* |
| Bold & Italic | `***Text***` or `___Text___` | ***Text*** |
| Strikethrough | `~~Text~~` | ~~Text~~ |
| Inline code | `` `Text` `` | `Text` |
| Highlight (HTML) | `<mark>Text</mark>` | <mark>Text</mark> |
| Subscript (HTML) | `H<sub>2</sub>O` | H<sub>2</sub>O |
| Superscript (HTML) | `x<sup>2</sup>` | x<sup>2</sup> |
| Underline (HTML) | `<ins>Text</ins>` | <ins>Text</ins> |

> **Tip:** Use `*` instead of `_` inside words: `data**science**` works, `data__science__` does not.

---

## Blockquotes

Use `>` before the text. Blockquotes are good for notes, tips and important points.

```markdown
> This is a blockquote.
> It can have many lines.\
> Use `\` for a line break inside it.
```

> This is a blockquote.
> It can have many lines.\
> Use `\` for a line break inside it.

**Nested blockquotes** use `>>`:

```markdown
> Main quote
>> Nested quote
```

> Main quote
>> Nested quote

**Other Markdown inside blockquotes** also works:

```markdown
> ### Heading inside a quote
> - **Bold** bullet point
> - `code` bullet point
```

> ### Heading inside a quote
> - **Bold** bullet point
> - `code` bullet point

---

## Lists

### Bullet List

Use `-`, `*` or `+` followed by a space. Indent with `Tab` (or 2–4 spaces) for sub-bullets; `Shift + Tab` moves back.

```markdown
- Python
  - NumPy
  - Pandas
    - DataFrame
    - Series
```

### Bullet & Numbered List

```markdown
- Install VS Code
- Install Git
- Install Miniconda
   1. Download the installer
   2. Run it
```

### Checkbox

```markdown
- [x] Learn Markdown
- [x] Learn Git
- [ ] Learn ML
```

- [x] Learn Markdown
- [x] Learn Git
- [ ] Learn ML


## Links

| Type | Write |
|---|---|
| Basic link | `[Link Text](https://github.com)` |
| Link with hover title | `[GitHub](https://github.com "Go to GitHub")` |
| Plain URL | `<https://github.com>` |
| Email | `<name@example.com>` |
| Reference link | `[GitHub][gh]` and somewhere below: `[gh]: https://github.com` |


### Table of Content

```markdown
[Go to Tables](#tables)
[Go to Text Formatting](#text-formatting)
```

Rules to make the heading link (`#...`):
1. Use **lowercase** letters.
2. Replace **spaces** with `-`.
3. Remove special characters like `.` `,` `(` `)` `?` `:` `&`.

| Heading | Link |
|---|---|
| `## Text Formatting` | `#text-formatting` |
| `## Math Equations (LaTeX)` | `#math-equations-latex` |

### Links to Other Files

```markdown
[Setup notes](setting_up_env.md)
[Image file](images/plot.png)
```

If the file name has **spaces**, wrap the path in `< >` or replace each space with `%20`:

```markdown
[Setup notes](<1 setting_up_env.md>)
[Setup notes](1%20setting_up_env.md)
```

Example: [Setting Up Environment](<1 setting_up_env.md>)

---

## Images

Same as a link, but with `!` in front. The `!` tells Markdown to **display** the image.

```markdown
![Alt text](image.png)
![Alt text](images/plot.png)
![Python Logo](https://www.python.org/static/community_logos/python-logo.png)
```

- **Alt text** is shown if the image cannot load (and is read by screen readers).
- The path can be a **local file** or an **online link**.

**Image with a link** (click the image to open the link):

```markdown
[![Python Logo](https://www.python.org/static/community_logos/python-logo.png)](https://www.python.org)
```

**Resize or center an image** — use HTML:

```html
<img src="image.png" alt="My Image" width="300">

<div align="center">
  <img src="image.png" alt="My Image" width="300">
</div>
```

---

## Code

### Inline Code

Wrap the code in single backticks: `` `print(x)` `` → `print(x)`

If the code itself contains a backtick, wrap it with double backticks: ``` `` `code` `` ```

### Code Block

Use three backticks ```` ``` ```` before and after the code. Write the **language name** after the opening backticks for **syntax highlighting**.

````markdown
```python
name = "Shehzad"
print(f"Hello, {name}")
```
````

```python
name = "Shehzad"
print(f"Hello, {name}")
```

Common language names: `python`, `bash`, `powershell`, `sql`, `json`, `html`, `css`, `javascript`, `r`, `yaml`, `markdown`, `text`.

**Show changes** with the `diff` language:

````markdown
```diff
- old_line = 1
+ new_line = 2
```
````

```diff
- old_line = 1
+ new_line = 2
```

> **Tip:** To show a code block that contains ```` ``` ````, wrap it with **four** backticks ```` ```` ````.

---

## Tables

Use `|` to separate columns and `---` to separate the header row.

```markdown
| Name | Age | City |
|---|---|---|
| Ali | 22 | Lahore |
| Sara | 25 | Karachi |
```

| Name | Age | City |
|---|---|---|
| Ali | 22 | Lahore |
| Sara | 25 | Karachi |

**Column alignment** with `:`

```markdown
| Left | Center | Right |
|:---|:---:|---:|
| A | B | 100 |
| AAA | BBB | 5 |
```

| Left | Center | Right |
|:---|:---:|---:|
| A | B | 100 |
| AAA | BBB | 5 |

> **Tips:**
> - Columns do not need to line up in the source text.
> - You can use **bold**, `code` and [links](#tables) inside cells.
> - To write a `|` inside a cell, use `\|`.
> - For a line break inside a cell, use `<br>`.

---

## Escaping Special Characters

To show a Markdown symbol as normal text, put a backslash `\` before it.

| Write | Result |
|---|---|
| `\*not italic\*` | \*not italic\* |
| `\# not a heading` | \# not a heading |
| `\[not a link\]` | \[not a link\] |
| `1\. not a list` | 1\. not a list |

Characters you can escape: `` \ ` * _ { } [ ] ( ) # + - . ! | ``

---

## Math Equations (LaTeX)

Works in **Jupyter Notebooks**, **GitHub**, and VS Code preview.

| Type | Write | Result |
|---|---|---|
| Inline math | `$E = mc^2$` | $E = mc^2$ |
| Block math | `$$ ... $$` | Centered on its own line |

```markdown
$$
\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i
$$
```

$$
\bar{x} = \frac{1}{n} \sum_{i=1}^{n} x_i
$$

Common LaTeX symbols:

| Write | Meaning | Write | Meaning |
|---|---|---|---|
| `x^2` | Power $x^2$ | `x_i` | Subscript $x_i$ |
| `\frac{a}{b}` | Fraction $\frac{a}{b}$ | `\sqrt{x}` | Root $\sqrt{x}$ |
| `\sum_{i=1}^{n}` | Sum $\sum_{i=1}^{n}$ | `\int_a^b` | Integral $\int_a^b$ |
| `\alpha, \beta, \mu, \sigma` | $\alpha, \beta, \mu, \sigma$ | `\pi, \theta, \lambda` | $\pi, \theta, \lambda$ |
| `\le, \ge, \ne, \approx` | $\le, \ge, \ne, \approx$ | `\infty` | $\infty$ |
| `\times, \cdot, \pm` | $\times, \cdot, \pm$ | `\rightarrow` | $\rightarrow$ |
| `\hat{y}`, `\bar{x}` | $\hat{y}, \bar{x}$ | `\mathbb{R}` | $\mathbb{R}$ |

---

## GitHub Alerts

Special colored blockquotes (shown on **GitHub**):

```markdown
> [!NOTE]
> Useful information.

> [!TIP]
> Helpful advice.

> [!IMPORTANT]
> Key information.

> [!WARNING]
> Needs attention.

> [!CAUTION]
> Possible risk or bad result.
```

> [!NOTE]
> Useful information.

> [!TIP]
> Helpful advice.

> [!WARNING]
> Needs attention.

---

## Diagrams (Mermaid)

GitHub (and VS Code with a Mermaid extension) can draw diagrams from text:

````markdown
```mermaid
flowchart LR
    A[Collect Data] --> B[Clean Data]
    B --> C[Train Model]
    C --> D[Evaluate]
    D --> E[Deploy]
```
````

```mermaid
flowchart LR
    A[Collect Data] --> B[Clean Data]
    B --> C[Train Model]
    C --> D[Evaluate]
    D --> E[Deploy]
```


## Footnotes

Works on GitHub:

```markdown
Pandas is built on NumPy.[^1]

[^1]: NumPy provides the fast array operations underneath Pandas.
```

Pandas is built on NumPy.[^1]

[^1]: NumPy provides the fast array operations underneath Pandas.



## Emoji

- Copy and paste the emoji directly: ✅ 🚀 📊 

## Markdown in Jupyter Notebooks

A notebook has two main cell types: **Code** and **Markdown**.

| Shortcut (command mode, press `Esc` first) | Action |
|---|---|
| `M` | Change cell to **Markdown** |
| `Y` | Change cell to **Code** |
| `Shift + Enter` | Run the cell (renders the Markdown) |
| `Enter` / double-click | Edit a Markdown cell |
| `A` / `B` | Insert a cell above / below |

Use Markdown cells to explain:
- **What** the next code does
- **Why** a step is needed
- **Results** and conclusions
- **Formulas** with LaTeX (`$...$`)

---

## Create a Table of Content Automatically

**Automatic method** (with the **Markdown All in One** extension):
1. Install it: `Ctrl + Shift + X` → search **Markdown All in One** → **Install**.
2. Place the cursor where you want the table of content.
3. Press `Ctrl + Shift + P` → type **Markdown All in One: Create Table of Contents** → `Enter`.
4. It **updates automatically** when you save the file.

---
[**Next Lesson `Git and GitHub`**](<3 git_and_github.md>)


### Author
- **[MUHAMMAD SHEHZAD](https://github.com/dbdmlabs)**
