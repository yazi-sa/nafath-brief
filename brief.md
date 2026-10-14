Version: NAFATH-V3
Track: Cybersecurity

## Overview
A citizen uses a mobile application to ask an assistant a question about a public service. First, the mobile connection must be encrypted because personal information needs protection while traveling between the device and the server. Then, the question moves across the network, where IPv6 provides enough addresses for citizens' connected devices. Next, the AI assistant searches official documents and trusted sources to prepare an accurate answer instead of guessing or presenting unsupported information. Meanwhile, saved questions remain personal data even when names are replaced with codes, so the system must protect their privacy. Finally, the software API must follow clear versioning rules because any incompatible change requires a new MAJOR version. Together, these topics show how security, networking, reliable AI, privacy, and software maintenance support a trustworthy citizen service.

## Software
You increase MAJOR when a change to the public API breaks compatibility.
You increase MINOR when you add a new feature without breaking existing functionality, such as adding a new search option.
You increase PATCH when you fix a bug without affecting existing functionality, such as fixing an error in the response.
In this assistant, an example of a MAJOR change is removing an API endpoint that the mobile app needs to send questions and receive answers.

Resource: Semantic Versioning - https://semver.org/


## AI
RAG is a method that combines a language model with external information.
It works by searching for relevant texts from a knowledge source and using them to generate an answer.
It reduces incorrect answers because the model can use information from available sources instead of relying only on its training data. 
For this assistant, an example is answering a citizen’s question about government service fees using official government documents instead of guessing.

Resource: Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks - https://arxiv.org/abs/2005.11401

## Mobile
ATS is an Apple feature that keeps the connection between an app and its server safe from snooping and tampering.
It requires network connections to use TLS with trusted certificates and secure encryption.
If the app calls a plain HTTP endpoint, ATS blocks the connection by default.
For this assistant, this matters because citizens’ questions should stay private, so developers should use HTTPS to protect data while it is being sent.

Resource: Preventing Insecure Network Connections - https://developer.apple.com/documentation/security/preventing-insecure-network-connections

## Networking

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
