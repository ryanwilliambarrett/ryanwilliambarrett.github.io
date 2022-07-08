## Using Google Cloud Translate AI API from Jupyter Notebook

Using the API for Translation AI from Google Cloud is very powerful and it can help people complete incredible complicated tasks quickly. Abby Carey at Google has created a wonderful [tutorial](https://codelabs.developers.google.com/codelabs/cloud-translation-python3#0) that can train you to use Translation AI from Google's web host using Cloud Shell and Python. However, many tasks benefit from using Jupyter Notebook to create reproducable Python scripts to use and edit yourself or share with colleagues. This page is dedicated to detailing an example of using Translation AI and the Google Cloud API locally with Jupyter Notebook.

## First Steps

To begin, please initialize a Translation AI project using this [tutorial](https://codelabs.developers.google.com/codelabs/cloud-translation-python3#0). This step is imperative becauese it generates service account keys that we can download as a JSON file next. This will allow us the requisite credentials to create an environment variable for the Translate AI API in Jupyter Notebook for use.

## Downloading the credentials as a JSON file

Once you have followed the necessary steps in the Google tutorial and created a Translation AI project you must then do the following:

1. In the Google Cloud console, go to the [Service accounts page](https://console.cloud.google.com/iam-admin/serviceaccounts?walkthrough_id=iam--create-service-account-keys&_ga=2.44801696.523119782.1657215207-190287399.1657054577&_gac=1.92424559.1657282078.CjwKCAjwq5-WBhB7EiwAl-HEkt1rDGXmXFl6TVNspwwNWnJ4O9oOTIgRgPXb4bMjQ-mp8vbmSGw5QRoCeR0QAvD_BwE).
2. Select the project that you initialized for Translate AI.
3. On the Service accounts page, click the email address of the Translate AI account that you want to create a key for.
4. Click the Keys tab.
5. Click the Add key drop-down menu, then select Create new key.
6. Select JSON as the Key type and click Create.
Clicking Create downloads a service account key file. After you download the key file, you cannot download it again.

## Running the Translate AI API locally using Jupyter Notebook

You will need to install google.cloud because the Cloud Client Libraries are the recommended way to access Google Cloud APIs programmatically.

```markdown
pip install google.cloud
```
Next, you will need to set an environment variable so you can access the Google Cloud Translate API. This is done using your JSON file containing your credentials so set the path to the detailed location of this file.

```markdown
#set environment variable
os.environ["GOOGLE_APPLICATION_CREDENTIALS"]="C:\\Users\\xxx\\file.json"
```



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
