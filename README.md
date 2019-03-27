# GPG44-45
An assesment of the Zonafide solution against HMG Good Practice Guides 44 and 45

# Introduction

Discussions with the UK Cabinet Office/GDS, the UK Department for Digital, Media, Culture and Sport, HMRC and others concluded that they see Zonafide as a facilitator of identity and entitlement proofing. This document sets out what our position had originally been on identity and how we compare to HMG Good Practice Guides for Identity Proofing (GPG44) and Identification of an Individual and Authentication and Credentials (GPG45) for use with HMG Online Services.

We, until recently, would have said Zonafide “Did not do Identity”. Our design principles focussed on People, Activities and Collaboration. Our focus was ensuring people could control the activities they were involved with and had an easy way to collaborate to stop imposters falsifying them. We felt identity was the focus of organisations wanting to “know” who people were to protect their business rather than the public. For example, organisations need to check credit information to reduce the risk of a bad debt or check a sanctions list to ensure they do not do business with someone resident in a prohibited country.

For Zonafide to be able to help people work together to stop fraud we needed to motivate organisations to collaborate as well. We met with a lot of them but, where they recognised the advantages for the public, they felt they had their own solutions to protect them. To collaborate they needed the product to provide benefits specifically for them. So over time we developed features of Zonafide that addressed problems they had AND ensured they acted on customers instructions and not imposters.

We also chose a use case in UK Register Services where the public could benefit from an easier way of proving marriage, birth and death for activities that required them. While focusing on that we learned of the problems the private sector had processing these events and also a number of problems across Government that our solution could help with. We were also able to develop an architecture where all the costs were borne by those parties needing the proofs so the public sector did not have to procure any technology or change existing systems or processes.

However, Zonafide is different. It's use of blockchain, smart contracts and a crypto token driven ecosystem does not have any precedent. So once people “get it” we still cannot find a way to progress because it doesn't fit into any category for procurement or engagement. Although the UK Government has recently changed its strategy regarding GOV.UK Verify the GDS did see how Zonafide fitted into that.

In considering what role Zonafide might play in GOV.UK Verify we assessed ourselves against GPG44 and GPG45. According to the Open Identity Exchange GOV.UK Verify is currently the only service to adhere to them. In doing this assessment we found it pointed out how these standards are based on assumptions about technology might not be applicable to blockchain. This was not just a good exercise for Zonafide but also for how other blockchain based solutions might assess themselves against these standards.

# Methodology

We have worked through GPG44 and 45 and attempted to consider each assessment characteristic. As the assumptions, or bias, about technology in the guides mean that the assessment characteristics are often not directly comparable we have provided some explanation. Those explanations themselves are also subject to opinion, assumption and interpretation so caution is advised.

We have put this document on GitHub so we can invite others to contribute to improve its accuracy. We encourage people to contribute and really appreciate any feedback.

We tackle GPG44 first and then GPG45.

GPG44 is Issue No. 2.0, October 2014

[GPG45](https://webarchive.nationalarchives.gov.uk/20150514214143/https://www.gov.uk/government/publications/identity-proofing-and-verification-of-an-individual) is Issue No. 2.3, July 2014

# GPG44 – Chapter 2 – Minimum Authentication Outcomes

## AC Element A: Credential Type

This relates to types of Credentials used to support Authentication to HMG online services. There are three categories whose scores relate to Level 1-3 of minimum outcomes.

**1** The credential in blockchain would be possession of a private key. Signing a transaction that includes the associated public key and submitting it to the network would prove that the user is in possession of the private key (Secret).

**3** The private key is a Credential type that demonstrates the user is in possession of something equivalent to a hardware or software token. The current requirement is biased to a particular technical solution and could be improved by spelling out support for cryptographic private keys

**Assessment: Score 3 = Level 3**

AC Element B: Quality of the Credential

This is about how the Credential is protected from compromise.

**2**

- Elliptic Curve Cryptography is generally considered a highly effective way of preventing prediction, duplication without direct access, tampering of a private key. Users would need to be aware of their responsibility to take the appropriate measures to protect their private keys.

- Need to check NIST SP 800-63-2 (reference(c)) and FIPS 140-2 Level 3 (reference(d))

**3**

- The user has the choice of products and services to prevent duplication, detect and prevent tampering and use algorithms meeting FIPS 140-2 Level 3 (reference(d))

- Of course a question has to be raised of whether the user can be trusted to take responsibility for this and whether an Identity Provider is considered my trustworthy.

**Assessment: Score 3 = Level 3**

## AC Element C: Management of the Credential

The criteria for assessment for managing a credential has a significant bias to a particular technology architecture. GPG44 has a role of Authentication Provider that we do not believe exists in a blockchain solution. In traditional systems the Credential itself is not controlled by the user. The user has to prove they have knowledge of a Credential that an Authentication Provider controls. This incongruency means some of the Criteria need analysis to discover what the real intent behind them is.

**1**

- Credentials are not stored by any other party than the user
- Another party, the Authentication Provider, cannot suspend, revoke, or restore a Credential. If the objective of this is to take control of a Credential on behalf of a user, in the case of a loss or theft, then this would be achieved by another means in a blockchain solution. For example, a service implemented as a smart contract might remove a public address from an access list.
- Another party, the Authentication Provider, cannot influence can change the state of a Credential only the services that credential has access to.
- Credentials are implicitly bound to one account, technically a public key, and the Authentication Provider has no control over that.
- The issuing process for a Credential is completely under the control of the user and an Authentication Provider has no control over that.
- The Credential is implicitly under the control of the user and an  Authentication Provider has no influence over that.
- The user can chose a tool provider to produce their Credentials and would make a choice based on marketed quality management processes.
- The tool used by a user for Credential creation and administration would be responsible for adherence to industry standards like ISO27001. **A point here is again whether the application feels users cannot be trusted to choose appropriate tools for their Credential management**.

