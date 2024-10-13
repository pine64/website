---
title: "Best practices for navigating the bridged community chat"
draft: false
---

The PINE64 community chat is connected across multiple platforms: **IRC**, **Telegram**, **Discord**, and **Matrix**. Each platform has its own unique user base and interface, however they interact with each other through the bot account bridging all platforms.

The software to bring all platforms together is called [**Matterbridge**](https://github.com/42wim/matterbridge). It acts as the bridge that connects these platforms. It facilitates seamless communication by relaying messages between them. When a user sends a message on any platform (such as IRC), the bot account picks it up. The bot then relays the message to all other connected platforms (such as Telegram, Discord, Matrix). This ensures that users on different platforms can communicate with each other. 

Users can choose their preferred platform while staying connected to the community.

## A short explanation on how to read the messages

The following example can be used to illustrate the use of the bridged community chat:

    [D] <Dave> Hey everyone! Just got my new PinePhone. Loving it so far! 📱
    [T] <Eve> Welcome, Dave! We’re discussing the upcoming application updates.
    [M] <Frank> Hey folks! I’m here from Matrix. Any tips on optimizing battery life?
    [I] <Ingrid> Greetings! 🌲 I wonder about the same, Frank.
    [I] <Ingrid> Also, kudos to the PINE64 community for the software progress so far!

In this example, the part in the square brackets at the beginning shows the platform, from which each user is writing, [**D**]iscord, [**I**]RC, [**M**]atrix and [**T**]elegram. The part in the angle brackets contains the name of each user: in this example, Dave, Eve, Frank and Ingrid are chatting with each other.

The bot account relaying the message can have a name such as _Pine64 Protocol Droid_. Mind that this is not the name of the user, who wrote the message.

## Things to consider when using the bridged community chat

In the bridged community chat that spans across Discord, Matrix, Element, and IRC, there are several important considerations to keep in mind. These guidelines help ensure smooth communication and prevent unintended issues. Let’s explore each of these aspects:

### Avoid editing messages

Editing messages may lead to repeated broadcasts across platforms. To maintain clarity and prevent confusion, refrain from editing your messages after they have been sent.

### Be cautious with the Discord and Matrix reply function

While Discord and Matrix allows users to reply directly to specific messages, this feature does not translate to other platforms. When responding to messages, avoid using Discord and Matrix reply function, as it does not display properly on the other platforms.

Instead mention the name of the user you are replying to in your message.

### Use paste services for code and log data

Code snippets and log data may not display correctly due to formatting limitations on the bridged community platforms. To share code or logs effectively, consider using paste services (such as Pastebin or GitHub Gists) and provide a link to the content.

By adhering to these best practices, you can contribute to a seamless and harmonious experience within the bridged community chat. Happy chatting!

### Telegram images do not appear in IRC

When sending images via Telegram, be aware that they do not appear in the IRC channel. If visual content is crucial, consider alternative methods of sharing, such as providing a link to an image hosting service.

### Mind file size limits for uploaded files

Keep in mind that uploaded files, especially videos, have maximum size limits. If sharing files, verify that they fall within the acceptable size range to ensure successful transmission across all platforms.

### Avoid manual line breaks and long messages

Messages with manual line breaks (hard returns) are interpreted as separate messages. To prevent fragmentation, avoid lengthy messages with excessive line breaks.

Long messages get cut off. To ensure complete communication, keep your messages concise and within reasonable length.

### Underscores can cause formatting issues

Underscores (_) in texts (for example as part of web links) can cause formatting issues due to being interpreted as command to write a text in italic. This sometimes causes links to not properly display and work across the bridge.
