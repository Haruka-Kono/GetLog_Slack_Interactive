# GetLog_Slack_Interactive
Using Jupyter notebook, To Retrive logs in Slack channels and DMs due to limitation of accession for 90 days :( 

## Requirements
- python 3.x
- Jupyter notebook (JupyterLab)
- numpy
- pandas
- openpyxl
- slack_sdk
- slack_bolt (optional)

## Why Interactive?
- Can run with checking output
- Can custom construction (ex. fields selection)
- My poor programing skill

## Basic Construction
- retrive raw data (json format), shape them to excel format table, and export both of them (raw and excel)
- about shaped table:
  - containing fields for channel (not DM) are `type (message or thread)`, `thread_ts` `date (formatted from ts)`, `time (formatted from ts)`, `user (real_name)`, `text`, `reply_count`, `reply_users_count`, `topic`, `FileName`, `FileURL (url_private_download)`
  
  - containing fields for DM are `type (message or thread)`, `thread_ts` `date (formatted from ts)`, `time (formatted from ts)`, `user (real_name)`, `text`, `reply_count`, `reply_users_count`, `FileName`, `FileURL (url_private_download)`
  - separate channel logs into ones without replies ('type': message) and with replies ('type': thread)
  - messages in thread field are associated with replies by their parent messages
 
 ## How to Use
 Because I don't distribute to Slack App Directory, you have to create new slack app and install it to your workspace for get tokens. When you create app, please refer my App Manifest in `./app_manifest/manifest.json`.
