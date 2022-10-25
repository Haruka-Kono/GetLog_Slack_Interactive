# GetLog_Slack_Interactive
Using Jupyter notebook, To Retrive Logs in Slack channels and DMs as xlsx (shaped) and json (raw data) format due to 90-day limitation (wonderful!) for accession logs by Slack team :( 

## Requirements
- python 3.x
- Jupyter notebook (JupyterLab)
- numpy
- pandas
- openpyxl (now I choose xlsx, not csv due to construction of formatted file and encoding)
- slack_sdk
- slack_bolt (optional)

## Why Interactive?
- Can run script with checking output
- Can custom construction (ex. fields selection)
- **My poor programing skill...**

## Basic Construction
- retrive raw data (json format), shape them to xlsx table, and export both of them (raw as json and xlsx)
- about shaped table
  - containing fields for channel (not DM): `type (message or thread)`, `thread_ts` `date (formatted from ts)`, `time (formatted from ts)`, `user (real_name)`, `text`, `reply_count`, `reply_users_count`, `topic`, `FileName`, `FileURL (url_private_download)`
  
  - containing fields for DM: `type (message or thread)`, `thread_ts` `date (formatted from ts)`, `time (formatted from ts)`, `user (real_name)`, `text`, `reply_count`, `reply_users_count`, `FileName`, `FileURL (url_private_download)`
  - separate channel logs into ones without replies ('type': message) and with replies ('type': thread)
  - messages in thread field are associated with replies by their parent messages
 
 ## How to Use
 Because I don't distribute to Slack App Directory, if you want to use this tool, you have to create new slack app and install it to your workspace for getting tokens. For creating app, please refer my App Manifest in `./app_manifest/manifest.json`.
