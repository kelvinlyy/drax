# XML_postToREST

XML_postToREST is a Python program for posting DOIs metadata in XML format to DataCite REST API

<br/>

## Getting Started

`xml_post_parser.py` is the program you will call to do the task

It will call two python classes:
* `xml_encode.py`: encode XML files to JSON envelope

* `json_post.py`: post JSON envelopes to server port


<br/>

## Usage

Check the configuration file `xml_post_parser_config.json` and start configure your program:

<br/>


**Important fields**

```
"server_port":

the location you want to post your files to

"bearer_auth_key":

your Bearer Auth key to access DataCite REST API

"prefix":

namespace of the DOIs you are using

"schema_url":

schema for the DOIs
```


**Folder names**

```
"xml_folder":

the directory for your input XML files

"json_folder":

the directory for your JSON envelopes to be stored at

"processed_xml_folder":

the directory for your processed XML files

"posted_json_folder":

the directory for your successfully posted JSON envelopes

"post_failed_folder":

the directory for your JSON envelopes that failed to post

```
<br/>
----------------------------------------

Then from the config file, use the value of `"xml_folder"` as the name to create a folder in the same directory

Store your xml files to be posted to the folder

<br/>

Last, run `xml_post_parser.py`

``` python
python xml_post_parser.py
```

XML files will begin to be encoded into JSON files and then posted to the server port

**Successfully posted** files will be stored at `"posted_json_folder"`

**Failed files** will be stored at `"post_failed_folder"`

<br/>

## Additional file for testing

`tests/test_server.py`:

construct a dummy server at http://localhost:5000

<<<<<<< HEAD
you can post data to http://localhost:5000 and view the posted data on http://localhost:5000/data
=======
run `test_server.py` in one terminal and `xml_post_parser.py` in another


***Remember to change "server_port" in the config file to http://localhost:5000/***
>>>>>>> 40e4ec154fd62e1340fa852dfb1e626ccaaa75bb

***Remember to change "server_port" in the config file to http://localhost:5000/***
