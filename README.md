# aiga
Artificial Intelligence Governance Architecture (AIGA)

AIGA is an application-layer protocol for the discovery, authentication, and state management of Autonomous AI Agents. It provides a standardized mechanism for "Hardware-Enforced Accountability," utilizing Trusted Execution Environments (TEEs) and the IETF RATS architecture to solve the Time-of-Check Time-of-Use (TOCTOU) vulnerability in AI governance.

 Repository Contents

draft-aylward-aiga-2-00.xml: The authoritative source code for the Internet-Draft (xml2rfc v3 format).

draft-aylward-aiga-2-00.txt: The rendered text version for easy reading.

How to Build

This draft is authored in XML2RFC v3. To compile it locally:

Install the tool:

pip install xml2rfc


Render to Text (for review):

xml2rfc draft-aylward-aiga-2-00.xml --text


Render to HTML (for web):

xml2rfc draft-aylward-aiga-2-00.xml --html


Contributing

Contributions are welcome, particularly in aligning the transport mechanisms with SEAT and RATS working group standards.

Fork this repository.

Create a branch for your changes.

Submit a Pull Request (PR).

References

AI Governance Architecture:
https://datatracker.ietf.org/doc/draft-aylward-aiga-2/00/

IETF RATS Working Group:
https://datatracker.ietf.org/wg/seat/about/

IETF SEAT Working Group:
https://datatracker.ietf.org/wg/seat/about/

For an in-dept, interactive source of information, chat with the custom GEM 'AIGA - AI Governance Architecture' Bot powered by Gemini 3 Pro
https://gemini.google.com/gem/13vYlB0rlLsBzRIGhjxoJc0gE_Co0BkG0?usp=sharing

License

This work is intended for standardization within the IETF. Use of this content is subject to the IETF Trust Legal Provisions.


