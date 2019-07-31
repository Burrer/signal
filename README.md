# Signal-2019

This repo contains templates HTML/CSS, JSON personalization examples, as well as v3 Email API cURL examples for the "Twilio SendGrid's Email API: Features, Tricks, and Tips" workshop.

If wanting to use SendGrid's official API libraries please visit use the following URL: (https://sendgrid.com/docs/for-developers/sending-email/libraries/)

Important to note: SendGrid dog foods our APIs to power the UI, so all of these steps can be done via the API as well as the UI.  For interested attendees feel free to use our [Postman integration](https://sendgrid.com/blog/sendgrid-v3-api-postman-2/) for easy access to API endpoints and documentation.

# Goal:
To deliver a handlebar based transactional template to yourself or a friend, using your own SendGrid account using your own authenticated domain, and tracking the emails activity using the webhook or email activity feed within your account (last step optional).

# Requirements:
  - SendGrid Account API Key - get trial acct [here](https://sendgrid.com/free/)
  - Domain and access to hosting (optional - but needed for DNS creation)
  - Email Template (samples provided)
  - Terminal/Command/API Client (Postman)

# Steps
- Create an API key with at least mail permissions (give full permissions if following through steps with API)
UI: Settings -> API Keys -> Create Key
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/78ffe380-37ef-4c35-887b-25cfe0f6c20e/00000004.png)
  
- Authenticate Your Domain:  If you do not have a domain skip ahead to the next steps (you will still be able to send mail, you will just a see a 'via sendgrid.net' statement in the FROM address).  Go to ['Sender Authentication'](https://app.sendgrid.com/settings/sender_auth) and click on 'Authenticate Your Domain".  Make sure to select 'Yes' for link branding (#2) if planning on using SendGrid for click tracking.  If you have a dedicated IP (pro100k plans and higher) you should also have a section to authenticate your IP(s) rDNS via A records.
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/5dab8e97-f289-4e2f-8426-ce45b50518d9/00000006.png)

- Take the DNS records and input them in your domain's host.

- After implementing the new DNS records in your domain host go back to [Sender Authentication](https://app.sendgrid.com/settings/sender_auth) and 'verify' your new domain and link authentication.  Please note: propagation time varies by host and can take up to 24 hours for some hosts.  You can check on your DNS propagation by running [dig](https://www.tecmint.com/10-linux-dig-domain-information-groper-commands-to-query-dns/) commands in terminal/command (example: 'dig [host record] cname') to see if your DNS records are publicly queriable.

- Build Template or Copy/Paste Template HTML/CSS into Transactional Templates editor - make sure to set subject line ("Welcome to Signal, {{firstname}}!") when building your transactional template.
If wanting to build your own handlebar based templates look to this documentation [here](https://sendgrid.com/docs/for-developers/sending-email/using-handlebars/)
Feel free to add subsitution values to your template - but make sure to log those same substitutitons under 'dynamic template data' in your API request.
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/6e309f0b-e7bf-4196-a952-e97b556cf9cb/00000003.png)
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/c9a8ad74-2733-4bd1-a435-527cbfd1441a/00000008.png)

- (*Optional*) Setup your event notification app with an endpoint URL.  Feel free to use a service like [Requestbin](http://requestbin.net/)
Or use own webhook endpoint - webhook code samples [here](https://sendgrid.com/docs/for-developers/tracking-events/).  Make sure to setup your webhook URL in the [Event Notifcation App](https://app.sendgrid.com/settings/mail_settings).
There will be a Workshop on "Consuming Twilio SendGrid Webhooks" at 8/6 (same day as this workshop) from 4:15pm to 5:25pm.

- Use cURL examples, Twilio [SendGrid API Library](https://sendgrid.com/docs/for-developers/sending-email/libraries/) or [Postman](https://www.getpostman.com/downloads/) to send an email using a transactional template
Make sure to substitute all different parameters of the request in text editor with your own data - search for "REPLACE" in requests and subsitute your own info.
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/fed05cc9-6190-4dbb-ae45-c4b29bcb04d9/00000010.png)

- Use webhook and/or the [Email Activity Feed](https://app.sendgrid.com/email_activity) to track you email activity and history
![N|Solid](https://content.screencast.com/users/ryantsg/folders/Jing/media/8947def8-fd85-4296-832d-337f18ecc070/00000009.png)
