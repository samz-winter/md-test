<h1><img src="https://grubhub.zendesk.com/system/brands/0001/3323/grubhub-squarelogo-1455220281753_thumb.png">  Markdown Folder and Document Test</h1>

> **NOTE:**\
> • This is just a test of some Markdown in a document.\
> • Markdown can be used as long as the file type is .md

**Other Style Guides**
  - [Managing Postgres Views](http://www.postgresqltutorial.com/managing-postgresql-views/)
  - [Cool External Link](https://www.camdenrockland.com/moving-to-maine)
  - [Repository Query Storage](https://github.com/samz-winter/md-test/tree/master/query_storage)
  - [Repository Report Schedule](https://github.com/samz-winter/md-test/tree/master/report-schedule)

## Page Contents
1. [Introduction](#introduction)
1. [Naming Conventions](#naming-conventions)
1. [Folder Usage and Organization](#folder-usage-and-organization)
1. [Best Practices for Queries](#best-practices-for-queries)
1. [Miscellaneous ](#miscellaneous )
1. [Helpful Links](#helpful-links)

## Introduction
With the recent revision of our Tableau Server site folders, now is a good time to update the naming conventions and folder usage guidelines.

Keep in mind that anyone in the company who has access to the Care site can view our workbooks. As such we should be presenting our data in the cleanest and clearest way possible.

## Naming Conventions
<a name="naming--be-specific"></a><a name="1.1"></a>
**[1.1](#naming--be-specific) Be specific when naming all items.**
* Include the purpose of the report in the Workbook name so it's apparent at a glance what the Workbook contains and should be used for.
* Include an abbreviated purpose in the View names, so all Views are tied to their Workbooks even if someone is browsing Views only or shares just the View with an interested party. When possible make this the first part of the name so all Views are together if sorted alphabetically.
* Include similar naming for datasources and extracts where possible.
* Be aware of similar Workbooks that may include the same View names. When possible, adjust naming accordingly so there is no confusion.

```diff
- BAD:
Workbook:
  Care Overall
Views:
  Main
  Tickets
  Enterprise

+ GOOD:
Workbook:
  Agent Dashboard Reports for Care
Views:
  Agent Dashboard Weekly
  Agent Dashboard Monthly
  Manager Dashboard Monthly
```

## Cool Document Description
### New features ###
- Synchronize with Google Drive or Dropbox
- Publish directly on GitHub, Gist, Blogger, WordPress, Tumblr or any SSH server
- Google Drive multiple sign in

> **NOTE:**\
> Documents are stored in the browser's local storage, which means they are not shared between different browsers/computers. Furthermore, clearing your browser's data may delete all your local documents.
> Full access to Dropbox or Google Drive is required to be able to import any document in StackEdit. Imported documents are downloaded in your browser and are not transmitted to a server.


StackEdit is a free, open-source Markdown editor based on PageDown, the Markdown library used by Stack Overflow and the other Stack Exchange sites.

### StackEdit can:

 - Manage multiple Markdown documents online or offline
 - Export your documents in Markdown, HTML or PDF and format it using a template
 - Synchronize your Markdown documents in the Cloud
 - Edit existing Markdown documents from Google Drive, Dropbox and your local hard drive
 - Post your Markdown document on Blogger/Blogspot, WordPress, Tumblr
 - Publish your Markdown document on GitHub, Gist, Google Drive, Dropbox or any SSH server
 - Share a link to a Markdown document that renders it in a nice viewer
 - Show statistics about your document
 - Convert HTML to Markdown

### Features:

 - Real-time HTML preview with Scroll Link feature to bind editor and preview scrollbars
 - Markdown Extra/GitHub Flavored Markdown support and Prettify/Highlight.js syntax highlighting
 - LaTeX mathematical expressions using MathJax
 - WYSIWYG control buttons
 - Configurable layout
 - Theming support with different themes available
 - A la carte extensions
 - Offline editing
 - Online synchronization using Google Drive (multi-accounts) and Dropbox
 - One click publish on Blogger, Dropbox, Gist, GitHub, Google Drive, SSH server, Tumblr, WordPress
 
**[back to top](#page-contents)**
  
## Example Query
Use the following query to search all column names in a schema.
```sql
select
  table_schema, table_name, column_name, data_type
from
  information_schema.columns
where 
  column_name like '%cust%'
order by 
  1,2,ordinal_position asc
```
**[back to top](#page-contents)**
