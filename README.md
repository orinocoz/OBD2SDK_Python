OBD2SDK_Python
==============

Python SDK for using the OBD2 cloud storage service

The OBD2 cloud storage service is available here: https://github.com/BizDevGeek/OBD2CloudStorage

This project contains an SDK that you can use to save OBD2 PID values. Use it with existing Python based OBD2 capture software such as the popular "pyobd". Any time a PID is logged from the computer, save it using the SDK so that it gets stored in the cloud storage service.  

The SDK stores the saved values in a local buffer. The buffer is a MongoDB collection. 

sync.py pulls records from the local buffer (MongoDB) and sends them to the API via JSON. It then removes them from the buffer. 

Installation

If you're installing the API to your own server, make sure that's setup first. You'll need the URL for the next step. EX: http://10.10.10.10/obdapi/

"python register.py" - Prompts you for the server URL (or use the author's for default) and for an email address and returns an API Key for you to use. It creates the config file below.

config.txt - Created by register.py. Contains the URL of the API server and your API Key for the SDK. 

Using the SDK

Copy the .py files to where your Python program is. 

In your Python program, add "import jnsdk". To save a PID each time you poll it from the OBD2 serial connection: jnsdk.SendPID(APIKey, PID, PIDValue)


