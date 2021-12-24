#   Analytics
    Analytics is the core of most data endeavors.
    Once your data is stored and transformed, you're ready to generate reports, dashboards, and do ad hoc analysis on the data.
    Whereas the bulk of analytics used to encompass business intelligence (BI), it now includes other facets such as operational analytics and customer-facing analytics. 
    Let's briefly touch on these variations of analytics

#   Business intelligence
    Business intelligence (BI) marshalls collected data to describe the past and current state of a business. 
    BI requires the processing of raw data using business logic.
    Note that data serving for analytics is yet another area where the stages of the data engineering lifecycle can get tangled.
    As we mentioned earlier, business logic is often added to data in the transformation stage of the data engineering lifecycle, but a logic-on-read approach has become increasingly popular.
    That is, data is stored in a cleansed but fairly raw form, with minimal business logic post-processing.
    A BI system maintains a repository of business logic and definitions.
    This business logic is used to query the data warehouse so that reports and dashboards accord with business definitions.
    As a company grows its data maturity, it will move from ad hoc data analysis to self-service analytics, which allows democratized data access to business users, without the need for IT to intervene.
    
    The capability to do self-service analytics assumes that data is in a good enough place that people across the organization can simply access the data themselves, slice and dice it however they choose, and get immediate insights from it.
    
    We find that though self-service analytics is simple in theory, it’s incredibly difficult to pull off in practice.
    
    The main reason is that poor data quality and organizational silos get in the way of allowing widespread use of analytics, free of gatekeepers such as IT or reporting departments.

#   Operational analytics
    Operational analytics focuses on the fine-grained details of operations, promoting actions that a user of the reports can act upon immediately. 
    For example, operational analytics could be a live view of inventory, or real-time dashboarding of website health.
    In this case, data is consumed in a real-time manner, either directly from a source system, from a streaming data pipeline such as AWS Kinesis or Kafka, or aggregated in a real-time OLAP solution like Druid.
    The types of insights in operational analytics differ from traditional BI since operational analytics is focused on the present and doesn’t necessarily concern historical trends.

#   Customer-facing analytics
    You may wonder why we've broken out customer-facing analytics separately from BI. 
    In practice, analytics provided to customers on a SAAS (Software as a Service) platform come with a whole separate set of requirements and complications.
    Internal BI faces a limited audience and generally presents a handful of unified views.
    Access controls are critical, but not particularly complicated.
    Access is managed using a handful of roles and access tiers.
    
    With customer-facing analytics, the request rate for reports, and the corresponding burden on analytics systems, goes up dramatically; access control is significantly more complicated and critical.
    Businesses may be serving separate analytics and data to thousands or more customers.
    Each customer must see their data and only their data.
    Where an internal data access error at a company would likely lead to a procedural review, a data leak between customers would be considered a massive breach of trust, likely leading to media attention and a significant loss of customers. Minimize your blast radius related to data leaks and security vulnerabilities.
    Apply tenant or data level security within your storage, and anywhere else there’s a possibility of data leakage.

#   MULTITENANCY
    Many modern storage and analytics systems support multi-tenancy in a variety of ways. Engineers may choose to house data for many customers in common tables to allow a unified view for internal analytics and machine learning. This data is presented externally to individual customers through the use of logical views with appropriately defined controls and filters. It is incumbent on engineers to understand the minutiae of multitenancy in the systems they deploy to ensure absolute data security and isolation.

