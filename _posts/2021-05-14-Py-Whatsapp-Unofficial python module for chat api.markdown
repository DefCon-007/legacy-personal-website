---
title: "Py-WhatsApp: Unofficial python module for chat api"
layout: post
date: 2021-05-14
tag: 
- Python
- Module
- WhatsApp
image: /assets/images/Projects/pywhatsapp-banner.png
headerImage: true
projects: true
hidden: true # don't count this post in blog pagination
description: "An unofficial python module for chat-api.com to communicate with WhatsApp without official business API and programmatically send messages."
category: project
author: defcon
externalLink: false
---

Py-WhatsApp is the un-official python module for [chat-api.com](https://chat-api.com) and provides a pure pythonic way to communicate with WhatsApp programmatically without the official business API. 

Github - <https://github.com/DefCon-007/py-whatsapp>

PyPi - <https://pypi.org/project/whatsapp-api/>

## What is chat-api.com

It is a multifunctional rest api for WhatsApp accounts working on top of WhatsApp web. They offer a 3-day free trial to allow you to use the service before buying and this python package allows you to interface with most of its services directly.

## Pitfalls of official WhatsApp API 

1. You first need to get approved from WhatsApp to start using the business API. 
2. You are tied in with a third party provider to avail the services and has to pay their set prices which are generally low but depends on per incoming/outgoing message.
3. When someone contacts your number, you have to reply with in 24 hours. Post that, you can only send a template message to the contact. 
4. You cannot send any message to a person who has not initiated a conversation with you, you can only send them a template message. 
\
    **What is template message?**
    This is a message which has to be first approved by WhatsApp and then you can use it to contact potential customers or reply to conversations which are older than 24 hours. 

For more information head over to <https://www.whatsapp.com/business/api/>. 


## How to use

1. Go to [chat-api.com](https://chat-api.com) and create a new account. 
2. After successful account creation you will have a single instance active, copy the `instanceId` and `token` and keep them safe.
3. Install the module using `pip install whatsapp-api`.
4. Now use the following code snippet to send the message. [Click here](https://github.com/DefCon-007/py-whatsapp) to read more in-depth details on using the library.

    ```python
    from whatsapp import WhatsApp

    token = "xxxxxxx"
    instance_id = "instancexxx"

    object = WhatsApp(token, instance_id)

    phone_number = "911234512345"
    message = "This is a sample text message. *This will be bold*"
    response = object.send_message(phone_number, message)
    ```

    Keep in mind the phone number has to be in the international format, here the sample number is from India(country code +91).

## Disclaimer

I am in no way associated to WhatsApp to Chat-API. This post and the corresponding module is only for educational purpose.

---
