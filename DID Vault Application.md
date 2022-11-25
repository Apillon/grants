# DID Vault

- **Team Name:** Apillon
- **Payment Address:** Ethereum address: (USDC)
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2

> :exclamation: *The combination of your GitHub account submitting the application and the payment address above will be your unique identifier during the program. Please keep them safe.*

## Project Overview :page_facing_up:

### Overview
With this project we will implement DID Vault for Polkadot ecosystem. This will be a new service within the existing Web3 infrastructure. It will provide an encrypted storage of KILT or any other future Polkadot generated DID credentials. DID Vault is therefore a Web3, end to end encrypted way of storing user DID credentials, removing the need of DID local storage, management, usage of Sporran  wallet, and opening up the possibility of DID usage in future Web3 applications (mobile & web). 

DID Vault is a layer higher than KILT, therefore the DID's are generated and managed 100% on KILT protocol, but once created the users may store DID credentials in DID Vault. 
DID Vault also enables integration to other Web3 services, allowing users to login with their DID without the need of any wallets, DID.json files and other friction, which is currently present. 

Apillon Team is heavily motivated to build this project because we are building a Web3 development platform, which provides a simple SDK for building on top of KILT + CRUST + PHALA and other parachains that make sense within the Web3 context.  On Apillon, developers will be able to utilise the Authentication service to generate DID's for their end users on KILT. 

In order for adoption to happen, we want to make the use of wallets optional in the authentication and DID management process, while still allow users to fully utilise their DID's. In order to achieve that, we need to develop an end to end encrypted DID Vault within our platform and at the same time make it a standalone open source project for anyone to use and speed up the Web3 adoption. 

### Challenge
KILT protocol offers top level Web3 authentication and DID generation, but besides Sporran wallet, there are no friction-less ways for users to utilise their credentials. 

Even though Sporran wallet is fully functional, it represents “another wallet” in a series of wallets that Web3 users have to obtain using different services, which causes not only friction to onboard such users, but at the same time it increases the risk of data loss or loss of access.

There is also a high chance users who obtain digital identities, will store those on centralised servers, like Dropbox or Google Drive. Lastly, mandatory wallets complicate the usage in mobile native apps. 

### Project Details
We expect the teams to already have a solid idea about your project's expected final state. Therefore, we ask the teams to submit (where relevant):

#### UI and Flow Design

https://www.figma.com/file/85PjhVTfEUlG9BnxTRoKNE/AT-Wireframes-v0.1?node-id=22%3A2118&t=SHcbVz9BnbahAGLG-1

https://drive.google.com/file/d/15W8S1QzJ_rI5mhH155PoF93S7HGG1Yid/view?usp=sharing

https://www.figma.com/file/eTbGFYefjg5SGuipWKkeB1/Kilt?node-id=0%3A1

#### Flow description step by step

![technical diagram](https://github.com/Apillon-web3/grants/blob/main/Grant_Assets/vault_technical_diagram.png)

### DID Creation, attestation, encryption and storage - Diagram 1
1.  User creates account (Email + Pass)
2.  Hashing and encryption happens in the browser (client side)
3.  Apillon layer - Account is created in a central database, but all the data is already encrypted, coming from client side
4.  Generates email - This is the start of attestation, this actually sends a transactional email to the user. Once confirmed the attestation is passed. This is a normal attestation step that follows the KILT protocol. Multiple attestation options shall be available with email as first.
5.  DID - Full DID is issued on the KILT protocol - financed by the Apillon as the Attester
6.  Attested credentials are sent to the client from the Attester.
7.  Once the file is received at the client side, it is encrypted using the users strong password
8.  Once encrypted, the file is sent to Apillon server and stored

### Diagram 2 - Login scenario
1.  User initiates the login process
2.  User sends us email + hashed password
3.  We check the email + password match (up till here this is typical login scenario)
4.  If the login is passed, the encrypted DID is sent to the client
5.  Encrypted DID is decrypted using users “strong password”
6.  Once decrypted, user can operate with the DID as expected from DID functionality
7.  This part from the UI perspective and dev integration in websites works the same way as google login.
8.  DID is then validated and or used

### Diagram 3 - Social account recovery system - Optional
1.  User that already created DID in the previous step, now has the ability to add the recovery system to their DID by logging in successfully with the DID in adding a recovery trustee/buddy account
2.  In this scenario private/public keys are generated from the strong password and the public key is stored in our vault and associated with this specific user.
3.  Users may encrypt the strong password with the public key from the buddy and we store the encrypted password, allowing the initial user to recover lost DID using their trustee or buddy that was previously assigned to recover.

In the case user actually forgets the password the flow is the following:
1.  User sends a password request
2.  We confirm the identity of the user via support
3.  If confirmed the key is unlocked with two steps, first decryption happens via Apillon keys and the second from the users Buddy system

#### Technology stack
Technology stack consists of established mainstream web technologies that will enable large number of web developers to use and contribute to the project later on:

- javascript (typescript)
- rust (ink)
- vuejs
- nuxt

Additionally next SDKs and clients will be used:
- polkadot sdk
- kilt sdk
- crustio sdk
- ipfs client
- phala sdk


#### 2 phases of development
The project is organised in two phases. 

**Phase 1**
In phase 1 we are going to deliver the following: 
1. UI for Vault, where users can encrypt and upload their existing DID's storing them in the Vault
2. Client side encryption
3. Sending encrypted DID's to IPFS
4. Login with "DID Vault" functionality as a proof of concept
5. Functionality that pulls encrypted DID from the IPFS to the browser/client and is then decrypted with user password

This specific Grant application is intended only for Phase 1, which takes us to the usable proof of concept, of working Web 3 DID Vault. 

Phase 2 is planned as an upgrade at a later time and it upgrades the DID storage and retrieval significantly by implementing Phala Phat Contract. 


**Phase 2**
In phase 2 we are going to deliver the following: 
- UI upgrade, where users can also generate DID's and immediately push them to the Vault (phase 1)
- Upgrade the centralized computation power to Phala Phat Contract (proof of concept tested already)
- Social Recovery methods for additional recovery options



What is included in the package: 
- designs of UI components: #addlink
- technical backend flow: #addlink 
- data models #missing
- overview of technical stack: #addlink 
-  documentation of core components: #missing 
- MVP link: #missing 


### Ecosystem Fit

Help us locate your project in the Polkadot/Substrate/Kusama landscape and what problems it tries to solve by answering each of these questions:


### Where and how does your project fit into the ecosystem?

Project upgrades the existing DID solution as provided by KILT (ecosystem parachain) with a friction free, yet full Web3 compatible solution, that simplifies DID usage and speeds up DID authentication for all services using DID's, within Polkadot ecosystem, as well as for potential users. Giving simple access to DID's to mass of users, directly affects the adoption of all underlying services on Polkadot. 

### Who is your target audience (parachain/dapp/wallet/UI developers, designers, your own user base, some dapp's userbase, yourself)?
DID Vault targets all Web3 projects and their users. Anyone developing a Web3 project or a dApp that is planning to use or already using KILT network (or any other DID standard) for identity generation, management and authentication, may integrate DID vault to improve the authentication user experience and immediately speed up the onboarding of their users. 

Apillon also has a direct use case with the DID Vault, we are planning to integrate the Vault into our own platform, allowing developers building on Apillon, to utilise Vault authentication from the first version of their product, with seamless integration into rest of our infrastructure. 

### Are there any other projects similar to yours in the Substrate / Polkadot / Kusama ecosystem?
Only similar project could be the Sporran wallet, which also works with KILT generated DID's. 

  - If so, how is your project different?
  Our project still utilises the full scope of DID's, but bypasses the requirement of Sporran wallet. At the moment Sporran wallet supports only DID use case and is not compatible with mobile apps, making the overall usability limited.
  
  - If not, are there similar projects in related ecosystems?
  Ethereum has a similar solution: https://www.kepler.xyz/

## Team :busts_in_silhouette:

### Team members
- Team lead: Nino Kutnjak
- Names of team members:
	- Tadej Vengust
	- Mitja Kjuder
	- Luka Golinar
	

### Contact

- **Contact Name:** Ninoslav Kutnjak
- **Contact Email:** nino.kutnjak@apillon.io
- **Website:** apillon.io

### Legal Structure

- **Registered Address:** Address of your registered legal entity, if available. Please keep it in a single line. (e.g. High Street 1, London LK1 234, UK)
- **Registered Legal Entity:** Name of your registered legal entity, if available. (e.g. Duo Ltd.)

### Team's experience
Tadej Vengust is experienced Web3 developer and team lead that worked on a number of projects since 2017. Some of the most important are:
-   0xcert framework - open source SDK for NFT management - [https://github.com/0xcert/framework](https://github.com/0xcert/framework)
-   Official ERC721 reference implementation - [https://github.com/nibbstack/erc721](https://github.com/nibbstack/erc721)
-   Genobank (BIO NFTs) - [https://github.com/Genobank/biosample-permission-token](https://github.com/Genobank/biosample-permission-token)
-   ERC721 contract validator - [https://github.com/nibbstack/erc721-validator](https://github.com/nibbstack/erc721-validator)
-   Specron - smart contract testing environment - [https://github.com/specron](https://github.com/specron)
-   [Hiveterminal](https://www.hiveterminal.com/) - factoring platform
-   [https://credentify.eu/](https://credentify.eu/) - blockchain-secured stackable ECTS
-   AVL - Ensuring product authenticity through verifiable production data.
-   Iskratel - Reducing the risk of complaints through accurate compliance data.
-   IBO - Improving production process infrastructure with data traceability.
-   ESTIMATEGAS - live testing smart contracts -  https://github.com/fulldecent/live-testing-with-estimateGas/
Tadej is a lead architect for Apillon platform.
Luka Golinar is Apillon backend developer taking care of KILT integration from research to inplementation. 
Mitja Kjuder has years of experience in smart contracts and backend development. He has implemented a number of smart contracts for various DeFi and NFT projects audited by top audit  service providers.

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

We've done initial interviews with a number of stakeholders within the Polkadot ecosystem in order to get feedback on the relevance of the DID Vault for the ecosystem. The common feedback was very positive and amphasized the need for proposed solution.

In next step we've done initial hand in hand research with the KILT team evaluating the technical viability. Based on that we've defined three main user stories (https://github.com/Apillon-web3/grants/blob/main/Grant_Assets/vault_technical_diagram.png) and prepared initial wireframes (https://www.figma.com/file/85PjhVTfEUlG9BnxTRoKNE/AT-Wireframes-v0.1?node-id=22%3A2118&t=aV8m9lIf3TPV6fty-0).


## Development Roadmap :nut_and_bolt:

This section should break the development roadmap down into milestones and deliverables. To assist you in defining it, we have created a document with examples for some grant categories [here](../docs/grant_guidelines_per_category.md). Since these will be part of the agreement, it helps to describe _the functionality we should expect in as much detail as possible_, plus how we can verify and test that functionality. Whenever milestones are delivered, we refer to this document to ensure that everything has been delivered as expected.

Below we provide an **example roadmap**. In the descriptions, it should be clear how your project is related to Substrate, Kusama or Polkadot. We _recommend_ that teams structure their roadmap as 1 milestone ≈ 1 month.

> :exclamation: If any of your deliverables is based on somebody else's work, make sure you work and publish _under the terms of the license_ of the respective project and that you **highlight this fact in your milestone documentation** and in the source code if applicable! **Teams that submit others' work without attributing it will be immediately terminated.**

### Overview

- **Total Estimated Duration:** 2 months
- **Full-Time Equivalent (FTE):**  4 FTE
- **Total Costs:** 28,000 USD


### Milestone 1  — UI, upload and encrypt

- **Estimated duration:** 1 month
- **FTE:** 4
- **Costs:** 14,000 USD


| Number | Deliverable | Specification |

| -----: | ----------- | ------------- |

| **0a.** | License | Apache 2.0 / GPLv3 / MIT / Unlicense |

| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |

| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |

| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |

| 1. | Web app UI | We will build and publish the UI for DID Vault and enable client side upload + encryption of DID Vaults|



### Milestone 2 - Store to IPFS, retrieve and decrypt

- **Estimated duration:** 1 month
- **FTE:** 4
- **Costs:** 14,000 USD

| Number | Deliverable | Specification |

| -----: | ----------- | ------------- |

| **0a.** | License | Apache 2.0 / GPLv3 / MIT / Unlicense |

| **0b.** | Documentation | We will provide both **inline documentation** of the code and a basic **tutorial** that explains how a user can (for example) spin up one of our Substrate nodes and send test transactions, which will show how the new functionality works. |

| **0c.** | Testing and Testing Guide | Core functions will be fully covered by comprehensive unit tests to ensure functionality and robustness. In the guide, we will describe how to run these tests. |

| **0d.** | Docker | We will provide a Dockerfile(s) that can be used to test all the functionality delivered with this milestone. |

| 0e. | Article | We will publish an online video explaining how to use Vault for DID encryption and storage for users who already have DID's. |

| 1. | Fully functional backend | We will build and deploy beta ready DID Vault, where users will be able to upload, encrypt and store their DID's and use them to login to integrated services. |


## Future Plans
Immediately after milestones from this Grant are 

Please include here

- how you intend to use, enhance, promote and support your project in the short term, and
- the team's long-term plans and intentions in relation to it.


## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** 
We learned about the Grants Program on first Polkadot event in Slovenia in the lecture held by Urban Osvald. 


Here you can also add any additional information that you think is relevant to this application but isn't part of it already, such as:


### Previous relevant experience
Apillon's (Authtrail at that time) first production ready release was back in 2018 and it was an on chain solution for large scale data integrity. Solution worked as L2 while our goal was to handle large amount of structured and unstructured enterprise data. Main use cases were trusted product traceability and audit trails data integrity.

At first Ethereum network was chosen but later on we've decided switching to Moonbeam as we've recognized a great potential in Polkadot ecosystem. This release is relevant to show the team understands and knows how to develop encryption based solutions using blockchain. 

The data integrity module was successfully implemented with the following companies: 
- AVL List GmbH (https://www.avl.com)
- S&T Iskratel (https://www.iskratel.com)
- IBO GmbH (https://www.ibo-tec.de/en/)
- Hypex (https://hypex.si/en)

For that we've succesfully obtained two EU grants:

- Blockpool: https://blockpool.eu/25-selected-smes/kalmia-2/
- FED4SAE: https://fed4sae.eu/success-stories/betp/

- Work you have already done.
- If there are any other teams who have already contributed (financially) to the project.
- Previous grants you may have applied for.
