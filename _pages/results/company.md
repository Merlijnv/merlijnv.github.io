# Company Pentest

Together with a classmate of mine, we thought it would be really interesting to do a pentest for a company.
We got in contact with the company and had a conversation on what we could pentest. At the end of the meeting we had 2 things in our scope:

- A phishing test
- A external application test

## Test plan

We have set up a test plan got some feedback from the client and after that finalized it.

## Phisingtest

We got the objective to do a phishing test on the company. At first, the scope for this test was the full organization but because of the difficult times because of corona, we have decided to do 50% of the organization.
The phishing test has as the idea a password reset where they get send to their "own portal" where they have to log in to reset their password.

### GoPhish

As Phsing framework, we have chosen for GoPhish.
On this framework, we can create a campaign with an email template and a landing page.
These we can make ourselves or import from an existing site.
The campaigns can be planned and you get a clear overview of all the results.
![Go Phish](/images/gophish.png)

### Mail

The mail was set up to be noticeable but also believable.

![mailgun](/images/companymail.png)

### Landing Page

For the landing page we looked for a portal or something of the company quickly we found an employee portal which is perfect for our purpose.
We just imported the portal using the url and when we use it in our campaign you don't see anything.
But notice the {domain}.ml at the top which could be seen by the victim.
We also added a free generated ssl certificate which is making the portal more trustworthy.
When people fill in their info and click log in they will be redirected to the real login page.
And we will get that info without a password in our campaign.
![Landing page fake](/images/landingpage.png)

### SMTP Server

As an smtp server, we first tried to use postfix this worked but some of the emails went into spam. This was mostly on office 365 outlook which the company is also using.
To fix this we tried to get a real smtp server. We have used mailgun for a project we did last semester and know this could be a great solution.
We added the needed dns records and configured the smtp.
This way as far as we know for now all the emails ended up in the inbox instead of spam.
We can send 20K emails which is more then enough.
![mailgun](/images/mailgun.png)

### Findings

We had a great start on the first day after a couple hours we already have multiple people opening the mail and also pressing the link and submitting data.
![first findings](/images/firstfindings.png)

The second day we had some reports of phishing mail to the security officer these users will be flagged as reported so we can have a better view.
Even after the phishing being noticed and discussed between colleagues still we went from 30 -> 61 this day.
![second day](/images/secondday.png)

### End results

At the end we had some very interesting findings we had a lot of clicks and submitted data  even after the intranet message send out
The email opened is not correct because some people opened the mail without downloading the tracking image this could be a lot more than shown.

![end result](/images/phishingendresults.png)

We have had multiple users submitting data even multiple times.
Also we had an employee warning other coworkers by sending the mail with a clear warning but those coworkers tried to login using the url in this mail.