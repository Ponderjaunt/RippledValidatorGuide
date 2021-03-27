# RippledValidatorGuide
Linux Rippled Validator Initialization Guide

# XRP Ledger Linux Validator Initialization Guide

*Author*

[Otter Rock Validation Services](https://otterrock.live/)

*Editors*

[Ponderjaunt](https://twitter.com/PonderJaunt) & 'Stifflips'

---

*This guide was compiled independently, without consultation with any named entity stated within. Unless otherwise amended, assume that this guide is NOT officially supported by any of the platforms mentioned below. Each platform has their own official documentation. This guide is an attempt to connect procedures from each platform, but these procedures may change at any point; users should expect that these procedures are experimental and that unforeseen risk exists within new technological services. Continue at your own risk. Please forgive any errors and omissions.*

*All content in this guide is information of a general nature and does not address the
circumstances of any particular individual or entity. Nothing in the guide constitutes professional
and/or financial advice, nor does any information in the guide constitute a comprehensive or
complete statement of the matters discussed or the law relating thereto.*

---

If you did find this guide useful, have feedback, or would like to make an XRP donation please visit the ‘About’ or ‘Contact us’ section of my website at [www.otterrock.live](http://www.otterrock.live). 

## Resources

⦁	[https://xrpl.org/](https://xrpl.org/)  
⦁	[https://github.com/ripple/validator-keys-tool](https://github.com/ripple/validator-keys-tool)  
⦁	[https://xrpl.org/overview.html](https://xrpl.org/overview.html)  
⦁	[https://xrpl.org/capacity-planning.html#amazon-web-services](https://xrpl.org/capacity-planning.html#amazon-web-services)  
⦁	[https://xrpl.org/xrp-ledger-toml.html#cors-setup](https://xrpl.org/xrp-ledger-toml.html#cors-setup)  

## Introduction

### What is XRP?

XRP is a digital asset that’s native to the XRP Ledger, an open-source, permission-less and decentralized block chain technology.

[Learn | XRPL.org](https://xrpl.org/overview.html)

### How Does the XRP Ledger Work?

The XRP Ledger is a decentralized cryptographic ledger powered by a network of peer-to-peer servers. The XRP Ledger uses a novel Byzantine Fault Tolerant consensus algorithm to settle and record transactions in a secure distributed database without a central operator.

XRP is a public, counterparty-free asset native to the XRP Ledger, and is designed to bridge the many different currencies in use worldwide. XRP is traded on the open-market and is available for anyone to access.

The complete instructions to install the Rippled Server and use it’s many features and functions including Validator operation is available on the [XRPL website](https://xrpl.org/run-rippled-as-a-validator.html).

This guide ought to be helpful to those in need of support and/or additional understanding on the process of running nodes on the XRPL.

*This XRPLD guide has been compiled for use on Fedora/RHEL/Centos OS variants may have different commands and can be translated to other Linux OS environments. This guide may be used for explanation in general for any use of the XRPL Validation process from test server to full production node.*

[Run rippled as a Validator | XRPL.org](https://xrpl.org/run-rippled-as-a-validator.html)

***Meeting these standards ensures stability, decentralization and growth for the entire network:***

- **Available**

    A good validator is always running and submitting validation votes for every proposed ledger. Strive for 100% uptime.

- **In agreement**

    A good validator's votes match the outcome of the consensus process as often as possible. To do otherwise could indicate that your validator's software is outdated, buggy, or intentionally biased. Always run the [latest `rippled` release](https://github.com/ripple/rippled/tree/master)  without modifications. [Watch `rippled` releases](https://github.com/ripple/rippled/releases)  to be notified of new releases.

- **Issuing timely votes**

    A good validator's votes arrive quickly and not after a consensus round has already finished. To keep your votes timely, make sure your validator meets the recommended [system requirements](https://xrpl.org/system-requirements.html), which include a fast internet connection.

- **Identified**

    A good validator has a clearly identified owner. Providing [domain verification](https://xrpl.org/run-rippled-as-a-validator.html#6-provide-domain-verification) is a good start. Ideally, XRP Ledger network UNLs include validators run by different owners in multiple legal jurisdictions and geographic areas. This reduces the chance that any localized events could interfere with the impartial operations of trusted validators.

[ripple/rippled](https://github.com/ripple/rippled)

### Why Run rippled as a Validator?

1. Structures a live connect to a distributed network of peers
2. Validates cryptographically signed transactions with consensus
3. Maintain a localized copy of the public global ledger

### Capacity Planning

It is important to plan now what size Validator you plan to run and how much capacity you are willing to allot for utility. In general, the size of the ledger will grow and minimum requirements will change as optimizations, ledger size, and network capacity change. Here's an overview of some of the technical specifications for XRPL network resources:

[https://xrpl.org/capacity-planning.html#amazon-web-services](https://xrpl.org/capacity-planning.html#amazon-web-services)

### Domain Setup

Please keep in mind that you may be exposing your IP address to the world when operating a Validator!

Locally operating an XRPL Node may reveal information about your network to the entire ledger, take steps to ensure you understand network security operational standards.

Assigning a domain to your node provides clarity of your intent in operating a Validator on the XRPL. Assigning a domain is not a requirement, but it is recommended to increase decentralization and awareness around which entities are acting as validators.

Please bear in mind that failure to understand what your validator is doing may result in errors, and failure to constantly maintain operation and storage requirements may result in the network degrading you as a servicer. You may see 'error code 73' as a result of not keeping the validator running efficiently or consistently. A list of validators ranked by their agreement, or consensus, on transactions over a period of time can be found below:

[XRP Ledger Explorer - XRPSCAN](https://xrpscan.com/validators)
