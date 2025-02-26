# sca-scripts
Python scripts that leverage the Veracode API to automate tasks or extend capabilities of Veracode Software Composition Analysis (SCA). These scripts are not officially supported by Veracode.

**Dependencies**

The following Python packages need to be installed:

* Veracode API Authentication library: [veracode-api-signing](https://pypi.org/project/veracode-api-signing/)
* Veracode API Helper library:  [veracode-api-py](https://pypi.org/project/veracode-api-py/)

**Authentication**

Option 1 - Save your Veracode API credentials in `~/.veracode/credentials` file as follows:

    [default]
    veracode_api_key_id = <YOUR_API_KEY_ID>
    veracode_api_key_secret = <YOUR_API_KEY_SECRET>

Option 2 - Save your Veracode API credentials in environment variables as follows:

    VERACODE_API_KEY_ID=<YOUR_API_KEY_ID>
    VERACODE_API_KEY_SECRET=<YOUR_API_KEY_SECRET>    

## generate_notice_file.py ##
A script that generates a License Notice file (sometimes called an Attribution Report) for an application that has been scanned by Veracode SCA. This helps to comply with open source licenses, which require documenting the terms under which open source components have been made available. Currently works with SCA upload scans. Plain text is the only file format supported at this time.

**Usage**

`generate_notice_file.py [-h] <arguments>`

Arguments:
* `-a` or `--app_name` `<APPLICATION>` - name of the application within Veracode (required).

NOTE: The generated file will be named "\<APPLICATION\>_notice.txt". 

**Example**
```
> python generate_notice_file.py --app_name "Verademo application"
```
