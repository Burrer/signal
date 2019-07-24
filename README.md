# Signal-2019

This repo contains templates HTML/CSS, JSON personalization examples, as well as v3 Email API cURL examples for the "Twilio SendGrid's Email API: Features, Tricks, and Tips" workshop.

If wanting to use SendGrid's official API libraries please visit use the following URL: (https://sendgrid.com/docs/for-developers/sending-email/libraries/)

# Goal:
To deliver a handlebar based transactional template to yourself or a friend, using your own SendGrid account using your own authenticated domain.

# Requirements:
  - SendGrid Account API Key (get trial [here](https://sendgrid.com/free/))
  - Terminal/Command/Postman
  - Domain and access to hosting
  - Email Template (samples provided)

# Steps
- Create an API key with at least mail permissions (cURL example provided)
UI: Settings -> API Keys -> Create Key
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/78ffe380-37ef-4c35-887b-25cfe0f6c20e/00000004.png)
  
- Authenticate Your Domain (requires domain ownership and access to host for DNS creation)
Sendgrid Documentation
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/5dab8e97-f289-4e2f-8426-ce45b50518d9/00000006.png)

- Build Template or Copy/Paste Template HTML/CSS into Transactional Templates editor
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/6e309f0b-e7bf-4196-a952-e97b556cf9cb/00000003.png)
If wanting to build your own handlebar based templates look to this documentation [here](https://sendgrid.com/docs/for-developers/sending-email/using-handlebars/)

- (*Optional*) Setup your event notification app with event webhook endpoint URL
[SendGrid Event Kit](https://sendgrid.com/docs/for-developers/tracking-events/event-kit/)(easiest method)
Or use own webhook endpoint - webhook code samples [here](https://sendgrid.com/docs/for-developers/tracking-events/)

- Use Twilio [SendGrid API Library](https://sendgrid.com/docs/for-developers/sending-email/libraries/) or cURL examples in repo to send emails to yourself using a transactional template
Make sure if using cURL request to substitute all areas in brackets: [API key], [FROM], [TO], etc.
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/416feee0-ef1f-4a41-b73a-fb12aef32e1b/00000007.png)
Copy/Paste in terminal to send email

- (Optional) Use webhook or the [Email Activity Feed](https://app.sendgrid.com/email_activity) to track you email activity and history
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/5b1db284-85db-4863-9929-e79dfe9e0b44/00000005.png)
