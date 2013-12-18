# Install

````
git clone git@github.com:ArnaudWopata/parse-upload.git
npm install
````

# Settings

`parse-upload` uses environment variables to get Parse AppId and APIKey.
The easiest way to use it is to write a `.env` file and use foreman to run `parse-upload`

````
PARSE_APP_ID=<APP_ID>
PARSE_APP_API_KEY=<APP_API_KEY>
````

# Usage

Typing `./parse-upload -h` will give you that output:

````
  Usage: parse-upload [options] [command]

  Commands:

    * [model] [attr] [path] [id]

  Options:

    -h, --help           output usage information
    -V, --version        output the version number
    -v, --verbose        moar logs
    -l, --label <label>  the attr value displayed when showing list (default is objectId)
````

## Parameters

* `model` ; mandatory ; the model you want to use (`User`, `Project`, `Todo`…)
* `attr` ; mandatory ; the attribute you want to attach the file to (`file`, `image`, …)
* `path` ; mandatory ; the file or directory to attach. Giving a directory will not attach sub-directories.
* `id` ; optionnal ; the target model instance `objectId`. If ommited, user is prompted which one to use

## Options

* `-v --verbose` will cluter your terminal with insightful informations
* `-l --label` the label to display when prompting instance if id is not given (`title`, `name`)

## Example

````
foreman run ./parse-upload -l title Item files images/item10

foreman run ./parse-upload -l name User avatar my-pic.jpg
````

