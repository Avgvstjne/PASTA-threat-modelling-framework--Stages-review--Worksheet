# PASTA-threat-modelling-framework--Stages-review--Worksheet
---
**Scenario**

"You are part of the growing security team at a company for sneaker enthusiasts and collectors. The business is preparing to launch a mobile app that makes it easy for their customers to buy and sell shoes.
You are performing a threat model of the application using the PASTA framework. You will go through each of the seven stages of the framework to identify security requirements for the new sneaker company app.”

**Description:**
"Our application should seamlessly connect sellers and shoppers. It should be easy for users to sign-up, log in, and manage their accounts. Data privacy is a big concern for us. We want users to feel confident that we’re being responsible with their information.
Buyers should be able to directly message sellers with questions. They should also have the ability to rate sellers to encourage good service. Sales should be clear and quick to process. Users should have several payment options for a smooth checkout process. Proper payment handling is really important because we want to avoid legal issues."
---
[PASTA worksheet.pdf](https://github.com/user-attachments/files/24785803/PASTA.worksheet.pdf)

---
### **Review of each stage of this PASTA threat modelling exercise:**

# Stage I: Define business and security objectives
Summary:
We define the objectives early by asking broad questions about the purpose of the application like how does the app make the business money? and understanding the answer can help guide the details in our work.

Recommendations:
A shopping application like this will need to process payments and because of that we know certain technologies are required to keep information private and secure and that everything will need to be compliant with PCI-DSS.

# Stage II: Define the technical scope
Summary:
Our objective here is to understand the attack surface by identifying the technologies being used by the application and understanding their dependencies.

Recommendations:
We prioritize APIs because they facilitate the exchange of data between customers, partners, and employees. They will handle heaps of sensitive data and connect various users and systems together. But, we need to consider details like which APIs are being used before we prioritize one technology over another.

# Stage III: Decompose the application
Summary:
Following the previous stage we investigate how the application's components communicate together. Our objective here is to review how the application works and how security controls are currently implemented.

Recommendations:
We use a data flow diagram that shows how a typical search request passes through multiple layers. Then we NEED to make sure that the MySQL database is using prepared statements when queries are inputed.

# Stage IV: Threat analysis
Summary:
Here we mainly focus on the type of data the application will be processing and the types of threats that might affect the application. This relates to the technologies we've already scoped.

Recommendations:
To effectively implement information security responsibilities, it is important to consider the technological attack surface and any relevant threats to the product. Injection attacks are common for SQL databases. Session hijacking is possible because the app communicates cookies between multiple layers.

# Stage V: Vulnerability analysis
Summary:
Here we associate asset vulnerabilities with potential threats in order to identify what is wrong with the design of the app or its codebase based on security testing.

Recommendations:
We would need to have prepared statements to avoid making our SQL database vulnerable to injection attacks. And session hijacking is possible if cookies are mishandled between input and output sources.

# Stage VI: Attack modelling
Summary:
Our objective here is to link the threats and vulnerabilities identified in the previous steps using attack trees because we need to show that the potential threats that we've identified are actually viable. 
Useful resources like MITRE ATT&CK and the CVE® list will help to find evidence that validates the information modelled in the attack tree.

Recommendations:
We use the attack tree to model how user data is vulnerable to the attacks that were identified earlier. Like the data flow diagram, an actual attack tree for a mobile application would be much more complex than displayed in the worksheet.

# Stage VII: Risk analysis and impact
Summary:
For the final stage of PASTA our main goal here is to identify ways to mitigate the risks that were identified from stages IV - VI and plan for any remaining risks that can't be remediated.

Recommendations:
Some examples of technical, operational, and managerial controls that can be implemented before launch to reduce risk are SHA-256, incident response procedures, password policy, and principle of least privilege.
