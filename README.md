# Weasy - Weak signals made easy
This is a project tryng to get weak signals from team.
It consists of :
 - Getting team mood
 - Getting team comments

## Setting up a team mood
You will need a gmail account in order to do that.
Follow thoses steps to create an account
### Setting up the form

TODO

### Setting up the daily mail

go to 

Insert the following code, changing all variables

```javascript
function sendFormEmail() {
    var toEmailAddress = "<YOUR_TEAM@mail.com>";
    var htmlMessage = HtmlService.createHtmlOutputFromFile("TeamMood.html").getContent();
    var subject = "Beyond Team Mood";
    var message = "Hey, please tell us how you feel. It's important for us to gather this to be able to react properly";
    MailApp.sendEmail(toEmailAddress, subject, message, {
      htmlBody: htmlMessage
    });
}


function createTriggers() {
   var days = [ScriptApp.WeekDay.MONDAY, ScriptApp.WeekDay.TUESDAY,
               ScriptApp.WeekDay.WEDNESDAY, ScriptApp.WeekDay.THURSDAY,                                            
               ScriptApp.WeekDay.FRIDAY];
   for (var i=0; i<days.length; i++) {
      ScriptApp.newTrigger("sendFormEmail")
               .timeBased().onWeekDay(days[i])
               .atHour(16).create();
   }
}
```


You can see a working example here : [https://docs.google.com/spreadsheets/d/1KCWLYyU49Tmf2zsnl302bfmM608GQ3hnbZAbliObnWc/edit?usp=sharing]



### Setting up a new web page
Copy the code from index.html then change the params. Host it wherever you can and here we go.

There is no need for a back end server as Google is used as back end. You can event just checkout the project and launch it from your computer.

## Contribute

Here is how you can participate :
 - Set it up in you team
 - Reference the project or talk about it
 - Send your opinion through github
 - Submit your changes throuh pull requests

## Changelog
### Version 0.0.1
-No released yet
