#   Introducing data lakes



#   Accommodating varying data formats

    The most advertised benefit of a data lake is its ability to store structured, semi-structured, and unstructured data on a large scale. 
    The increasing variety of data sources that participate in the data analytics process has introduced a new challenge. Since there has not been an accepted standard around data exchange formats, it is pretty much up to the discretion of the data provider to choose one for you. Some commonly used data exchange formats and their common uses are listed as follows:

    Structured—Database rows
    Semi-Structured—Comma-separated values (CSV), Extensible Markup Language (XML), and JavaScript Object Notation (JSON).
    Unstructured—Internet of things (IoT), logs, and emails


#   Storing data in zones
    A data lake is a repository of data that stores data in various zones. 
    Although there are no limits or rules for how many zones are ideally required, three zones are generally considered the best practice: 
    1. raw 2. curated 3. transformed

    catalog and publish --> dashboard, customer.

    As data moves through each zone, it increases in maturity, becomes a lot cleaner, and finally achieves its true purpose for which it was originally collected: data analytics.

    Once data gets ingested from a variety of sources such as databases, files, application programming interfaces (APIs), and IoT in the raw zone, it passes through a wrangling (cleaning) process to validate, standardize, and harmonize it—in short, bring all data to a common level in terms of format and organizational standards. 
    
    After cleansing, data is saved to the curation zone


#   Transformed zone

    A typical set of transform operations include a combination of joining datasets, data aggregation, and data modeling. Finally, the results of the transformations are stored in the transformation zone. 
    
    Now, data is ready to make the final leg of its journey.

#   self-service model

    The next phase of processing is done in a self-service model. Various sub-groups within the analytics group—such as data analysts, data scientists, machine learning (ML) engineers, and artificial intelligence (AI) engineers—start transforming data as per requirements.

#   Accommodating varying data characteristics

#   Segregating storage and compute in a data lake

    The ability of a data lake to segregate (decouple) the storage and compute layers is perhaps one of its most desirable features. But why is decoupling storage and computation such a big deal? 

    Direct-attached storage (DAS)
    
    As the name suggests, a storage device (hard disk drive/solid-state drive, or HDD/SSD) is physically attached to the computer. This type of storage mostly exists in personal computers and laptops.
    
    Network-attached storage (NAS)
    
    Centralized storage using multiple hard drives connected as an array.
    NAS allows quick and easy sharing of data between computers using regular ethernet.

    Storage area network (SAN)
    
    High-performance shared storage using fiber-optic connectivity.
    A SAN allows for the fast sharing of data between computers.

    Cloud storage
    
    Cloud storage is a relatively recent addition to this list. 
    In this case, the storage physically exists on the cloud-provider servers. Cloud storage allows users the flexibility to access it from anywhere, as well as an assurance that data is highly available and safe because multiple copies are maintained on the backend.

    Azure Blob storage, Amazon Simple Storage Service (S3), and Google Cloud Storage are some of the best-known cloud storage solutions.


#   Block storage
    All storage types in the preceding list (except cloud storage) are categorized as file and block storage. This means data is stored on the storage device in small-sized blocks, usually 512 bytes in size. A group of contiguous blocks is deemed a file, and that is how humans relate to data.


#   Object storage

    Cloud storage is categorized as object storage. Object storage does not work like a traditional filesystem. Unlike block storage, every object contains the following:

    Identifier (id)
    
    A globally unique identifier (GUID) for each object in storage
    
    Data
    
    Stored as blobs all in one location (not broken into multiple blocks)
    
    Metadata
    
    Data about the data, such as author, permissions, and timestamps

    Object storage is quickly becoming the standard for data engineering and analytics operations due to certain key advantages, listed here:

    Object storage is highly scalable, which means the storage can grow as per the growing data demands within an organization.
    You save money because there is no requirement to book storage capacity in advance.
    The feature of embedding metadata within the object facilitates data classification and analytics workloads.
    Data can easily be accessed via HyperText Transfer Protocol (HTTP) or APIs.
    Very suitable for storing large files such as video, audio, images, and backups of data.
    Suitable for write-once, read-many-times scenarios such as data analytics.


    However, there are a few drawbacks as well, as outlined here:

    Performance of object storage is slower compared to block storage, particularly writing.
    Data cannot be appended to objects; any change to data simply amounts to deleting the existing object and recreating it.
    Suitable for workloads that require relatively static data.

    Since each change to an object amounts to deleting it and creating a new version, object storage is unsuitable for online transaction processing (OLTP) operations where data changes are very frequent. However, it is very suitable for online analytical processing (OLAP) operations because data changes infrequently.
    
#   Note
    While a data lake is a globally accepted term/concept, it may be implemented using a range of tools, services, and frameworks. It can be created using on-premises hardware, but the true power is realized when a data lake is created in the cloud.
    



