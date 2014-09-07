---
layout: post
title: Setup Postfix and Getmail
published: true
date: 2014-09-06 19:19:38 -0500
---

I decided I would use [nmh](https://savannah.nongnu.org/projects/nmh/). Now I need to get my mail to my computer.
I setup [getmail](https://www.linode.com/docs/email/clients/retrieving-email-using-getmail/)
and [postfix](http://souptonuts.sourceforge.net/postfix_tutorial.html).

I tried fetchmail to pull all my mail from gmail, but it sends to postfix and I ended up
with a "real" mailserver on my machine. That ended up with me sending lots of mailbox full
messages to lots of people.

getmailrc
~~~~~~
[retriever]
type = SimplePOP3SSLRetriever
server = pop.gmail.com
port = 995
username = USERNAME
password = PASSWORD

[destination]
type = Maildir
path = ~/.mail/

[options]
delete = true
message_log = ~/.getmail/log

~~~~~~

I run nmh inc command with the -file switch.
~~~~~~
inc -file /home/user/.mail
~~~~~~

postfix is setup according to the above tutorial with the addition of
~~~~~~
smtp_tls_CApath = /etc/ssl/certs
~~~~~~

I had to run c_rehash on that directory after trying to connect to gmail.

I am still figuring out how to use nmh, but I like the idea of that much control.
