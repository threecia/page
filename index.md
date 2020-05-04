## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/threecia/page/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

## LLVM study notes
### attribute語法
attribute本身以這種形式出現: `__attribute__((name1, name2(arg1, arg2, arg3), name3))`
[reference](https://gcc.gnu.org/onlinedocs/gcc-4.9.1/gcc/Attribute-Syntax.html#Attribute-Syntax)
### `__attribute__((noreturn))`
noreturn 的用意是標記callee function 沒有return 動作, 這個attribute較常被compiler設計成警告noreturn之後的user code
### `__attribute__(())`
noreturn 的用意是標記callee function 沒有return 動作, 這個attribute較常被compiler設計成警告noreturn之後的user code

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/threecia/page/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
