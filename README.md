# First Alexa Skill

* Go [here](https://www.amazon.com/ap/register?openid.pape.max_auth_age=0&openid.identity=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&pageId=usflex&ignoreAuthState=1&openid.return_to=https%3A%2F%2Fwww.amazon.com%2F%3F_encoding%3DUTF8%26ref_%3Dnav_ya_signin&prevRID=4CN21QYBVVZRQBNGEQZ7&openid.assoc_handle=usflex&openid.mode=checkid_setup&openid.ns.pape=http%3A%2F%2Fspecs.openid.net%2Fextensions%2Fpape%2F1.0&prepopulatedLoginId=&failedSignInCount=0&openid.claimed_id=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0%2Fidentifier_select&openid.ns=http%3A%2F%2Fspecs.openid.net%2Fauth%2F2.0) and create a new amazon.com account (if you'd like to use an existing one, skip this step).

  * The **Email** (user id) can be something like `team777@jupiter1.io`, it does not have to exist

* Go to https://developer.amazon.com and login with the account just created (or use an existing one). 

  * Fill the information of the registration wizard.

* Create an Alexa Skill
  * Go to the Alexa Console https://developer.amazon.com/alexa/console/ask 
  * Click on the **Create Skill** button
  * Type **First Skill** as skill name and click **Next**
  * Select **Custom** and click the **Create skill** button
  * Click **JSON Editor** on the left bar
  * Paste the contents of [facts-skill-interaction-model.json](https://raw.githubusercontent.com/jose-troche/alexa/master/facts-skill-interaction-model.json) in the editor
  * Click the **Build Model** button (it will take a few minutes to build the model)
  * Go back to the Alexa Console https://developer.amazon.com/alexa/console/ask
  * Click on the **View Skill ID** link
  * Copy the **Skill ID** (e.g. `amzn1.ask.skill.5a1e8977-e4f4-4a74-ba4c-5badaf4ac849`) from the popup. 
  
* Create a Lambda Function
  * Open a new browser tab
  * Go to https://jupiter1.signin.aws.amazon.com/console
  * Sign in with your **user name** (e.g. `team777`) and password
  * Make sure that the upper right menu dropdown for region has **US East (N. Virginia)** selected
  * Type **Lambda** in the **AWS Services** box
  * Select the **Lambda** service
  * Click the **Create a function** button
  * Select **Blueprints**
  * Type the keyword **alexa** in the blueprints filter box
  * Select the **alexa-skill-kit-sdk-factskill** blueprint
  * Type a unique **Name** like `alexaSkillTeam777`
  * For the **Role** dropdown, select the **Choose and existing role** option
  * For the **Existing Role** dropdown, select the **firstAlexaSkillRole** role option
  * Scroll down and click the **Create function** button
  * On the left, under **Add triggers** select the **Alexa Skills Kit** trigger
  * Scroll down and paste the **Skill ID** copied in previous section (e.g. `amzn1.ask.skill.5a1e8977-e4f4-4a74-ba4c-5badaf4ac849`)
  * Click the **Add** button
  * Scroll up and click the orange **Save** button
  * Copy the **ARN** on top of the orange **Save** button (e.g. `arn:aws:lambda:us-east-1:735534501522:function:alexaSkillTeam777`)
  

* Update the Endpoint of the Alexa Skill
  * Go back to the Alexa Console tab (or create a new one and go to https://developer.amazon.com/alexa/console/ask)
  * Click the **Edit** button
  * Select **Endpoint** on the left bar
  * Select the **AWS Lambda ARN** radio button
  * Paste the copied Lambda **ARN** (e.g. `arn:aws:lambda:us-east-1:735534501522:function:alexaSkillTeam777`) in the **Default Region** box
  * Click the **Save Endpoints** button
  * Click the **Test** link on the top menu bar
  * Enable testing by turning on the switch
  * Type **space facts** in the **Alexa Simulator** text box and press the [ENTER] key
  * You should hear Alexa reading an space fact that comes from the Lambda function
  
*Congratulations!!!* You just created your first Alexa skill

# Further Steps
* Testing the Lambda function
  * Copy the json content of the **JSON Input** panel in the Alexa Console
  * Go back the Lambda function tab
  * Select the **Configure test events** option from the dropdown to the left of the **Test** button (upper right section)
  * Paste the json content into the editor
  * Type a **Name** and then click the **Save** button
  * Click the **Test** button (upper right section)
  * Review the **Details** of the Execution results
  
* Examine the Lambda function code. Modify the code of the Lambda function by adding a new space fact. **Save** and **Test**
* Go back to the Alexa Console and try to add a new Intent in the skill model (hint: you have to rebuilt the model and also create a corresponding intent in the Lambda function)
* [Set Up Your Echo Dot]()
