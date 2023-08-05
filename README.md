# Notion API & Python SDK Tutorial for Beginners

| How to use Notion's API and Python SDK to fully control your Notion workspace.

[Notion's API](https://developers.notion.com/)

[Notion's Python SDK](https://github.com/ramnes/notion-sdk-py)

***Create a new Notion Integration: https://www.notion.so/my-integrations
    - Click "New Integration" button
    - Give your integration a name & Create the integration
    - Copy your secret key - this is your Notion API key/Token - If you're new to API keys, its essentally as good as your login information so DO NOT SHARE IT. Should your API key become compramised, simply delete your integration and redo this step. 


## Overview

The SDK offers us some simple ways to interact with Notion's API. 

Some endpoints require a json object that would be the definition for creating new, or updating objects like Databases, Pages, or Page Blocks.

- https://developers.notion.com/reference/block
- https://developers.notion.com/reference/page 
- https://developers.notion.com/reference/database

## API Reference

Each endpoint function can be categorized into the following objects:

### 1. Search
All of Notion
notion.search("Optional - search keywords")['results'] -> *Returns a list of all databases and pages.*

### 2. Databases
notion.databases.query(database_id) -> *Query/search a database's records, by database_id*

notion.databases.retrieve(database_id) -> *Retrieve information about a database, by database_id*

notion.databases.create(parent_id, database_object) -> *Creates a new database*

notion.databases.update(database_id, database_object) -> *Update a database*

### 3. Pages
notion.pages.create(parent_id, page_object) -> Create a new page, by parent_id (database_id or page_id)

notion.pages.retrieve(page_id) -> Retrieve a page's details by page_id

notion.pages.update(page_id, page_object) -> Update a page_id, requires a page object.

### 4. Users 
notion.users.list() -> *List all users*

notion.users.retrieve(user_id) -> *Retrieve a specific user, by user_id*

notion.users.me() -> *Return the authenticated user*

### 5. Blocks (on a page)
notion.blocks.retrieve(block_id or page_id) -> *Return the blocks from a page_id or block_id. 

notion.blocks.update(block_id) -> *Update a block, by block_id. Requires a Block object.*

notion.blocks.delete(block_id) -> *Delete a block, by block_id*

### 6. Block Children
notion.blocks.children.append(block_id, child_object) -> *Add blocks to an existing block_id. Requres a Block object.*

notion.blocks.children.list(block_id) -> *List the blocks that are children of a block, or page.*