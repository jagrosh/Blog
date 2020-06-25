---
title: "Sending the results of Google Forms to Discord"
excerpt_separator: "<!--more-->"
categories:
  - Discord
tags:
  - discord
  - guide 
  - google-forms
---

# 1. Create a Google form
* For ease of editing the script later, it is recommended that the first question in the form ask for the user's Discord ID

# 2. Open the Script Editor
* Go to the 'Responses' tab
* Select 'View in Google Sheets'
* In sheets, select Tools > Script editor

<!--more-->

# 3. Paste the following script:
```js
////////////////////////////////////////////////////////////////////////////
// Instructions:                                                          //
// 1. Modify the webhook url and other variables below to suit your needs //
// 2. In the drop-down above, select 'initialize' and then run            //
// 3. Fill out your google form to see if it works                        //
// 4. Repeat step 2 any time you modify anything in this file             //
//                                                                        //
// Copyright 2020 jagrosh  |  Apache 2.0 License                          //
////////////////////////////////////////////////////////////////////////////


// this should be set to the URL that you want the form to post to
var webhook = "https://discordapp.com/api/webhooks/123456789012345678/wOahkTHX4daNiCewEbh00kUgOttheReiCtHaTYoUh4v3FoUndThIsS3crEToKyEah" 

// specify which columns (0 = A) to exclude from the full responses list
var skip = [0, 1]

// specify the content to appear above the embed (this example assumes column A is a timestamp and B is a user ID
function content(headers,values) { return "Form submitted by `" + values[1].replace(/`/gi,"'") + " ` at `" + values[0] +"`:" }


//////////////////////////////////////////////////////////////////////////////
// DO NOT MODIFY THE FUNCTIONS BELOW HERE UNLESS YOU KNOW WHAT YOU'RE DOING //
//////////////////////////////////////////////////////////////////////////////

// run this once after making a change to the script
function initialize() {
  var triggers = ScriptApp.getProjectTriggers();
  for (var t in triggers) {
    ScriptApp.deleteTrigger(triggers[t]);
  }
  ScriptApp.newTrigger("sendToDiscordWebhook")
    .forSpreadsheet(SpreadsheetApp.getActiveSpreadsheet())
    .onFormSubmit()
    .create();
}

// create and send the data from the row to discord
function sendToDiscordWebhook(row) {
  var payload = JSON.stringify(constructPayload(row.values));
  var options = {
    "method": "post",
    "contentType": "application/json",
    "payload": payload
  };
  var response = UrlFetchApp.fetch(webhook, options);
}

// construct the content from the values
function constructPayload(values) {
  var headers = getColumnNames();
  var fields = [];
  for(var i = 0; i < headers.length; i++) {
    if(skip.indexOf(i)!=-1 || !(values[i]))
      continue;
    fields.push({ "name": headers[i], "value": values[i], "inline": false });
  }
  return { "content": content(headers,values), "embeds": [{ "fields": fields }] };
}

// get column names from the spreadsheet
function getColumnNames() {
  var sheet = SpreadsheetApp.getActiveSheet();
  var headerRow = sheet.getRange("1:1");
  var headerRowValues = headerRow.getValues()[0];
  return headerRowValues;
}

// Copyright 2020 jagrosh
```
# 4. Create a webhook in the Discord channel you want the form results sent to

# 5. Modify the specified values in the script
* Copy the webhook URL from the webhook you created into the script, replacing the example url.
* Modify the skipped questions and output format, if desired

# 6. Initialize the script
* Select 'initialize' from the drop-down menu titled 'select function'
* Click the 'Run' button (Triangular "play" button)

# 7. Test the form
* Fill out and submit the form. The results should get relayed to the Discord channel.
