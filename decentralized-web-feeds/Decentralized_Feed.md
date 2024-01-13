# A decentralized, curated, and interactive web feed

_Author: Michael Netter_

> _“The power of the web is not in centralization, it’s not in closed systems or anything like that.
> It’s in its open nature and that’s what allowed it to flourish for the first 10 or 15
> years.”_ - Matt Mullenweg

Let me start with the following thought experiment: How would the web look like if you could

- **follow websites** like you follow people on social media?
- get a feed that shows you the most relevant content from the websites you follow?
- interact with content (e.g. like) on websites like you interact with content on social
  media?
- discover new websites like you discover new people on social media?

All these features have been available on social media platforms for 15+ years and users have become
accustomed to having a personalized feed of content being pushed to them. Contrast this with the
web,
where content is mainly discovered through a search engine (often requiring SEO) or by cross-posting
it on social media.

There's so much valuable content created on the web every day. Why is it that I cannot follow a
website and get the most relevant content pushed into my feed?

In this article, I try to explore the building blocks required for a decentralized web feed that
would allow users to follow websites and get a curated feed of content.

## The evolution of the web

The web was initially conceived as a decentralized system powered by open standards and protocols (
e.g. HTTP and HTML). [Tim Berners-Lee described it](https://www.w3.org/History/1989/proposal.html)
as a network of information systems that are connected through hyperlinks, accessible to anyone, and
without any centralized control.

During the 1990s and early 2000s, the number of
websites [grew exponentially](https://www.internetlivestats.com/total-number-of-websites/). Web
feeds such as **RSS** emerged as one way to cope with the increasing number of websites. They allow
users to keep track of many websites without manually checking them for updates. However, RSS has
several drawbacks:

- It may become a firehose, especially when users subscribe to high-volume content creators (such
  as news sites).
- No feedback signal (what content is relevant to and which content resonates with
  consumers?)
- No baked-in identity and no way to interact with the content and the creator
- Since RSS readers are client applications, it's difficult to build a recommendation system to
  discover new content creators.

At the same time, the web became more interactive and usable, starting the era of **Web 2.0**. Blogs
and social media platforms such as Facebook emerged. While still being based on the same open
standards and protocols, the web became more centralized on the **application level**.

Social media solved many of the aforementioned issues and opened up the web to a broader,
non-tech-savvy user base by providing the following advantages:

- Easily create and share content (enabled by a baked-in identity system)
- Convenience of a personalized, curated news feed (promoting more relevant items and hiding less
  relevant ones)
- Easily discover new (and relevant) content
- Simple ways to interact with the content (such as through replies and likes)
- (Feedback loop and analytics that help content creators to sharpen their content)

However, this led to privacy concerns and the concentration of power is in stark contrast to one of
the original ideas of the web:

> _Decentralisation: No permission is needed from a central authority to post anything on the web,
> there is no central controlling node, and so no single point of failure … and no “kill switch”!
> This also implies freedom from indiscriminate censorship and
> surveillance._ - [History of the Web](https://webfoundation.org/about/vision/history-of-the-web/)

What if we could provide the convenience of a personalized, curated web feed without compromising
on privacy and decentralization?

## A decentralized, curated, and interactive web feed

In the following, I try to explore the idea of a decentralized web feed.

From the previous discussion, we can derive the following building blocks that would be needed to
allow users to follow websites and get a curated feed of content:

    Higher      +------------------+ +------------------------+ +-----------------------------+
    Layers      |                  | |                        | |                             |
      ↑         |   Social graph   | | Interaction / Feedback | |    Aggregation / Curation   |
      |         |                  | |                        | |                             |
      |         +------------------+ +------------------------+ +-- --------+                 |
      |         +--------------------------------+ +----------------------+ |                 | 
      |         |                                | |                      | |                 |
      |         |         Identity               | |    Content event     | |                 |
      |         |                                | |                      | |                 |
      |         +--------------------------------+ +----------------------+ +-----------------+
      |         +------------------------------------------+ +--------------------------------+
      |         |                                          | |                                |
      ↓         |  Decentralized communication & storage   | |              WWW               |
    Lower       |                                          | |                                |
    Layers      +------------------------------------------+ +--------------------------------+

### WWW

This base layer building block is already in place. It refers to the existing web of individual
websites that are connected through hyperlinks (aka the World Wide Web).

### Decentralized communication & storage

The other base layer building block is a sufficiently decentralized system that is needed for
storage and communication which are required by higher-level building blocks. Depending on the level
of decentralization, this could be a blockchain or some sort of federated system (such
as [ActivityPub](https://www.w3.org/TR/2018/REC-activitypub-20180123/), which also specifies
many of the other building blocks).

### Identity

The web itself initially did not have a baked-in identity system. Today, there are several
decentralized identity initiatives such as [W3C DID](https://www.w3.org/TR/did-core/). The notion of
a decentralized identity is important because it enables users to use to follow a website (which is
also represented by a decentralized identity) and interact with it.

### Social graph

To allow users to follow websites, some kind of persistent social graph is needed. This graph stores
the identities and their connections with each other (in this case, which users follow which
websites). It uses the identity building block to have unique identifiers for users and websites and
the decentralized communication & storage building block to persist the social graph. A persistent
social graph further eases the discovery of new websites.

The [Ethereum Follow Protocol](https://app.ethfollow.xyz/) (EFP) is an example of such a
decentralized social graph.

### Content event

A website needs to notify its followers when new content is published. This requires a structured
way to describe a content item. RSS or Atom could be leveraged for this. Additionally, some kind of
event system is needed to notify followers of new content. The notification event only needs to
contain the URL of the content item; the content itself (e.g. a blog post) can be fetched from the
publisher's website.

### Aggregation / Curation

To provide a personalized, curated feed of content, some kind of aggregation and curation is needed.

This could be implemented on the client side or using intermediary services provided by third
parties. One could imagine different aggregation services with different curation algorithms. The
user registers with an aggregation service of his choice. Then the service fetches all content items
and — based on previous views and interactions — creates a compelling feed.

### Interaction / Feedback

Users should be able to interact with content in their feed (e.g. like and comment on content items
or mention other users). They use their decentralized identity to interact with the content event,
which stores the interaction. Additional analytics such as the number of views could be stored to
improve the curation algorithm and provide feedback to content creators.

## Implementation

I can see many different ways to implement the vision of a decentralized web feed each having
different trade-offs (e.g. regarding their level of decentralization or usability).

[Aero Cast](https://github.com/moonstoneid/aero-cast) is a demo implementation of a decentralized
web feed that [@mkellnhofer](https://github.com/mkellnhofer) and I created to explore the idea. It
is based on the Ethereum blockchain which already provides many of the building blocks described
above.

![Overview](overview-light.png#gh-light-mode-only "Overview")
![Overview](overview-dark.png#gh-dark-mode-only "Overview")

In a nutshell, Aero Cast consists of the following components:

- **Publishers**: A publisher is an entity that creates content. This could be a website or a blog.
  Each publisher has its own Ethereum account. This account owns a publisher contract.
- **Subscribers**: A subscriber is an entity that consumes content. Each subscriber has its own
  Ethereum account and his personal subscriber contract. When a subscriber subscribes to a
  publisher, the publisher's address is stored as a subscription in the subscriber contract.
- **Registry**: The registry contract stores the list of publisher and subscriber contracts.
  It basically serves as a lookup table.
- **Aggregator**: The aggregator is a centralized service that creates a web feed for a subscriber.
  Many different aggregators could exist and the subscriber can choose which aggregator to use. The
  aggregator listens for new content events from subscribed publishers. It then fetches the content
  and creates a curated web feed.

Of course, this is just a demo implementation to show the feasibility of the idea and there are many
ways to improve it. For example, Aero Cast could be extended to allow subscribers to interact with
content.

## Final thoughts

My main goal in writing this article was to explore the idea of being able **to follow individual
websites** and create a decentralized web feed. There are certainly many initiatives that I'm not
aware of that are working on similar ideas (e.g. [Farcaster](https://www.farcaster.xyz/) or
the [fediverse](https://en.wikipedia.org/wiki/Fediverse)).

Another thought I wanted to capture is that the web — while being based on the idea of
decentralization using open standards and protocols — became
**centralized on the application level**. Today, a few centralized platforms control how content is
distributed and consumed. Blockchains provide a way to decentralize the application layer again.

Finally, I'm happy if some readers find value in this article or if it sparks new ideas. I would
be happy to hear your feedback.

## Acknowledgments

Thanks to [@mkellnhofer](https://github.com/mkellnhofer) for our valuable discussions on the idea of
a decentralized web feed. He also contributed the majority of the code for
the [Aero Cast](https://github.com/moonstoneid/aero-cast) demo.