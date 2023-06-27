
# A decentralized, curated, and interactive web feed
Author: Michael Netter, Version: 0.1

The web was initially conceived as a decentralized system powered by open protocols. On the application level however, a few centralized platforms emerged, and today they control how content is distributed and consumed. People flock to social networks to consume their daily, curated feed of information. Creators cross-post their content on social media to get the attention of their audience as posts on individual websites usually have a much smaller reach. 

While being convenient, this concentrated power poses several risks, such as creators being deplatformed and a loss of privacy for consumers.

In this article I try articulate my thoughts on a new, decentralized web feed on a programmable blockchain that solves the aforementioned issues. Serving as a decentralized computer, with blockchains it is now possible to build new systems that are decentralized not only on the protocol level but are also **decentralized on the application level**. 

Such a decentralized web feed revives the idea of the web as a decentralized system and allows users to post and find relevant content without compromising their privacy.

## RSS and why Social Media is so attractive
Web feeds, such as RSS and Atom, became a popular way in the early 200s to get updates from websites. These open standards have no power structure that tries to get content in front of your face. RSS often turns into a firehose, for example when users subscribed to high-volume content creators.

Besides, RSS does not have a feedback channel (who consumes the content and how often?) and contains no signal (what content is relevant to you as consumers? For creators, which content resonates with their audience?). It also lacks any type of baked-in identity and ways to interact with the content and the creator. Besides, since RSS readers are client applications and there is no centralized database of the connection between consumers and creators, it's difficult to build a recommendation system to discover new content creators.

From a consumer standpoint, centralized social media platforms overcome the aforementioned issues of web feeds and make these platforms so attractive. First is the convenience of a personalized, curated news feed (promoting more relevant items and hiding less relevant ones). Second, these platforms make it easy to discover new (and relevant) content creators. Third, they allow consumers to interact with the content (such as through replies and likes).

For content creators, they offer a convenient way to communicate with the audience and also provide a feedback loop and analytics that help them to sharpen their content.

## Privacy and deplatforming as major threats of centralized platforms
Despite aforementioned advantages for content creation and consumption, centralized social media platforms threaten the privacy of their users. They control how content is distributed. 

They also have access to a treasure trove of personal information (such as demographics) they can share with third-parties for monetization. 

Besides, content creators face the risk of being deplatformed (identities and connections are owned by the platform) and lose the connection to their audience (this is why many social media content creators start email newsletters where they own the connection with their consumers).

## A decentralized, curated, and interactive web feed

The following is a rough sketch of a decentralized web feed. The goal is to outline the general idea without having worked out all details. The goal is 

To be viable, it should at least have the following properties:
- **Decentralized**: No centralized platform that owns content or connections
- **Curated**: Feed should contain relevant content
- **Interactability**: Ability for users to interact with content
- **Discoverability**: Ability for users to find new, relevant content
- Push()? might not be needed

### Entities
The following entities are defined:
- Publishers: A publisher is an entity that creates content.
- Channels: A channel is created and owned by a publisher. It is a medium through which publishers share their content.
- Users: A user is an entity that consumes content. Users subscribe to channels (which is similar to following people on social media).

### System overview
A programmable blockchain (such as Ethereum) forms the basis. A smart contract manages the entities described above. It provides some of the same functionality that social network platforms offer, such as registration, sharing content and interaction, but it does that in a decentralized way.

#### Registration
At first, a publisher must register with the contract. In this step, his blockchain account address is added to the list of publishers. Then the publisher uses the contract to create a new channel. The channel is added to the list of channels and the publisher is registered as the owner of the channel. Users can also register with the contract and are then added to the list of users. This completes the registration.

#### Publishing
Today, a publisher creates new content on his blog or website. But instead of cross-posting it to centralized social media platforms, he creates a new message in his channel. The message should be in a structured format and contain only a link to the original content. This is because storage on the blockchain is typically expensive. RSS could be leveraged for this.

#### Subscribing
Users may browse the list of existing channels to find publishers they are interested in. They may also directly subscribe on the publisher's website. Subscription means that they call a function of the contract to add their account address to a specific channel.

#### Interaction
Since the contract is public, any type of client can be created (mobile, web-based, desktop) to render the subscribed content. Think of these clients as similar to RSS readers but with a major difference: the user may interact with the content. Interactions such as likes are stored in the contract. Additionally, the contract may store analytics such as number of views.

#### Curation
Up to here, the user would get an uncurated list of all content items published by all the channels they subscribed to only sorted by published date.

Content curation could be implemented in the client or using an intermediary. One could image a curation service as such an intermediary. The user registers with a curation service of his choice. Then the service fetches all content items and — based on previous views and interactions — creates a compelling list of new content. 





- privacy: hide user accounts

From EPNS: However, the user experience in web3 is still mediocre and lacks the characteristics of seamless interactions and communication as found in the current web model.

preserve privacy (hide subscribers)
Getting adoption (cold start problem)


### Why RSS did not succeed

newsletter not as convenient


## Solution

## tl;dr
This article captures my thoughts on
My thoughts on why people flock to social networks to consume their daily feed of information, why creators cross-post their website content on social media to get the attention of their audience, why RSS/Atom failed and how this could be solved in a privacy-friendly and decentralized way.

Posting content on social media is probably the most way frequently used way for creators today to get the attention of their audience. While convenient, it creates a number of problems for both creators and consumers.


creators / consumers
## Intro:

In this article I try to articulate my thoughts on the problems that need to be solved and the properties of such a system.

websites/blogs get few visits, content is crossposted on social media, giving them power over distribution and commercial expoitation

### Problems to solve
Users
- Curation / algorithm
- Discovery
- Privacy-friendly

Content creators
- Interact
- Analytics / feedback loop

UX and convenience make

users want personalization and priorization not a chronological stream
stream that shows them the most important content first,
creators don't want to be deplatformed (hence many create email newsletters, which is decentralized)


decentralized at application level
privacy friendly, allow to follow websites




Problem
- concentration at few large centralized providers
- content is there
- users are there
- algorithms to create feed
- interact with content
- share content on social media because no one visits individual websites



RSS
it is decentralized, with no power structure trying to stuff other content in front of your face. but lacks features
contains no signal what is important and what is not. one reason is that there is no feedback channel, it is completely decentralized.

We don’t want to give you a firehose
- discovery: no curation, how to find good rss feeds, readers must help users to find good rss feeds
- no reply
- no identity backed in
- no interactivity backed in, one way communication (even email newsletter you can reach out to subscribers and they can mail you)
- no feedback loops to see what content resonates with your audience

- publisher: no analytics, strip away brand and feed raw content

wordpress plugin