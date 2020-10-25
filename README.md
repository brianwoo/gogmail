# gogmail
Wrapper Library to send email messages with Gmail with OAuth2

# How to Install
go get -u github.com/brianwoo/gogmail

# How to Setup the Gmail API and OAuth2
In order to send email using Gmail + OAuth2, you will need to create a project in the [Google Developer Console](https://console.cloud.google.com). (Thanks to Binod Kafle for the instructions)

## Step 1:
![Select a project](/images/select_a_project.png)

## Step 2:
![New project](/images/new_project.png)

## Step 3:
Give your project a name:
![Name your project](/images/name_your_project.png)

## Step 4:
You will then be brought back to the Google Cloud Platform home page.
Select APIs & Services --> Dashboard
![Enable APIs](/images/enable_apis.png)

## Step 5:
Search for gmail in the search field and select Gmail API
![Search for gmail](/images/search_for_gmail.png)

## Step 6:
Click "Enable" to enable the Gmail API and select your project in the pop-up.
![Enable Gmail API](/images/enable_gmail.png)

## Step 7:
Your Gmail API will take a few seconds to create.

In the Gmail API side panel, select Credentials --> Configure Consent Screen
![Gmail Credentials](/images/gmail_api_credentials_consent.png)

## Step 8:
Select your User Type (Internal may not be available)
![User Type](/images/api_user_type.png)

## Step 9:
Give your application a name. This is the name of the app asking for consent
![oauth consent screen](/images/oauth_consent_screen.png)

Go to the bottom and click Save

## Step 10:
Next, click Credentials from the side panel and  click Create Credentials
--> Select OAuth client ID
![oauth credentials](/images/oauth_credentials.png)

## Step 11:
On the Create OAuth client ID screen, select "Web application" and https://developers.google.com/oauthplayground for the Authorized redirect URIs
![create oauth client ID](/images/create_oauth_client_id.png)

## Step 12:
Make sure you save your Client ID and Client Secret somewhere for later
![oauth_client_created](/images/oauth_client_created.png)

## Step 13:
Go to https://developers.google.com/oauthplayground

Click the settings button in the upper right corner. Click the checkbox "Use your own OAuth credentials". Copy and paste the OAuth Client ID and Client secret from earlier.

Next, enter http://mail.google.com in the input box (next to the Authorize APIs)

Click Authorize APIs button.
![oauth 2.0 configuration](/images/oauth_playground.png)

## Step 14:
You will then see a Sign in screen.  Select your account to sign in.

![sign in screen](/images/choose_an_account.png)

## Step 15:
You will see a screen such as the following. Click Advanced and Click the Go to Project link

![app not verified](/images/app_not_verified.png)

## Step 16:
Grant your project permission to access Gmail

![grant project permission](/images/grant_project_permission.png)

## Step 17:
You will be brought back to Step 2. Click "Exchange authorization code for tokens".

Copy the Refresh token and Access token for later use.

![refresh access tokens](/images/refresh_access_token.png)

That's it for API setup!




