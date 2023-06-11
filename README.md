# DesignConcepts-and-Patterns
**************************************************************************************
https://leetcode.com/discuss/interview-question/system-design/3616948/golden-rules-to-answer-in-a-system-design-interview

𝐆𝐨𝐥𝐝𝐞𝐧 𝐑𝐮𝐥𝐞𝐬 𝐭𝐨 𝐚𝐧𝐬𝐰𝐞𝐫 𝐢𝐧 𝐚 𝐒𝐲𝐬𝐭𝐞𝐦 𝐃𝐞𝐬𝐢𝐠𝐧 𝐈𝐧𝐭𝐞𝐫𝐯𝐢𝐞𝐰
Sharing with you 30 golden rules to answer in System Design Interviews. The rules are as follows -

If we are dealing with a read-heavy system, it's good to consider using a Cache.

If we need low latency in the system, it's good to consider using a Cache & CDN.

If we are dealing with a write-heavy system, it's good to use a Message Queue for async processing

If we need a system to be an ACID complaint, we should go for RDBMS or SQL Database

If data is unstructured & doesn't require ACID properties, we should go for No-SQL Database

If the system has complex data in the form of videos, images, files etc, we should go for Blob/Object storage

If the system requires complex/heavy pre-computation like a news feed, we should use a Message Queue & Cache

If the system requires searching data in high volume, we should consider using a search index, tries or a search engine like Elasticsearch

If the system requires to Scale SQL Database, we should consider using Database Sharding

If the system requires High Availability, Performance, & Throughput, we should consider using a Load Balancer

If the system requires faster data delivery globally, reliability, high availability, & performance, we should consider using a CDN

If the system has data with nodes, edges, and relationships like friend lists, & road connections, we should consider using a Graph Database

If the system needs scaling of various components like servers, databases, etc, we should consider using Horizontal Scaling

If the system requires high-performing database queries, we should use Database Indexes

If the system requires bulk job processing, we should consider using Batch Processing & Message Queues

If the system requires reducing server load and preventing DOS attacks, we should use a Rate Limiter

If the system has microservices, we should consider using an API Gateway (Authentication, SSL Termination, Routing etc)

If the system has a single point of failure, we should implement Redundancy in that component

If the system needs to be fault-tolerant, & durable, we should implement Data Replication (creating multiple copies of data on different servers)

If the system needs user-to-user communication (bi-directional) in a fast way, we should use Websockets

If the system needs the ability to detect failures in a distributed system, we should implement a Heartbeat

If the system needs to ensure data integrity, we should use Checksum Algorithm

If the system needs to scale servers with add/removal of nodes efficiently, with no hotspots, we should implement Consistent Hashing

If the system needs to transfer data between various servers in a decentralized way, we should go for
Gossip Protocol

If the system needs anything to deal with a location like maps, nearby resources, we should consider using Quadtree, Geohash etc

Avoid using any specific technology names such as - Kafka, S3, or EC2. Try to use more generic names like message queues, object storage etc

If High Availability is required in the system, it's better to mention that system cannot have strong consistency. Eventual Consistency is possible

If asked how domain name query in the browser works and resolves IP addresses. Try to sketch or mention about DNS (Domain Name System)

If asked how to limit the huge amount of data for a network request like youtube search, trending videos etc. One way is to implement Pagination which limits response data.

If asked which policy you would use to evict a Cache. The preferred/asked Cache eviction policy is LRU (Least Recently Used) Cache. Prepare around its Data Structure and Implementation.
******************************************************************************************
**********************************************************************************************************************

https://www.linkedin.com/pulse/jwt-jws-jwe-omar-ismail/

**********************************************************************************************************************
**********************************************************************************************************************

https://www.linkedin.com/pulse/jwt-jws-jwe-omar-ismail/

**********************************************************************************************************************
**********************************************************************************************************************
Saga patterns
https://www.linkedin.com/pulse/saga-pattern-microservices-omar-ismail/

**********************************************************************************************************************
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
