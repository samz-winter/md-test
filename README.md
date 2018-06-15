# Markdown Folder and Document Test

> **NOTE:**\
> • This is just a test of some Markdown in a document.\
> • Markdown can be used as long as the file type is .md

**Other Style Guides**
  - [Managing Postgres Views](http://www.postgresqltutorial.com/managing-postgresql-views/)
  - [Cool External Link](https://www.camdenrockland.com/moving-to-maine)
  
## Page Contents
  1. [Cool Document Description](#cool-document-description)
  1. [Example Query](#example-query)

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
  
count(distinct case when os.delivery_time between date_trunc('week', current_date)-'2week'::interval 
and date_trunc('week', current_date)-'1week'::interval then os.order_id end) as previous_week_orders,
```
**[back to top](#page-contents)**
