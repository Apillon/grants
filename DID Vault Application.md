# DID Vault

- **Team Name:** Apillon.io **(company LTD)**
- **Payment Address:** BTC, Ethereum (USDT/USDC/DAI) or Polkadot/Kusama (aUSD) payment address. Please also specify the currency. (e.g. 0x8920... (DAI))
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2

> :exclamation: *The combination of your GitHub account submitting the application and the payment address above will be your unique identifier during the program. Please keep them safe.*

## Project Overview :page_facing_up:

### Overview
This project will bring new service to the Web3 infrastructure: encrypted storage of KILT generated DID's. DID Vault is therefore a Web3, end to end encrypted way of storing users DID's, removing the need of DID local storage, management, usage of Sporran wallet, and opening up the possibility of DID usage in Web3 Mobile Apps. 

DID Vault is a layer higher than KILT, therefore the DID's are generated and managed 100% on KILT protocol, but once created the users may store DID's on DID Vault. 
DID Vault also enables integration to other Web3 services, allowing users to login with their DID without the need of any wallets, DID.json files and other friction, which is currently present. 

Apillon Team is heavily interested in building this project because we are building a Web3 development platform, which provides a simple SDK for building on top of KILT + CRUST + PHALA and other parachains that make sense within the Web3 context.  On Apillon, developers will be able to utilise the Authentication service to generate DID's for their end users on KILT. In order for adoption to happen, we want to make the use of wallets optional in the authentication and DID management process, while still allow users to fully utilise their DID's. In order to achieve that, we need to develop an end to end encrypted DID Vault within our platform and at the same time make it a standalone open source project for anyone to use and speed up the Web3 adoption. 

### Challenge
KILT protocol offers top level Web3 authentication and ID generation, but besides Sporran wallet, there are no friction-less ways for users to utilise their credentials. Even though Sporran wallet is fully functional, it represents “another wallet” in a series of wallets that Web3 users have to obtain using different services, which causes not only friction to onboard such users, but at the same time it increases the risk of data loss or loss of access. There is also a high chance users who obtain digital identities, will store those on centralised servers, like Dropbox or Google Drive. 


### Project Details

We expect the teams to already have a solid idea about your project's expected final state. Therefore, we ask the teams to submit (where relevant):

#### UI and Flow Design
https://www.figma.com/file/85PjhVTfEUlG9BnxTRoKNE/AT-Wireframes-v0.1?node-id=22%3A2118&t=SHcbVz9BnbahAGLG-1

https://drive.google.com/file/d/15W8S1QzJ_rI5mhH155PoF93S7HGG1Yid/view?usp=sharing

https://www.figma.com/file/eTbGFYefjg5SGuipWKkeB1/Kilt?node-id=0%3A1

#### Flow description step by step

### DID Creation, attestation, encryption and storage - Diagram 1

1.  User creates account (Email + Pass)
2.  Hashing happens in the browser (client side)
3.  Apillon layer - Account is created in a central database, but all the data is already encrypted, coming from client side
4.  Generates email - This is the start of attestation, this actually sends a transactional email to the user. Once confirmed the attestation is passed. ,
5.  DID - Full DID is issued on the KILT protocol - financed by the Apillon attester
6.  Attested credentials are sent to the client via our servers, which means the file is temporarily saved on our server - We are still looking how to optimise this step or upgrade it with specific solution to bypass our servers
7.  Once the file is back at the client side, it is encrypted using the users strong password
8.  Once encrypted, the file is sent to Apillon server and stored

### Diagram 2 - Login scenario

1.  User initiates the login process
2.  User sends us email + hashed password
3.  We check the email + password match (up till here this is typical login scenario)
4.  If the login is passed, the encrypted DID is sent to the client
5.  Encrypted DID is decrypted using users “strong password”
6.  Once decrypted, user can operate with the DID as expected from DID functionality
7.  DID is then validated and or used

### Diagram 3 - Social account recovery system

1.  User that already created DID in the previous step, now has the ability to add the recovery system to their DID by logging in successfully with the DID in adding a recovery trustee/buddy account
2.  In this scenario private/public keys are generated from the strong password and the public key is stored in our vault and associated with this specific user.
3.  Users may encrypt the strong password with the public key from the buddy and we store the encrypted password, allowing the initial user to recover lost DID using their trustee or buddy that was previously assigned to recover.

In the case user actually forgets the password the flow is the following:
1.  User sends a password request
2.  We confirm the identity of the user via support
3.  If confirmed the key is unlocked with two steps, first decryption happens via Apillon keys and the second from the users Buddy system

#### Data models
#TODO 

#### 2 phases of development
Project is organised in two phases. First phase works as a proof of concept where we implement DID Vault as an end to end encrypted **centralised** solution, inteded for testing purposes only. Once the centralised DID Vault is developed and has an ability to integrate with other Web3 services, we are starting the Phase two of the project where we swap out the centralised way of DID storage with either: 
- Phala Phat Contract
- IPFS + encryption storage
- CESS (native encryption storage)
- Smart contract solution

Second Phase requires a lot of research between all possible solutions in order to find the best one (best being the one with strongest Web3 use case and expected performance). First phase of implementation is therefore planned as an MVP, a Proof of Concept on which we can then build if it proves to be as demanded as it appears. We are also planning to file a Level 3 grant proposal once Phase 1 is concluded. 




- Mockups/designs of any UI components
- Data models / API specifications of the core functionality
- An overview of the technology stack to be used
- Documentation of core components, protocols, architecture, etc. to be deployed
- PoC/MVP or other relevant prior work or research on the topic
- What your project is _not_ or will _not_ provide or implement
  - This is a place for you to manage expectations and to clarify any limitations that might not be obvious

### Ecosystem Fit

Help us locate your project in the Polkadot/Substrate/Kusama landscape and what problems it tries to solve by answering each of these questions:

- Where and how does your project fit into the ecosystem?
- Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?
- What need(s) does your project meet?
- Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?
  - If so, how is your project different?
  - If not, are there similar projects in related ecosystems?

## Team :busts_in_silhouette:

### Team members

- Name of team leader
- Names of team members

### Contact

- **Contact Name:** Full name of the contact person in your team
- **Contact Email:** Contact email (e.g. john@duo.com)
- **Website:** Your website

### Legal Structure

- **Registered Address:** Address of your registered legal entity, if available. Please keep it in a single line. (e.g. High Street 1, London LK1 234, UK)
- **Registered Legal Entity:** Name of your registered legal entity, if available. (e.g. Duo Ltd.)

### Team's experience

Please describe the team's relevant experience. If your project involves development work, we would appreciate it if you singled out a few interesting projects or contributions made by team members in the past. For research-related grants, references to past publications and projects in a related domain are helpful.

If anyone on your team has applied for a grant at the Web3 Foundation previously, please list the name of the project and legal entity here.

### Team Code Repos

- https://github.com/<your_organisation>/<project_1>
- https://github.com/<your_organisation>/<project_2>

Please also provide the GitHub accounts of all team members. If they contain no activity, references to projects hosted elsewhere or live are also fine.

- https://github.com/<team_member_1>
- https://github.com/<team_member_2>

### Team LinkedIn Profiles (if available)

- https://www.linkedin.com/<person_1>
- https://www.linkedin.com/<person_2>

## Development Status :open_book:

If you've already started implementing your project or it is part of a larger repository, please provide a link and a description of the code here. In any case, please provide some documentation on the research and other work you have conducted before applying. This could be:

- links to improvement proposals or [RFPs](https://github.com/w3f/Grants-Program/tree/master/rfp-proposal) (requests for proposal),
- academic publications relevant to the problem,
- links to your research diary, blog posts, articles, forum discussions or open GitHub issues,
- references to conversations you might have had related to this project with anyone from the Web3 Foundation,
- previous interface iterations, such as mock-ups and wireframes.

## Development Roadmap :nut_and_bolt:

This section should break the development roadmap down into milestones and deliverables. To assist you in defining it, we have created a document with examples for some grant categories [here](../docs/grant_guidelines_per_category.md). Since these will be part of the agreement, it helps to describe _the functionality we should expect in as much detail as possible_, plus how we can verify and test that functionality. Whenever milestones are delivered, we refer to this document to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions, it should be clear how your project is related to Substrate, Kusama or Polkadot. We _recommend_ that teams structure their roadmap as 1 milestone ≈ 1 month.

> :exclamation: If any of your deliverables is based on somebody else's work, make sure you work and publish _under the terms of the license_ of the respective project and that you **highlight this fact in your milestone documentation** and in the source code if applicable! **Teams that submit others' work without attributing it will be immediately terminated.**

### Overview

- **Total Estimated Duration:** Duration of the whole project (e.g. 2 months)
- **Full-Time Equivalent (FTE):**  Average number of full-time employees working on the project throughout its duration (see [Wikipedia](https://en.wikipedia.org/wiki/Full-time_equivalent), e.g. 2 FTE)
- **Total Costs:** Requested amount in USD for the whole project (e.g. 12,000 USD). Note that the acceptance criteria and additional benefits vary depending on the [level](../README.md#level_slider-levels) of funding requested. This and the costs for each milestone need to be provided in USD; if the grant is paid out in Bitcoin, the amount will be calculated according to the exchange rate at the time of payment.

### Milestone 1 Example — Basic functionality

- **Estimated duration:** 1 month
- **FTE:**  1,5
- **Costs:** 8,000 USD

> :exclamation: **The default deliverables 0a-0d below are mandatory for all milestones**, and deliverable 0e at least for the last one. If you do not intend to deliver one of these, please state a reason in its specification (e.g. Milestone X is research oriented and as such there is no code to test).

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | Apache 2.0 / GPLv3 / MIT / Unlicense |
| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |
| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |
| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |
| 0e. | Article | We will publish an **article**/workshop that explains [...] (what was done/achieved as part of the grant). (Content, language and medium should reflect your target audience described above.) |
| 1. | Substrate module: X | We will create a Substrate module that will... (Please list the functionality that will be implemented for the first milestone. You can refer to details provided in previous sections.) |
| 2. | Substrate module: Y | The Y Substrate module will... |
| 3. | Substrate module: Z | The Z Substrate module will... |
| 4. | Substrate chain | Modules X, Y & Z of our custom chain will interact in such a way... (Please describe the deliverable here as detailed as possible) |
| 5. | Library: ABC | We will deliver a JS library that will implement the functionality described under "ABC Library" |
| 6. | Smart contracts: ... | We will deliver a set of ink! smart contracts that will...


### Milestone 2 Example — Additional features

- **Estimated Duration:** 1 month
- **FTE:**  1,5
- **Costs:** 8,000 USD

...


## Future Plans

Please include here

- how you intend to use, enhance, promote and support your project in the short term, and
- the team's long-term plans and intentions in relation to it.


## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Web3 Foundation Website / Medium / Twitter / Element / Announcement by another team / personal recommendation / etc.

Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:

- Work you have already done.
- If there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.
