# Signal-2019

This repo contains templates HTML/CSS, JSON personalization examples, as well as v3 Email API cURL examples for the "Twilio SendGrid's Email API: Features, Tricks, and Tips" workshop.

If wanting to use SendGrid's official API libraries please visit use the following URL: (https://sendgrid.com/docs/for-developers/sending-email/libraries/)

Important to note: SendGrid dog foods our APIs to power the UI, so all of these steps can be done via the API as well as the UI.  For interested attendees feel free to use our [Postman integration](https://sendgrid.com/blog/sendgrid-v3-api-postman-2/) for easy access to API endpoints and documentation.

# Goal:
To deliver a handlebar based transactional template to yourself or a friend, using your own SendGrid account using your own authenticated domain, and tracking the emails activity using the webhook or email activity feed within your account (last step optional).

# Requirements:
  - SendGrid Account API Key - get trial acct [here](https://sendgrid.com/free/)
  - Domain and access to hosting (for DNS creation)
  - Email Template (samples provided)
  - Terminal/Command/API Client (Postman)

# Steps
- Create an API key with at least mail permissions
UI: Settings -> API Keys -> Create Key
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/78ffe380-37ef-4c35-887b-25cfe0f6c20e/00000004.png)
  
- Authenticate Your Domain (requires domain ownership and access to host for DNS creation).  If you do not have a domain skip ahead to the next steps (you will still be able to send mail, you will just a see a 'via sendgrid.net' statement in the FROM address).
Sendgrid Documentation
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/5dab8e97-f289-4e2f-8426-ce45b50518d9/00000006.png)

- Build Template or Copy/Paste Template HTML/CSS into Transactional Templates editor - make sure to set subject line ("Welcome to Signal, {{firstname}}!") when building your transactional template.
If wanting to build your own handlebar based templates look to this documentation [here](https://sendgrid.com/docs/for-developers/sending-email/using-handlebars/)
Feel free to add subsitution values to your template - but make sure to log those same substitutitons under 'dynamic template data' in your API request.
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/6e309f0b-e7bf-4196-a952-e97b556cf9cb/00000003.png)
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/c9a8ad74-2733-4bd1-a435-527cbfd1441a/00000008.png)

- (*Optional*) Setup your event notification app with event webhook endpoint URL
[SendGrid Event Kit](https://sendgrid.com/docs/for-developers/tracking-events/event-kit/)(easiest method)
Or use own webhook endpoint - webhook code samples [here](https://sendgrid.com/docs/for-developers/tracking-events/)

- Use Twilio [SendGrid API Library](https://sendgrid.com/docs/for-developers/sending-email/libraries/) or cURL examples in repo to send emails to yourself using a transactional template
Make sure to substitute all different parameters of the request with your ownn data: API KEY, FROM ADDRESS, TO ADDRESS, etc.
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/416feee0-ef1f-4a41-b73a-fb12aef32e1b/00000007.png)
Copy/Paste in terminal to send email


- (Optional) Use webhook or the [Email Activity Feed](https://app.sendgrid.com/email_activity) to track you email activity and history
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/5b1db284-85db-4863-9929-e79dfe9e0b44/00000005.png)
