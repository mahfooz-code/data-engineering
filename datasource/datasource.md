#   Evaluating source systems - key engineering considerations

    Below are some important characteristics of source systems that data engineers must think about.
    
    This is by no means an exhaustive list, but rather a starting set of evaluation questions.
    
    1. What are the basic characteristics of the data source? Is it an application? A swarm of IoT devices?
    
    2. How does the source handle state?
    
    3. At what rate is data generated? How many events per second? How many GB per hour?
    
    4.What level of consistency can data engineers expect in the output data?
    
    5. How often do errors occur?
    
    6. Will the data contain duplicates?
    
    7.Will some data values arrive late, possibly much later than other messages produced at the same time?
    
    8. What is the schema of the ingested data? Will data engineers need to join across several tables or even several systems to get a full picture of the data?
    
    9. If schema changes - say, a new column is added - how is this dealt with and communicated to downstream stakeholders?
    
    10. How frequently should data be pulled from the source system?
    
    11. For stateful systems, i.e. a database tracking customer account information, is data provided as periodic snapshots or as update events (CDC)? What’s the logic for how changes are performed, and how are these tracked in the source database?
    
    12. Who/what is the data provider that will transmit the data for downstream consumption?
    
    13. Will reading from a data source impact its performance?
    
    14. Does the source system have upstream data dependencies? What are the characteristics of these upstream systems?
    
    15. Are data quality checks in place to check for late or missing data?

    16. Data engineers also need to understand the limits of the source systems they interact with.


#   Datsource

    This includes human-generated spreadsheets, IOT sensors, web and mobile applications, and everything in between.


#   Challenges with source system
    One of the most challenging nuances of source data is a schema.
    The schema defines the hierarchical organization of data.

    One popular model is schemaless.

#   Data transmission
    There are numerous ways to transmit data from a source, including:

    1. Programmatically
    2. Message brokers
    3. APIs
    4. RPC
    5. Streams
    6. Output files




