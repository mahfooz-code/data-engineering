#   Transformation
    The next stage of the data engineering lifecycle is transformation.
    As we mentioned, data can be ingested in its raw form, with no transformations performed.
    In most cases, however, data needs to be changed from its original form into something useful for downstream use cases.
    Without proper transformations, data will not be in an appropriate form for reports, analysis, or machine learning.
    Typically, the transformation stage is where data begins to create value for downstream user consumption.

#   Key considerations for the transformation phase
    When thinking about data transformations within the context of the data engineering lifecycle, it helps to consider the following.
    
    1. What's the cost and ROI of the transformation? All transformations should have an associated business value attached.2. Is the transformation expensive from a time and resource perspective?
    3. What value will the transformation bring downstream? In other words, what is the ROI of a transformation?
    4. Is the transformation as simple and self-isolated as possible?
    5. What business rules do the transformations support?
    6. During transformation, am I minimizing data movement between the transformation and the storage system?

    Data can be transformed in batch, or while streaming in-flight.
    Transformation is often entangled in other phases of the data engineering lifecycle.
    Typically, data is transformed in source systems or during ingestion.
    Business logic is a major driver of data transformation.
    Business logic is critical for obtaining a clear and current picture of business processes.


#   Examples
    For example, a source system may add an event timestamp to a record before forwarding it to an ingestion process.
    Or a record within a streaming pipeline may be "enriched" with additional fields and calculations before it's sent to a data warehouse.
    Transformations are ubiquitous in various parts of the lifecycle.
    Data preparation, data wrangling, and cleaning - all of these transformative tasks add value to end-consumers of data.

#   Batch transformation
    Batch transformations are overwhelmingly popular, but given the growing popularity of stream processing solutions 
    such as Flink, Spark, Beam, etc as well as the general increase in the amount of streaming data, we expect the popularity of streaming transformations to continue growing, perhaps entirely replacing batch processing in certain domains soon.

#   Stream transformation

#   Data featurization
    Data featurization for machine learning is another data transformation process.
    Featurization intends to extract and enhance features of data that will be useful for training machine learning models.
    Many machine learning processes require that data points be mapped into a vector space using one-hot encoding or embeddings. Featurization is something of a dark art, combining domain expertise (to identify which features might be important for prediction), with extensive experience in data science. For this book, the main point to take away is that once data scientists determine how to featurize data, featurization processes can be automated by data engineers in the transformation stage of a data pipeline.



