---
layout: post
title: NoSQL Smackdown Postmortem, Part 2
---

Yesterday I wrote a [post](http://www.toluju.com/2010/03/30/nosql-smackdown-postmortem-part-1/) outlining the status of NoSQL, and what technology is involved. With the boring stuff out of the way, on to the more interesting questions regarding the NoSQL Smackdown. Where do the participants fit in? What do they have to say? Who cried uncle and ran home to mommy? 

On the one side, we have Cassandra and SimpleDB, which are both distributed database systems built with scalability concerns as the driving motivator. On the other side, we have CouchDB and MongoDB, both document databases with flexible schema and programmer-friendly data representations.

* [Cassandra](http://cassandra.apache.org/) originates from Facebook, which built the system as a means to store and deliver private messages between users. The system was released as open source, and is now under heavy development, with many high profile companies contributing both funds and code. The system has proven itself in a number of operational environments, including popular sites like Digg and Twitter.
* [SimpleDB](http://aws.amazon.com/simpledb/) was developed at Amazon as a means to manage shopping cart information. It applies some principles of Dynamo, a research project developed by Amazon researchers. SimpleDB is available for use in Amazon's cloud computing platform, at charge. While not open source, some implementation concepts are outlined in the research publications of the Dynamo project, and a number of open source implementations have arisen out of this public knowledge (of which Cassandra may be considered one).
* [CouchDB](http://couchdb.apache.org/) was one of the first document database systems to gain popularity. It was built as an open source system from the start, and notably was implemented in the rather novel [Erlang](http://en.wikipedia.org/wiki/Erlang_%28programming_language%29) programming language, a rather unusual choice for a database system.
* [MongoDB](http://www.mongodb.org) is also a document database system, built to satisfy many of the same needs CouchDB aims to address. It is also open source, but implemented in C++. There are a number of features that differentiate MongoDB from CouchDB, such as a custom built binary serialization format, or as of recent betas, automatic replication and sharding.

## Where's the beef?

One could wonder, which so many similarities between these systems, why all the disagreement? Well, even though these systems all make many of the same assumptions, and all aim to offer solutions where traditional RDBMS's have failed, there are strong opinions about which problems are most important to solve, and how exactly those problems must be solved. 

One major rift was between Werner Vogels and the other three contenders - as CTO of Amazon, Werner is representing a major enterprise, with strong business needs and shareholders to answer to. The other contenders are all open source. Though many businesses rely on open source, the divide between the corporate world and open source community is firmly entrenched, and heated debate has been waged across those lines for decades.

Another rift was between two obvious contenders - CouchDB and MongoDB. The two are competing in the same space, and are vying for the same audience. As a result, each attempted to one-up the other by trumpeting certain distinguishing features, ease of use, or specific performance benchmarks. 

Finally, there was also a rift in ideology. Both Cassandra and SimpleDB tout scalability concerns as the most pressing issue for many applications, while CouchDB and MongoDB place emphasis on a simpler data model for higher productivity and more agile development practices. While both Cassandra and SimpleDB also offer a unique data model, and both CouchDB and MongoDB promise scalability, the difference in focus is clear.

## The missing factor

One issue I felt wasn't very well addressed during these debates (and I voiced this as a question near the end), was how traditional RDBMS's fit into the picture. These systems have served us well for decades, and there is still much ongoing and exciting development in such traditional systems (e.g. [RethinkDB](http://rethinkdb.com/) or [Drizzle](https://launchpad.net/drizzle)). Stu was quick to counter that outgrowing hardware and machine failure can be painful and disastrous for a live application. I agree, but there are known solutions to dealing with such problems (e.g. master-slave replication and judicious use of data sharding). Werner gave a more elaborate rebuttal, mentioning that RDBMS's are used for several of Amazon's components, and that many, if not most of the applications deployed on the Amazon cloud platform make use of traditional database systems. This eventually led Amazon to release an [offering](http://aws.amazon.com/rds/) specifically centered around RDBMS's. I may not be sufficiently remembering the event, but I cannot recall the rebuttals from Wynn and Jan.

Another interesting mention made in closing remarks was a third ideology in the NoSQL movement - graph databases. Specifically mentioned was [Neo4J](http://neo4j.org/), a database capable of managing data stored in a graph consisting of millions of nodes. As mentioned in the last post, application objects are treated as nodes in a graph, so the mapping between such a database and an application may be even more natural than with document databases. Furthermore, certain complex operations such as deep graph traversal can have very high computational costs in non-graph based systems. These operations are trivial on a graph database, as such databases are built to optimize such operations. 

## Conclusion of sorts

One final thought I'd like to take away from this is that the days where a single system can be used for every job are over. There is no swiss army knife, there is no magic bullet when it comes to storing and managing data. Every application has unique needs; what works well for one application can be horrible solution for another. It is vital for modern application developers to be knowledgeable of their needs, problems that may arise, and what solutions are available. And perhaps more importantly, developers must be able to prioritize their needs accordingly. Everyone has scaling problems of some form, but does that really mean you need a fully distributed database system? Sometimes the old trusted "good enough" solution is just that - good enough.

My thoughts on the NoSQL Smackdown event end here, but there's much more to be said about NoSQL. Such as how to deal with the trolls. I'll keep you posted.
