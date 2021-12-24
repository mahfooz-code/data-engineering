#   Storage
    After ingesting data, you need a place to store it.
    Choosing a storage solution is key to success in the rest of the data lifecycle, and it’s also one of the most complicated stages of the data lifecycle for a variety of reasons.

    Storage frequently occurs in multiple places in a data pipeline, with storage systems crossing over with processing, serving, and ingestion stages.

    For example, cloud data warehouses can store data, process data in pipelines, and serve it to analysts; streaming frameworks such as Kafka and Pulsar can function simultaneously as ingestion, storage, and query systems for messages; and object storage is a standard layer for the transmission of data.


#   Evaluating storage systems - key engineering considerations

    Here are a few key engineering questions to ask when choosing a storage system for a data warehouse, data lakehouse, database, object storage, etc.

    1. Is this storage solution compatible with the required write speeds for the architecture?

    2. Will storage create a bottleneck for downstream processes?

    3. Do you understand how this storage technology works? Are you utilizing the storage system optimally, or committing unnatural acts? For instance, are you applying a high rate of random access updates in an object storage system, an antipattern with significant performance overhead?

    4. Will this storage system handle anticipated future scale? You should take into account all capacity limits on the storage system: total available storage, read operation rate, write volume, etc.

    4. Will downstream users and processes be able to retrieve data in the required SLA?

    5. Are you capturing metadata about schema evolution, data flows, data lineage, and so forth? Metadata has a significant impact on the utility of data. Metadata represents an investment in the future, dramatically enhancing discoverability and institutional knowledge to streamline future projects and architecture changes.

    6. Is this a pure storage solution (object storage) or does it support complex query patterns (i.e., a cloud data warehouse)?

    7. Is the storage system schema-agnostic (object storage)? Flexible schema? (Cassandra) Enforced schema? (A cloud data warehouse)

    8. For data governance, how are you tracking master data, data quality, data lineage, and golden records?

    9. How are you handling compliance and data sovereignty? For example, can you store your data in certain geographical locations, but not others?


#   Data access frequency

    Not all data is accessed in the same way.
    Retrieval patterns will greatly vary, based upon the type of data being stored and queried.
    This brings up the notion of the "temperatures" of data.
    Data access frequency will determine what "temperature" your data is.
    Data that is most frequently accessed is called hot data.
    Hot data is commonly retrieved many times per day, perhaps even several times per second in systems that serve user requests. This is data that should be stored for fast retrieval, where "fast" is relative to the use case.

    Lukewarm data is data that might be accessed every so often, say every week or month.

    Cold data is seldom queried and is appropriate for storing in an archival system.

    Cold data is often data that is retained for compliance purposes, or in case of a catastrophic failure in another system.

    In the "old days," cold data would be stored on tapes and shipped to remote archival facilities.

#   Selecting a storage system

    What type of storage solution should you use? This depends on your use cases, data volumes, frequency of ingestion, format, and size of the data being ingested -- essentially, the key considerations listed above.

    There is not a one-size-fits-all universal storage recommendation. Every storage technology has its tradeoffs.

     Here are several popular storage options.

    1. Relational database management systems (RDBMS)
    2. Data lake
    3. Data warehouse
    4. Data lakehouse
    5. Streaming systems with data retention capabilities.
    6. Graph database
    7. In-memory (Redis, Memcached, etc)
    8. High performance NoSQL databases - RocksDB, etc
    9. Feature stores
    10. Data catalog
    11. Metadata stores
    12. Spreadsheets
