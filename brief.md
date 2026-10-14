Version: NAFATH-V3
Track: Cybersecurity

## Overview
A citizen uses a mobile application to ask an assistant a question about a public service. First, the mobile connection must be encrypted because personal information needs protection while traveling between the device and the server. Then, the question moves across the network, where IPv6 provides enough addresses for citizens' connected devices. Next, the AI assistant searches official documents and trusted sources to prepare an accurate answer instead of guessing or presenting unsupported information. Meanwhile, saved questions remain personal data even when names are replaced with codes, so the system must protect their privacy. Finally, the software API must follow clear versioning rules because any incompatible change requires a new MAJOR version. Lastly, prompt injection is a risk because external documents or webpages may contain hidden malicious instructions, so the assistant must treat external content as untrusted and validate instructions before following them.

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
IPv4 uses 32-bit addresses, which allow about 4.3 billion unique addresses. 
IPv6 uses 128-bit addresses, providing a much larger number of available addresses. 
This matters because 32 bits may not be enough for the growing number of devices connected to the internet. 
For this assistant, IPv6 helps ensure that citizens’ devices can have unique addresses when connected to the assistant.

Resource: Internet Protocol, Version 6 (IPv6) Specification - https://www.rfc-editor.org/rfc/rfc8200

## Cybersecurity
Prompt injection is an attack where user inputs change the model’s behavior in unexpected ways.
Direct prompt injection happens when a user types a command telling the model to reveal its hidden instructions.
Indirect prompt injection happens when the model reads external content, such as a web page or a file, that contains hidden commands.
Two ways to reduce prompt injections are adding safety instructions to guide the model and checking inputs to avoid unexpected behavior.

Resource: LLM01:2025 Prompt Injection - https://genai.owasp.org/llmrisk/llm01-prompt-injection/

## Data
Anonymization means removing identifying details so a person cannot be identified using any method that could realistically be used. 
Pseudonymization means replacing personal details with codes and keeping the extra identifying information separately. 
The difference is that properly anonymized data falls outside the GDPR, while pseudonymized data remains personal data. 
For this assistant, citizens’ questions could be stored using codes instead of names, but the data would still be personal data.

Resource: Regulation (EU) 2016/679 of the European Parliament and of the Council of 27 April 2016 (General Data Protection Regulation) - https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32016R0679

## Misconception in My Track
A common misconception is that prompt injection must appear as visible text that a human can easily notice. In fact, malicious instructions can be hidden in external content, such as a webpage or a file, and still affect an AI assistant if the model processes them. This matters for this assistant because it may read official documents or webpages to answer citizens’ questions, and hidden instructions could influence its response. This is supported by the section "LLM01:2025 Prompt Injection" in the OWASP page.

## Open Question
How can we test whether an AI assistant is vulnerable to hidden prompt injection in official documents, while ensuring that it still provides accurate answers based on trusted sources?
