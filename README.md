# Roadmap
Roadmap for planned features / APIs I want to implement in NEKOS.

## Alpha Release - Basic Java/Kotlin API
Once these features, runners and Java APIs are stable I will release an alpha release of the NEKOS API, NEKOS runner and services.
- [ ] A core Java/Kotlin API coded in Kotlin
    - This is what NEKOS will use internally for all requests. 
    - Services must be implemented in Java or Kotlin and distributed as a JAR file. The NEKOS runner will load this JAR and load services
    - Services get abstracted to as generic as possible while keeping as much functionality as possible. This allows any plugin to interact with any service without being coded specifically for any single service
    - Plugins can be used to give NEKOS functionality from within the server itself. Plugins can be coded in Java and Kotlin and can subscribe to various events that services can trigger.
    - This will form the core of the entire project

- [ ] Services when they have the following features:
    - Ability to reply to a message if this chat service is capable of sending messages
    - Format messages with whatever formatting the chat service supports 
    - File attachments in messages if supported in the chat service
    - The following events **when applicable**:
        - Message received
        - Message deleted
        - User joined
        - User left
    - The following objects from events must have the following functionality **when applicable**
        - Message
            - Content
            - User
            - Timestamp
            - Channel
            - *Replying to this message*
        - User
            - Name
            - Nickname / Friendly name
            - Hash of this services personally identifiable data (for example a static User ID)
            - *Discipline this user (kick/ban/etc)*
        - Channel
            - Name
            - Method to get list of users
            - Guild this belongs to
            - *Rename this channel*
        - Guild
            - Name
            - Method to get list of channels
            - *Rename this guild*

- [ ] The following official services:
    - [ ] Discord
    - [ ] Matrix
    - [ ] Telegram
    - [ ] Email
    - [ ] IRC
    - [ ] RSS (Read-only)

With these features, this should be enough to build chat bots in NEKOS that are service agnostic. Media bots, game bots and other novelty bots already in coded should be possible to port to NEKOS and by extension run on other platforms. This will be the first initial release of NEKOS. It isn't feature complete and is still alpha software.

## Alpha 2 - As close to feature completeness as possible for text services
In this release text services should have features as close as possible to their native APIs, while being generic and not interfering with the nature of NEKOS being service agnostic.
This will be mostly implemented on the side of the service, however this will likely require a lot additions in the API to accomodate these.

Some features the API will likely need to implement for some features in services are:
 - [ ] User groups 
 - [ ] NEKOS service agnostic formatting (Bold, italics, other markdown, headings, embeds automatically applied to a service)
 - [ ] Dynamic (Slash) commands 
 

The following service specific features can be abstracted and implemented. If a plugin tries to use a feature not available on a service NEKOS should leave it out causing as little quirks as possible. If the feature is critical, the plugin can list this.
Some examples include:  
 - [ ] Discord roles (Abstracted to user groups)
 - [ ] Matrix permission levels (Abstracted to user groups)
 - [ ] Embeds in Discord (Behind formatting)
 - [ ] Email HTML formatting
 - [ ] Discord & Telegram slash commands