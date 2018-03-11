# First Alexa Skill

* Go [here](https://www.amazon.com/ap/register?openid.pape.max_auth_age=0&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&pageId=usflex&ignoreAuthState=1&openid.return_to=https%3A%2F%2Fwww.amazon.com%2F%3F_encoding%3DUTF8%26ref_%3Dnav_ya_signin&prevRID=4CN21QYBVVZRQBNGEQZ7&openid.assoc_handle=usflex&openid.mode=checkid_setup&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&prepopulatedLoginId=&failedSignInCount=0&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0) and create a new amazon.com account (if you'd like to use an existing one, skip this step).

  * The **Email** (user id) can be something like `team777@jupiter1.io`, it does not have to exist

* Go to https://developer.amazon.com and login with the account just created (or use an existing one). 

  * Fill the information of the registration wizard.

* Create an Alexa skill
  * Go to the Alexa Console https://developer.amazon.com/alexa/console/ask 
  * Click on the **Create Skill** button
  * Type **First Skill** as skill name and click **Next**
  * Select **Custom** and click the **Create skill** button
  * Click **JSON Editor** on the left bar
  * Paste the contents of facts-skill-interaction-model.json in the editor
  * Click the **Build Model** button (it will take a few minutes to build the model)

  * In the model paste the json found here https://raw.githubusercontent.com/alexa/skill-sample-nodejs-fact/en-US/InteractionModel.json (Not the whole document, but just the GetNewFactIntent node).
  * As endpoint use the ARN of the lambda function created below
