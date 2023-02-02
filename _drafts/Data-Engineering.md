---
layout: post
title: Data Engineering
---

Software engineering is like finance in that there is a lot of jargon and you just have to hang out with people who use the language until it all sinks in.  There will probably come a time when words like *throughput* and *atomicity* feel obvious to me, but for now they just feel really unnatural.  I pretty much look up *throughput* every time I read it (or hear it).  

Vocab and definitions come from *Designing Data-Intensive Applications* by Martin Kleppmann. 

### Part I : Foundations of Data Systems
#### Chapter 1: Reliable, Scalable, Maintainable Applications
* **data-intensive**  
An application where a limiting factor is the amount and complexity of the data it uses.  Compare to **compute-intensive** applications, where the limiting factor is CPU power.
* **data systems**  
Examples: databases, caches, search indexes, message queues
* **reliability**  
The ability for a system to work correctly, even in the face of software/hardware faults and human errors
* **fault**  
When one component of the system deviates from the spec
* **failure**   
When the system as a whole stops providing the required service to users
* **fault-tolerant** or **resilient**  
A system that can anticipate faults and prevent them from causing failures
* **scalability**  
The ability for a system to support growth in data volume, traffic volume, and complexity
* **throughput**  
The number of records we can process per second, or the total time it takes to run a job on a dataset of a certain size.  Mostly relevant when discussing batch processes.
* **response time**  
The time between a client sending a request and receiving a response (i.e. service time)
* **latency**  
The duration that a request is waiting to be handled (i.e., during which it is latent)
* **tail latency amplification**  
If a single user request makes multiple server calls in parallel, it only takes one slow call to make the entire request slow.
* **scaling up** or **vertical scaling**  
Moving to a more powerful machine
* **scaling out** or **horizontal scaling** or **shared-nothing architecture**  
Distributing the load to multiple machines
* **maintainability**  
The ability for others to keep up and adapt the system


#### Chapter 2: Data Models and Query Languages
* **NoSQL**  
Stands for Not Only SQL
* **polyglot persistence**  
The idea that different applications have different requirements, so that relational as well as non-relational databases will continue to both be important for the foreseeable future
* **normalization**  
Removing duplication for a database to decrease write overhead and reduce the risk of inconsistencies. 
* **storage locality**  
The opposite of normalization, when relevant data is split across multiple tables. 
* **document model**  
A model with good locality and less normalization.  Examples: JSON, XML.
* **schema-on-read**  
Schema is implicit in the data, and is only interpreted once the data is read.  Schema is not defined or enforced by the database.
* **schema-on-write**  
Schema is explicitly defined and enforced by the database
* **imperative language**  
A language in which you specify which operations to perform, and in which order
* **declarative language**   
A language in which you specify the pattern of data you want, but not how to procure that data.  Examples: SQL, CSS
* **Triple-Stores**  
A model in which all information is stored as (subject, predicate, object)

#### Chapter 3: Storage and Retrieval
* **log**  
Append-only data file (sequence of records)
* **log-structured storage engine**  
* **compaction**  
The process of throwing away duplicate keys in the log, and only keeping the most recent update for each key in order to conserve disk space
* **solid state drives** or **SSDs**
* **Sorted String Table** or **SSTable**  
Each log-structured storage segment of key-value pairs is sorted by key
* **memtable**  
An in-memory balanced tree data structure which holds the latest logs
* **Log-Structured Merge-Tree** or **LSM-Tree**
* **write amplification**  
The effect that one write to the database results in multiple disk writes (due to repeated compaction)
* **B-Tree**  
A self-balancing tree data structure that keeps data sorted and allows searches, sequential access, insertions, and deletions in logarithmic time. The B-tree is a generalization of a binary search tree in that a node can have more than two children.
* **blocks** or **pages**  
Units which the B-tree breaks the database into - typically about 4KB in size.  Each block or page is written one at a time.
* **branching factor**  
The number of references to child pages in one page of the B-tree
* **leaf page**  
A page containing individual keys and their values
* **write-ahead log** or **WAL** or **redo log**  
An append-only file to which every B-tree modification must be written before it can be applied to the pages of the tree itself.  Used in the event of a database crash.  
* **page-oriented storage engine**  
* **online transaction processing** or **OLTP**  
* **online analytical processing** or **OLAP**  
* **data warehouse**  
A database optimized for analaytics, i.e. OLAP
* **Extract-Transform-Load** or **ETL**  
The process of getting data into a warehouse
* **star schema** or **dimensional modeling**  
Data warehouse model with a central **fact table** which foreign keys into many **dimension tables**
* **snowflake schema**  
A variation on the star schema, where dimension tables are further subdivided into subdimensions
* **row-oriented**  
Storage layout of most OLTP databases
* **column-oriented storage**  
Storage layout for most OLAP databases.  Potentially faster for queries that only parse a few columns.  Also lends itself well to compression, since values tend to repeat a lot in a given column.
* **materialized view**  
A cache of common queries
* **data cube** or **OLAP cube**  
A common special case of a materialized view: a grid of aggregates grouped by different dimensions

#### Chapter 4: Encoding and Evolution
* **rolling upgrade**  
Deploying a new version a few nodes at a time, gradually working through all the nodes.  Allows new versions to be deployed without service interruptions.  
* **backward compatibility**  
Newer code can read data that was written by older code.  Usually can be explicitly handled by whoever writes the new code.  
* **forward compatibility**  
Older code can read data that was written by newer code.  Usually trickier to handle than backward compatibility, because it requires the older code to ignore additions made by newer versions of the code.
* **encoding** or **serialization** or **marshalling**  
Translation from an in-memory data structure (e.g. list, hash table, tree) into a sequence of bytes.  
* **decoding** or **deserialization** or **unmarshalling** or **parsing**  
The reverse of encoding.
* **server**  
Exposes an API over a network
* **service**  
The API exposed by the server
* **clients**  
In networks, the clients are web browsers
* **microservice architecture** or **service-oriented architecture**  
A style of software design where services are provided to the other components by application components, through a communication protocol over a network. The basic principles of service-oriented architecture are independent of vendors, products and technologies.  A service is a discrete unit of functionality that can be accessed remotely and acted upon and updated independently.  It is about how to compose an application by integrating distributed, separately-maintained and deployed software components. It is enabled by technologies and standards that make it easier for components to communicate and cooperate over a network, especially an IP network.
* **web service**  
When HTTP is used as the underlying protocol for talking to the service
* **REST**  
Stands for Representational State Transfer.  Popular approach to web services.  Not a protocol, but a design philosophy that builds upon the principles of HTTP.  Emphasizes simple data formats and is often associated with microservices.
* **SOAP**  
XML-based protocol for making network API requests.  Aims to be independent from HTTP.
* **remote procedure call (RPC)**  
The technique of making a local call and having it execute on a remote service somewhere.
* **location transparency**  
The use of names to identify network resources, rather than their actual location.[
* **futures (promises)**
* **message broker** or **message queue**  
A middleman which stores messages in an asynchronous message-passing system.
* **asynchronous**  
When you execute something synchronously, you wait for it to finish before moving on to another task. When you execute something asynchronously, you can move on to another task before it finishes.

### Part II: Distributed Data
#### Chapter 5: Replication
* **replica**  
Each node that stores a copy of the database
* **leader-based replication**  
A replication scheme where one replica is designated as the **leader** and the rest are **followers**.  All write requests must go to the leader; followers are read-only.
* **replication log** or **change stream**  
Sequential list of all the changes the leader makes to the database.  Each follower takes the log from the leader and updates its local copy of the database accordingly.
* **semi-synchronous** 
A leader-based replication system where one follower is synchronous and the rest are asynchronous.
* **failover**  
When the leader fails, and one of the followers is promoted to leader, which means that it must handle all client writes going forward and all followers must consume data changes from the new leader.
* **read-scaling architecture**  
In a leader-based architecture, you can increase the capacity for read-only requests by adding more followers.
* **eventual consistency**  
If you run the same query on a leader and on an asynchronous follower, you may get different results because not all writes have been reflected in the follower.  This inconsistency is a temporary state; eventually they will be the same.  
* **replication lag**  
The delay between a write happening on the leader and being reflected on a follower
* **read-after-write-consistency** or **read-your-writes consistency**  
A guarentee that if the user reloads the page, they will always see any updates they submitted themselves.  It makes no promises about aother users' updates.  
* **moving backward in time**  
When a reader see older data after previously seeing newer data.  Can happen if you read from different replicas that are not in sync.
* **monotonic reads**  
A guarantee that a reader will not go back in time.  One way to do this: always read from the same replica.
* **consistent prefix reads**  
If a sequence of writes happens in a certain order, then anyone reading those writes will see them appear in the same order. 
* **multi-leader replication**  
A replication architecture which has one leader per datacenter.  
* **last write wins (LWW)**  
A way of resolving multi-leader database conflicts.
* **replication topology**  
Describes the communication paths between leaders.  Most popular is **all-to-all** because it is most robust to leader failure.  
* **leaderless replication** or **Dynamo-style**  
A replication architecture in which any replica can accept writes.
* **anti-entropy process**  
A background process that constantly looks for differences in the data between replicas and copies missing data from one to another.  
* **quorum**  
If there are n replicas, and every write is confirmed by w nodes and every read reads from r nodes, and w + r > n.
* **sloppy quorum**  
Writes and reads still require w and r successful responses, but those may include nodes that are not among the designated n 'home' nodes for a value if the home nodes are not available.  
* **hinted handoff**  
Once a network interruption is fixed, any writes one node temporarily accepted on behalf of another node are sent to the appropriate 'home' nodes.
* **concurrent**  
Two operations where neither knows about or depends the other.
* **version vectors**  
The collection of version numbers from all the replicas.  

#### Chapter 6: Partitioning
* **hot spot**  
A partition with a disproportionately high load

#### Chapter 7: Transactions
* **commit**  
Operation at the end of a successful transation
* **abort** or **rollback**  
Operation at the end of an unsuccessful transaction
* **ACID**  
The safety guarantees provided by transactions: Atomicity, Consistency, Isolation, and Durability
* **BASE**  
The opposite of **ACID**.  Stands for *Basically Available, Soft State, and Eventual Consistency*.
* **atomic**  
Something that cannot be broken into smaller parts
* **durability**  
Once a transaction has committed successfully, any data it has written will not be forgotten, even if there is a hardware fault or the database crashes.
* **dirty read**  
When you read data from the database that has not been committed yet
* **dirty write**  
When you overwrite data that has not yet been committed to the database
* **nonrepeatable read** or **read skew**  
An anomaly in which a value read from the database changes during a transaction.
* **read committed**  
Level of transaction isolation which guarantees no dirty read or dirty writes.  Allows read skew. Default isolation level for PostgreSQL. 
* **snapshot isolation**  
Level of transaction isolation which guarentees no read skew.  Good for long-running, read-only queries such as back-ups and analytics.  Key principle: *readers never block writers, and writers never block readers*.  Database may need to keep multiple different versions of itself for different queries -- known as **multi-version concurrency control**.
* **lost update**  
A write conflict that occurs when two writers read the same value concurrently, then modify it and write it back.  The second write *clobbers* the first write.
* **write skew**  
A race condition involving two concurrent writers.
* **phantom**  
When a write in one transaction changes the result of a search query in another transaction. *Writers don't just block other writers, they also block other readers and vice versa*. 
* **materializing conflict**
* **stored procedure**
* **two-phase locking**  
Algorithm for implementing serializability.
* **deadlock**
* **serializable snapshot isolation**
* **predicate lock** 
* **index-range locking** 

#### Chapter 8: The Trouble with Distributed Systems

#### Chapter 9: Consistency and Consensus

### Part III: Derived Data
#### Chapter 10: Batch Processing
#### Chapter 11: Stream Processing
#### Chapter 12: The Future of Data Systems
