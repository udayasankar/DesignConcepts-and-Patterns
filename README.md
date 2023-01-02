# DesignConcepts-and-Patterns
***********************************************************************************************************************

𝟭) 𝗖𝗔𝗣/𝗣𝗔𝗖𝗘𝗟𝗖 𝗧𝗵𝗲𝗼𝗿𝗲𝗺𝘀
With the help of these two theorems, distributed systems can choose a good balance between Consistency, Availability, Partition Tolerance, and Latency.

Details: https://lnkd.in/dTFksWj9


𝟮) 𝗠𝗲𝗿𝗸𝗹𝗲 𝗧𝗿𝗲𝗲
Identify data inconsistencies between servers.

Distributed systems store multiple copies of data on different servers for high availability and better reliability. Any replica server can contain a lot of data. Merkle Trees are used to identify inconsistencies in data between replicas. Naively splitting up the entire data range to calculate checksums for comparison is not very feasible; there is simply too much data to be transferred. Instead, we can use the Merkle tree to compare replicas of a range.

Details: https://lnkd.in/gZpt67uU


𝟯) 𝗕𝗹𝗼𝗼𝗺 𝗙𝗶𝗹𝘁𝗲𝗿
Bloom filters are used to quickly find if an element might be present in a set.

Details: https://bit.ly/3TbSAsR


𝟰) 𝗖𝗼𝗻𝘀𝗶𝘀𝘁𝗲𝗻𝘁 𝗛𝗮𝘀𝗵𝗶𝗻𝗴
Distributed systems use Consistent Hashing to distribute data across servers.

Consistent Hashing helps with two things:
1. It maps data to physical servers. Whenever the system wants to read or write data, Consistent Hashing tells us which server holds the data.
2. It ensures that only a small set of keys move when servers are added or removed.

Details: https://lnkd.in/dJQKjN6i


𝟱) 𝗚𝗼𝘀𝘀𝗶𝗽 𝗣𝗿𝗼𝘁𝗼𝗰𝗼𝗹
Used for efficiently sharing state information between servers.

Each server keeps track of state information about other servers in the cluster and gossips (i.e., shares) this information with one random server every second. This way, eventually, each server gets to know about the state of every other node in the cluster.

Details: https://bit.ly/3D2w14j


𝟳) 𝗛𝗲𝗮𝗿𝘁𝗯𝗲𝗮𝘁
Used for broadcasting the health status of a server.

Each server periodically sends a heartbeat message to a central monitoring server or other servers in the system to show that it is still alive and functioning.

Details: https://bit.ly/3eFnT04

****************************************************************************************************************************
************************************************************************************************************************

From simple to complex, here is my understanding of user identity management:

🔹WWW-Authenticate is the most basic method. You are asked for the username and password by the browser. As a result of the inability to control the login life cycle, it is seldom used today.
🔹A finer control over the login life cycle is session-cookie. The server maintains session storage, and the browser keeps the ID of the session. A cookie usually only works with browsers and is not mobile app friendly.
🔹To address the compatibility issue, the token can be used. The client sends the token to the server, and the server validates the token. The downside is that the token needs to be encrypted and decrypted, which may be time-consuming.
🔹JWT is a standard way of representing tokens. This information can be verified and trusted because it is digitally signed. Since JWT contains the signature, there is no need to save session information on the server side.
🔹By using SSO (single sign-on), you can sign on only once and log in to multiple websites. It uses CAS (central authentication service) to maintain cross-site information
🔹By using OAuth 2.0, you can authorize one website to access your information on another website

**********************************************************************************************************************

********************************************************************************************************************************************************************

https://github.com/Sairyss/domain-driven-hexagon

https://docs.github.com/en/graphql/overview/about-the-graphql-api

********************************************************************************************************************************************************************
***********************************************************************************************************************************************************************
Architectural Styles vs. Architectural Patterns vs. Design Patterns
Chapter 3: Architectural Patterns and Styles: https://learn.microsoft.com/en-us/previous-versions/msp-n-p/ee658117(v=pandp.10)?redirectedfrom=MSDN

https://herbertograca.com/2017/11/16/explicit-architecture-01-ddd-hexagonal-onion-clean-cqrs-how-i-put-it-all-together/

https://herbertograca.com/dev-theory-articles-listing/

https://herbertograca.com/2017/07/28/architectural-styles-vs-architectural-patterns-vs-design-patterns/

https://en.wikipedia.org/wiki/Software_design_pattern

https://en.wikipedia.org/wiki/Software_design_pattern


********************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************

https://martinfowler.com/articles/patterns-of-distributed-systems/

https://www.lewis-lin.com/blog/pedals-method

https://sre.google/workbook/non-abstract-design/

hierarchical-timing-wheels

https://blog.acolyer.org/2015/11/23/hashed-and-hierarchical-timing-wheels/

https://www.confluent.io/blog/apache-kafka-purgatory-hierarchical-timing-wheels/

http://www.cs.columbia.edu/~nahum/w6998/papers/sosp87-timing-wheels.pdf

********************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************



GRASP (object-oriented design)

General Responsibility Assignment Software Patterns (or Principles), abbreviated GRASP, is a set of "nine fundamental principles in object design and responsibility assignment"[1]: 6  first published by Craig Larman in his 1997[citation needed] book Applying UML and Patterns.

The different patterns and principles used in GRASP are controller, creator, indirection, information expert, low coupling, high cohesion, polymorphism, protected variations, and pure fabrication.[2] All these patterns solve some software problem common to many software development projects.
