# gogmail
A Library to send email messages with Gmail with OAuth2

# How to Install
go get -u github.com/brianwoo/gogmail

# How to Setup the Gmail API and OAuth2
To send email messages using Gmail with OAuth2, you will need to following the steps below to get four pieces of credential information:

1. OAuth Client ID
1. OAuth Client Secret
1. OAuth Refresh Token
1. OAuth Access Token

Credits: Thanks to Binod Kafle for the helpful instructions

## Step 1:
Create an API project in the [Google Developer Console](https://console.cloud.google.com).  Click the **Select a project**

![Select a project](/images/select_a_project.png)

## Step 2:
Create a **New Project** or use an existing project.

![New project](/images/new_project.png)

## Step 3:
If you are creating a new project, you will need to give your project a name:

![Name your project](/images/name_your_project.png)

## Step 4:
You will then be brought back to the Google Cloud Platform home page.
Select **APIs & Services** --> **Dashboard**

![Enable APIs](/images/enable_apis.png)

## Step 5:
Search for **gmail** in the search field and select **Gmail API**

![Search for gmail](/images/search_for_gmail.png)

## Step 6:
Click **Enable** to enable the Gmail API and select your project in the pop-up.

![Enable Gmail API](/images/enable_gmail.png)

## Step 7:
Your Gmail API may take a few seconds to create.

In the Gmail API side panel, select **Credentials** --> **Configure Consent Screen**

![Gmail Credentials](/images/gmail_api_credentials_consent.png)

## Step 8:
Select your **User Type** (Internal may not be available)

![User Type](/images/api_user_type.png)

## Step 9:
Give your application a name. This is the name of the app that will be asking for consent in the later step. When the name is entered, go the bottom of the screen and click **Save**

![oauth consent screen](/images/oauth_consent_screen.png)

## Step 10:
Next, click **Credentials** from the side panel and click **Create Credentials**
--> select **OAuth client ID**

![oauth credentials](/images/oauth_credentials.png)

## Step 11:
On the Create OAuth client ID screen, select **Web application** and enter https://developers.google.com/oauthplayground for the Authorized redirect URIs as shown:

![create oauth client ID](/images/create_oauth_client_id.png)

## Step 12:
The OAuth client is now created. Make sure you save your OAuth **Client ID** and **Client Secret** somewhere for later use.

![oauth_client_created](/images/oauth_client_created.png)

## Step 13:
Go to [OAuth Playground](https://developers.google.com/oauthplayground)

Click the settings button in the upper right corner. Click the checkbox **Use your own OAuth credentials**. Copy and paste the **OAuth Client ID** and **Client Secret** from earlier.

Next, enter http://mail.google.com in the input box (next to the **Authorize APIs** button in the lower left).  Click **Authorize APIs button** to proceed.

![oauth 2.0 configuration](/images/oauth_playground.png)

## Step 14:
A Sign in screen will then appear on the screen.  Select your account to sign in.

![sign in screen](/images/choose_an_account.png)

## Step 15:
As soon as you have logged in, you will see a screen as following. Click **Advanced** and Click the **Go to Project** link

![app not verified](/images/app_not_verified.png)

## Step 16:
Grant your project permission to access Gmail

![grant project permission](/images/grant_project_permission.png)

## Step 17:
Next, you will be brought back to Step 2 in the OAuth 2.0 Playground. Click **Exchange authorization code for tokens**.

Copy the **Refresh token** and **Access token** for later use.

![refresh access tokens](/images/refresh_access_token.png)

That's it for API setup!


# How to Use this Library
```golang
import (
	"log"

	"github.com/brianwoo/gogmail"
)

func main() {

	sendMail := gogmail.NewSendMail(
		"--- Enter OAuth Client ID here ---",
		"--- Enter OAuth Client Secret here ---",
		"--- Enter OAuth Access Token here ---",
		"--- Enter OAuth Refresh Token here ---")

	err := sendMail.Send("recipient@gmail.com", "this is my subject", "this is my email body")
	if err != nil {
		log.Fatal(err)
	} else {
		log.Println("Email sent successfully!")
	}

}
```

