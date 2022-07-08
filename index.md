## Using Google Cloud Translate AI API from Jupyter Notebook

Using the API for Translation AI from Google Cloud is very powerful and it can help people complete incredible complicated tasks quickly. Abby Carey at Google has created a wonderful [tutorial](https://codelabs.developers.google.com/codelabs/cloud-translation-python3#0) that can train you to use Translation AI from Google's web host using Cloud Shell and Python. However, many tasks benefit from using Jupyter Notebook to create reproducable Python scripts to use and edit yourself or share with colleagues. This page is dedicated to detailing an example of using Translation AI and the Google Cloud API locally with Jupyter Notebook.

## First Steps

To begin, please initialize a Translation AI project using this [tutorial](https://codelabs.developers.google.com/codelabs/cloud-translation-python3#0). This step is imperative becauese it generates service account keys that we can download as a JSON file next. This will allow us the requisite credentials to create an environment variable for the Translate AI API in Jupyter Notebook for use.

## Downloading the credentials as a JSON file



You can use the [editor on GitHub](https://github.com/ryanwilliambarrett/ryanwilliambarrett.github.io/edit/main/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

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

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/ryanwilliambarrett/ryanwilliambarrett.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
