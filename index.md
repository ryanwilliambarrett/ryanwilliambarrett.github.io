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
from os import environ
os.environ["GOOGLE_APPLICATION_CREDENTIALS"]="C:\\Users\\xxx\\file.json"
```
Now we are set up complete the same tasks that are demonstrated in Google's Cloud Service web client, but from our local Jupyter Notebook. The following code is a replication from the tutorial and it imports the translate function from the google.cloud library, then it lists the available translation languages in Translate AI. Make sure to enter your own Project ID in the first line of this code. This Project ID can be found in the Google Cloud Dashboard, associated with your relevant Translate AI project.

```markdown
project_id = "xxxxxxx-xxxxx-xxxxxx"
assert project_id
parent = f"projects/{project_id}"
client = translate.TranslationServiceClient()

response = client.get_supported_languages(parent=parent, display_language_code="en")
languages = response.languages

print(f" Languages: {len(languages)} ".center(60, "-"))
for language in languages:
    print(f"{language.language_code}\t{language.display_name}")
```

The following example can be run locally on your script and will offer an example about how to translate a phrase. Here, I simply translate "Hello World!" to Hindi. Please study the code as it can be easily transformed with Pandas and loops to process vectorized operations that can translate a lot of data at once.

```markdown
project_id = "xxxxxxx-xxxxx-xxxxxx"
assert project_id
parent = f"projects/{project_id}"
client = translate.TranslationServiceClient()

sample_text = "Hello world!"
target_language_code = "hi" #translate to Hindi

response = client.translate_text(
    contents=[sample_text],
    target_language_code=target_language_code,
    parent=parent,
)

for translation in response.translations:
    print(translation.translated_text)
```

## Conclusion

Thank you for getting this far. If you follow this guide step-by-step you will be in good shape to translate data from one langauge to another using Python in Jupyter Notebook scripts that can easily be saved for personal use and shared. this process will help people in team settings progress together using single .ipynb scripts so long as the JSON file is shared.
