```ngMeta
name: project:-“just-text-me”-module
completionMethod: manual
```
# Project: “Just Text Me” Module
The person you’ll most often text from your programs is probably you. Texting is a great way to send yourself notifications when you’re away from your computer. If you’ve automated a boring task with a program that takes a couple of hours to run, you could have it notify you with a text when it’s finished. Or you may have a regularly scheduled program running that sometimes needs to contact you, such as a weather-checking program that texts you a reminder to pack an umbrella.

As a simple example, here’s a small Python program with a textmyself() function that sends a message passed to it as a string argument. Open a new file editor window and enter the following code, replacing the account SID, auth token, and phone numbers with your own information. Save it as textMyself.py.


   #! python3
   # textMyself.py - Defines the textmyself() function that texts a message
   # passed to it as a string.

   # Preset values:
   accountSID = 'ACxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
   authToken = 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx'
   myNumber = '+15559998888'
   twilioNumber = '+15552225678'

   from twilio.rest import TwilioRestClient

❶ def textmyself(message):
❷     twilioCli = TwilioRestClient(accountSID, authToken)
❸     twilioCli.messages.create(body=message, from_=twilioNumber, to=myNumber)
This program stores an account SID, auth token, sending number, and receiving number. It then defined textmyself() to take on argument ❶, make a TwilioRestClient object ❷, and call create() with the message you passed ❸.

If you want to make the textmyself() function available to your other programs, simply place the textMyself.py file in the same folder as the Python executable (C:\Python34 on Windows, /usr/local/lib/python3.4 on OS X, and /usr/bin/python3 on Linux). Now you can use the function in your other programs. Whenever you want one of your programs to text you, just add the following:


import textmyself
textmyself.textmyself('The boring task is finished.')
You need to sign up for Twilio and write the texting code only once. After that, it’s just two lines of code to send a text from any of your other programs.

# Summary
We communicate with each other on the Internet and over cell phone networks in dozens of different ways, but email and texting predominate. Your programs can communicate through these channels, which gives them powerful new notification features. You can even write programs running on different computers that communicate with one another directly via email, with one program sending emails with SMTP and the other retrieving them with IMAP.

Python’s smtplib provides functions for using the SMTP to send emails through your email provider’s SMTP server. Likewise, the third-party imapclient and pyzmail modules let you access IMAP servers and retrieve emails sent to you. Although IMAP is a bit more involved than SMTP, it’s also quite powerful and allows you to search for particular emails, download them, and parse them to extract the subject and body as string values.

Texting is a bit different from email, since, unlike email, more than just an Internet connection is needed to send SMS texts. Fortunately, services such as Twilio provide modules to allow you to send text messages from your programs. Once you go through an initial setup process, you’ll be able to send texts with just a couple lines of code.

With these modules in your skill set, you’ll be able to program the specific conditions under which your programs should send notifications or reminders. Now your programs will have reach far beyond the computer they’re running on!

# Practice Questions

Q:

1. What is the protocol for sending email? For checking and receiving email?

Q:

2. What four smtplib functions/methods must you call to log in to an SMTP server?

Q:

3. What two imapclient functions/methods must you call to log in to an IMAP server?

Q:

4. What kind of argument do you pass to imapObj.search()?

Q:

5. What do you do if your code gets an error message that says got more than 10000 bytes?

Q:

6. The imapclient module handles connecting to an IMAP server and finding emails. What is one module that handles reading the emails that imapclient collects?

Q:

7. What three pieces of information do you need from Twilio before you can send text messages?
