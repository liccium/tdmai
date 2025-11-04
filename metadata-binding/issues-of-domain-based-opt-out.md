# Issues of Domain-Based Opt-out

## Robots.txt

Robots.txt has become a practical way for rightsholders to express their preferences regarding the crawling of web-published content. It is simple to implement, widely adopted, and recognised as a standard mechanism across the web.

However, when it comes to expressing AI training preferences, this approach is inadequate for many stakeholders. Location- or domain-based methods do not effectively address the realities of how AI training data is collected and used, for the following reasons:

1. Most professional creators and rightsholders do not publish their content online;&#x20;
2. Copyrighted content is republished on the Internet without authorisation;
3. Content is shared on websites rightsholders do not control, such as social media platforms or licensor's websites.

Robots.txt is insufficient as a primary mechanism for protecting creators’ rights in the context of AI training. It only applies in cases where rightsholders have direct control over a domain, cannot account for works that are republished without authorisation, and fails to cover downstream licensing or reuse of creative assets. To ensure comprehensive protection for creators and rightsholders, AI governance frameworks must adopt more advanced approaches – such as asset-level or registry-based rights reservation – that operate independently of domain ownership and reflect the realities of modern content distribution.

### Most professional creators and rightsholders do not publish their content online

Many creators in industries such as music, film, book publishing, and audiobooks do not distribute and publish their content directly online. Yet, their works may already be used in AI training datasets through other means (e.g., data bundles, unauthorised uploads). Relying solely on robots.txt disregards creators whose content is included in datasets without ever being published on a controlled website.&#x20;

A more robust framework would require AI model developers or system providers to verify whether rights reservations are put in place at the asset or work level, independent of robots.txt implementation.

### Copyrighted content is republished on the Internet without authorisation.

Content frequently appears online without rightsholders' permission due to piracy, negligence, or ignorance. While banning crawling of websites on which pirated content is published may be a step forward, it fails to address cases of unauthorised republication on legal platforms. For example, copyrighted images may circulate on forums, blogs, or social media without any indication of their original source.

Robots.txt is ineffective here because those sharing the content may not be aware of the original rights reservation or may actively disregard it without any legitimate reason.

### Content is shared on websites rightsholders do not control, such as social media platforms

Robots.txt requires control over the hosting domain, making it ineffective for content distributed on third-party platforms, such as social media or licensing partners’ websites, where creators cannot implement their individual robots.txt settings.

For instance, a photographer's image licensed to a news outlet may be shared on social media, where the original robots.txt settings are neither implemented nor enforceable – neither by the original rightsholder nor the licensee. Even when creators use robots.txt on their own websites, they cannot ensure downstream compliance. Licensing terms are often dictated by the licensee further along the distribution chain, and economic constraints may prevent the licensor from enforcing robots.txt settings effectively.

\
