# Store API

This API exposes various functionalities of a sample ecommerce store.

Notice the following files/folders in this directory.

## SampleStore Directory ##
This is the API project that was generated from an Open API specification. This directory contains the actual API implementation along with any supporting API docs, images and custom mediation sequences.

### Documents Directory Structure
API docs are kept inside `SampleStore/Docs` folder. `docs.yaml` file in that directory keeps track of meta data about all API documents kept there. If you want to add/delete a document in this directory, you MUST update this file to reflect your changes.

An example entry in the docs.yaml file would look like this:
```yaml
 -
  type: HOWTO
  name: Quickstart.md
  summary: QSG
  sourceType: MARKDOWN
  visibility: API_LEVEL
  ```

The above entry declares that a file exists inside `SampleStore/Docs/InlineContents/Quickstart.md` has a type of `HOWTO` category and formatted as a Markdown file. You can provide a quick summary with `summary` field. Visibility is set to individual `API_LEVEL`.

## Authoring API Documents for a Given API

Before doing any document related operation, you have to clone this Git repository into your local workstation.

To do that, follow these commands.
```bash
git clone https://github.com/dunithd/apim-docs-demo.git store-api-docs
cd store-api-docs
```

Then open the cloned repository (`store-api-docs` in this case) with your favorite document editor (E.g VS Code, Typora, etc) and do the editing.

You may add/modify/remove documents and push your changes back to GitHub. The CI server will take the rest from there. It basically rebuilds the API project with artifacts and uses `apitctl` command line tool to import it to all the APIM environments.

### Adding a New API Document ###
1. If the file is a Markdown file, copy that into /Docs/InlineContents directory.
2. Add a new entry into docs.yaml. Actual file name and the name field of the entry MUST match.
3. Checkin your changes to GitHub.

### Modifying an Existing API Document 
1. Edit the required docs.
2. Push your changes back to GitHub

### Removing an Existing API Document 
1. Delete the document from `Docs/InlineContents` directory.
2. Remove the corresponding entry from `docs.yaml` file.
2. Push your changes back to GitHub