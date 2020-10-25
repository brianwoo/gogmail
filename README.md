# gogmail
Wrapper Library to send email messages with Gmail with OAuth2

# How to Install
go get -u github.com/brianwoo/gogmail

# How to Setup the Gmail API and OAuth2
In order to send email using Gmail + OAuth2, you will need to create a project in the [Google Developer Console](https://console.cloud.google.com). (Thanks to Binod Kafle for the instructions)

![Select a project](/images/select_a_project.png)

![New project](/images/new_project.png)

Give your project a name:
![Name your project](/images/new_your_project.png)

You will then be brought back to the Google Cloud Platform home page.
Select APIs & Services --> Dashboard
![Enable APIs](/images/enable_apis.png)

Search for gmail in the search field and select Gmail API
![Search for gmail](/images/search_for_gmail.png)

Click "Enable" to enable the Gmail API and select your project in the pop-up.
![Enable Gmail API](/images/enable_gmail.png)

Your Gmail API will take a few seconds to create.

In the Gmail API side panel, select Credentials --> Configure Consent Screen
![Gmail Credentials](/images/gmail_api_credentials_consent.png)

Select your User Type (Internal may not be available)
![User Type](/images/api_user_type.png)

Give your application a name. This is the name of the app asking for consent
![oauth consent screen](/images/oauth_consent_screen.png)

Go to the bottom and click Save

Next, click Credentials from the side panel and  click Create Credentials
--> Select OAuth client ID
![oauth credentials](/images/oauth_credentials.png)

On the Create OAuth client ID screen, select "Web application" and https://developers.google.com/oauthplayground for the Authorized redirect URIs
![create oauth client ID](/images/create_oauth_client_id.png)

Make sure you save your Client ID and Client Secret somewhere for later
![oauth_client_created](/images/oauth_client_created.png)

Go to https://developers.google.com/oauthplayground


