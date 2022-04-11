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
