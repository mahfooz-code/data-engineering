#   Ingestion

    After you understand the data source and the characteristics of the source system you’re using, you need to 
    gather the data.

    The second stage of the data engineering lifecycle is data ingestion from source systems.
    
    In our experience, source systems and ingestion represent the biggest bottlenecks of the data engineering lifecycle.
    The source systems are normally outside of your direct control, and might randomly become unresponsive or provide data of poor quality.
    As a result, data flow stops or delivers bad data for storage, processing, and serving.
    Unreliable source and ingestion systems have a ripple effect across the data engineering lifecycle.


#   Key engineering considerations for the ingestion phase
    When preparing to architect or build a system, here are some primary questions to ask yourself related to the ingestion stage.
    
    1. What's the use case for the data I'm ingesting?
    2. Can I re-use this data, versus having to create multiple versions of the same dataset?
    3. Where is the data going? What's the destination?
    4. How frequently will I need to access the data?
    5. In what volume will the data typically arrive?
    6. What format is the data in? Can my downstream storage and transformation systems handle this format?
    7. Is the source data in good shape for immediate downstream use? If so, for how long, and what may cause it to be unusable?
    8. If the data is from a streaming source, do I need to do any in-flight transformations?


#   Batch
    
    Batch ingestion is simply a specialized and convenient way of handling streaming data in a time-discrete way.
    Batch data is ingested either on a predetermined time interval or as data reaches a preset size threshold.
    Batch ingestion is a one-way door - once data is broken into batches, the latency for downstream consumers is inherently constrained.

    Due to factors that limited the ways that data could be processed, batch was - and still is - a very popular way to ingest data for downstream consumption, particularly in the areas of analytics and machine learning. 
    
    However, the separation of storage and compute in many systems, as well as the ubiquity of event streaming and processing platforms, make continuous processing of data streams much more accessible and increasingly popular.

    Why artificially constrain your data ingestion when you can simply consume streaming events as they organically occur?

    The choice largely depends on the use case and expectations for data timeliness.



#   Streaming
    Virtually all data we deal with is inherently streaming.
    That is, data is nearly always produced and updated continually at its source.
    
    Streaming ingestion allows us to provide data to downstream systems - whether other applications, databases, or analytics systems - in a continuous, real-time fashion.

    Here Real-time" (or "near real-time") means that the data is available to a downstream system a short time after it is produced, for example, less than one second later.

    The latency required to qualify as real-time varies by domain and requirements.



#   push

    In the push model of data ingestion, a source system writes data out to a target whether that be a database, object storage, or a file system.




#   Pull

    In the pull model, data is retrieved from the source system.
    
    In practice, the line between the push and pull paradigms can be quite blurry; often data is both pushed and pulled as it works its way through the various stages of a data pipeline.


#   Key considerations for batch versus stream ingestion
    Below are some questions to ask yourself when determining if streaming ingestion is an appropriate choice over batch ingestion:

    - If I ingest the data in real-time, can downstream storage systems handle the rate of data flow?

    - Do I need true, to the millisecond real-time data ingestion? Or would a micro-batch approach work where I accumulate and ingest data, say every minute?

    - What are my use cases for streaming ingestion? What specific benefits do I realize by implementing streaming? If I get data in real-time, what actions can I take on that data that would be an improvement upon batch?

    - Will my streaming-first approach cost more in terms of time, money, maintenance, downtime, and opportunity cost than simply doing batch?

    - Is my streaming pipeline and system reliable and redundant in the event of infrastructure failure?

    - What tools are most appropriate for the use case? Should I use a managed service (Kinesis, Pubsub, Dataflow), or stand up my own instances of Kafka, Flink, Spark, Pulsar, etc.? If I do the latter, who will manage it? What are the costs and tradeoffs?

    - If I'm deploying a machine learning model, what benefits do I have with online predictions, and possibly continuous training?

    - Am I getting data from a live production instance? If so, what's the impact of my ingestion process on this source system?

#   Push versus pull


#   ETL
    Consider, for example, the ETL (extract, transform, load) process, commonly used in batch-oriented ingestion workflows.
    
    The extract part of ETL makes it clear that we’re dealing with a pull ingestion model.

#   CDC (change data capture)
    
    One common method triggers a message every time a row is changed in the source database.
    This message is pushed to a queue where it is picked up by the ingestion system.
    Another common CDC method uses binary logs, which record every commit to the database.
    The database pushes to its logs.
    The ingestion system reads the logs but doesn’t directly interact with the database otherwise.
    This adds little to no additional load to the source database.
    Some versions of batch CDC use the pull pattern.
    For example, in timestamp-based CDC an ingestion system queries the source database and pulls the rows that have changed since the previous update.
    
