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
- Can custom construction what you need (ex. fields selection)
- ~**My poor programing skill...**~

## Basic Construction
- retrive raw data (json format), shape them to xlsx table, and export both of them (raw as json and xlsx)
- about shaped table
  - containing fields for channel (not DM): `type (message or thread)`, `thread_ts` `date (formatted from ts)`, `time (formatted from ts)`, `user (real_name)`, `text`, `reply_count`, `reply_users_count`, `topic`, `FileName`, `FileURL (url_private_download)`
  
  - containing fields for DM: `type (message or thread)`, `thread_ts` `date (formatted from ts)`, `time (formatted from ts)`, `user (real_name)`, `text`, `reply_count`, `reply_users_count`, `FileName`, `FileURL (url_private_download)`
  - separate channel logs into ones without replies ('type': message) and with replies ('type': thread)
  - messages in thread field are associated with replies by their parent messages
 
 ## How to Use
 Because I don't distribute to Slack App Directory, if you want to use this tool, you have to create new slack app and install it to your workspace for getting tokens. For creating app, please refer my App Manifest in `./app_manifest/manifest.json`.

## Future Plans
- Custom scripts for applied to Google Colab

## Appendix
 Actually, I created this tool for me and my labmates (My lab use free-plan-Slack workspace which is created per one FY. Previously, limitations of old free plan were enough for us because they did not depend on date and our team was small, < 20 members. However, Slack, an awesome team has set date-dependency-plan. I think 90 days are so looooooooooong!... no, no, small team like us may have huge affect. Who understand what they want to do for us?)
 
 Sorry for making my long talk (longer than slack limitation!), well... OK, I have remember that I was planning to explain that this tool is minimum function for my lab's WS. So feel free to customize it what you need! And if you want to send feedback for me, please send messages in issues. 
