#   Data architecture
    A data architecture reflects the current and future state of data systems that support the long-term data needs and strategy of an organization.
    Because the data requirements of an organization will likely change very rapidly, and new tools and practices seem to arrive on a near-daily basis, data engineers must understand good data architecture. 

    A data engineer should first understand the needs of the business and gather requirements for new use cases.
    Next, a data engineer needs to translate those requirements to design new ways to capture and serve data, balanced for cost and operational simplicity.
    This means knowing the tradeoffs with design patterns, technologies, and tools in the areas of source systems, ingestion, storage, transformation, and serving data.

# Speed layer
The tools of the trade for the speed layer are Apache Spark Streaming, Apache Storm, and Apache Flink.

This is how everything comes together in Lambda architecture:

Incremental data from the source is concurrently pushed to the batch and speed layers.
The batch layer keeps accumulating the data over a certain period and refreshes the batch view after the period expires.


#   Lambda architecture
    Here are some case scenarios where you might use a Lambda architecture with great success:

    Access to near-real-time data
    
    There are scenarios in which the decision-making process is detrimentally impacted if access to the latest data is not available.

    Large historical datasets
    
    There are situations in which the historical data is extremely large, so aggregations can take a long time to finish and cannot be performed frequently.

    Dynamic nature of analytics (ad hoc)
    
    There are cases in which the case scenarios for data analytics are very dynamic and vary quite frequently.
    
    In this case, the batch and real-time views can be created or adjusted without affecting the underlying master data.


    A particular strength of the Lambda architecture is its strength to be easily migrated from traditional architecture. I have done several of these migrations in the past with great success.
    