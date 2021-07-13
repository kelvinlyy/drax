## Post XML files to a server port

<br/>

### Step 1

<br/>

Check the `"xml_post_parser_config.json"` file for the configurations of the codes

<br/>

**Important fields**

`"server_port"`:

the location you want to post your files to

`"bearer_auth_key"`:

your Bearer Auth key to access DataCite REST API

`"prefix"`:

namespace of the DOIs you are using

`"schema_url"`:

schema for the DOIs

<br/>

**Folder names**

`"xml_folder"`:

the directory for your input XML files

`"json_folder"`:

the directory for your JSON envelopes to be stored at

`"processed_xml_folder"`:

the directory for your processed XML files

`"posted_json_folder"`:

the directory for your successfully posted JSON envelopes

`"post_failed_folder"`:

the directory for your JSON envelopes that failed to post

<br/>

### Step 2

<br/>

From the config file, use the value of `"xml_folder"` as the name to create a folder in the same directory

Store your xml files to be posted to the folder

<br/>

### Step 3

<br/>

Run the python script

```python
python xml_post_parser.py
```

The XML files will now begin to be encoded into JSON files and then posted to the server port

**Successfully posted** files will be stored at `"posted_json_folder"`

**Failed files** will be stored at `"post_failed_folder"`

<br/>

## Additional files

<br/>

`clear_folders.py`:

empty all folders after posting (except `"xml_src"`)

<br/>

`test_server.py`:

construct a dummy server using port 5000 in localhost

you can view the posted json files on http://localhost:5000/data

run `test_server.py` in one terminal and `xml_post_parser.py` in another


***Remember to change "server_port" in the config file to http://localhost:5000/***

