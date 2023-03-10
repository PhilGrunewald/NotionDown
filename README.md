# NotionDown

Edit your Notion pages with your local editor of choice

Why you want to use this script:

You
1. are a nerd
2. love Notion
3. are a blue-sky thinker and don't trust clouds
4. spent an insane amount of time getting your editor (presumably vim) just right
5. want to keep editing your Notion pages locally

# What it does

Take a local markdown file and add it to a Notion page of your choice. Edit locally or in Notion and sync up or down. This isn't any clever merge - one is replaced with the other - so make sure to use it in the right direction.

Capability (so far):

- translate basic markdown into Notion blocks
- Headings, lists, inline formatting ... work both ways
- Check boxes can be represented in markdown with lines that start with '✓ ' (checked) or '✗ '/'o ' (unchecked)


# How to use

1. Clone repo and add `notiondown` to your executable paths.

2. Add the notion python library

```
pip install notion
```

3. Gain access to your Notion

Open Notion in your browser. In the developer section under cookies, find the `token_v2` and paste it into the text file `token_v2`.

4. Create a home for your pages

Create a new page in Notion where your new pages will go in the first instance. Have a look at the URL and copy the ID - that is the alpha-numercial code after the the page tilte and the '-'.
Paste this into the text file called `page_id`.

Note: You can then move your pages around in Notion. They still sync with your local file.

## Create a file locally

Create a markdown file and add it to Notion:

```
ndown write mymarkdownfile.md
```

Make changes in Notion and update your local file

```
ndown read mymarkdownfile.md
```

Note: local changes will get overwritten!

## Get an existing Notion page

To get a file you previously created in Notion, get the ID of that file (see 2) and run:

```
ndown get _theIDofYourNotionPage_
```

# How it works

When you get, read or write a Notion page, the page ID is stored as a hidden file, which has the same name as your markdown file, just leading with '.' and with the extension `.id`. This ID stays the same, even if you move the Notion page around. So organise your stuff locally or in Notion and keep read/writing.

Just be sure to keep the hidden id file and the markdown file in the same folder (I played with storing the id in the file name or somewhere inside the file - both are ugly options, but happy to revise).
