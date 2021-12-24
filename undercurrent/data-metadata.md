Metadata
Metadata is “data about data”, and it underpins every section of the data engineering lifecycle. Metadata is exactly the data needed to make data discoverable and governable.

We divide metadata into two major categories: auto-generated and human generated. It goes without saying that modern data engineering revolves around automation, but too often, metadata collection is still a manual, error prone process.

Technology can assist with this process, removing much of the error-prone work of manual metadata collection. In some sense, we’re now in the golden age of metadata management. We’re seeing a proliferation of data catalogs, data lineage tracking systems and metadata management tools. Tools can crawl databases to look for relationships and monitor data pipelines to track where data comes from and where it goes. A low-fidelity manual approach is to use an internally-led effort where metadata collection is crowdsourced by various stakeholders within the organization.

Metadata becomes a byproduct of data and data processes, useful exhaust. However, key challenges remain. In particular, interoperability and standards are still lacking. Metadata tools are only as good as their connectors to data systems, and their ability to share metadata with each other. In addition, automated metadata tools should not entirely take humans out of the loop.

Data has a social element - each organization accumulates social capital and knowledge around processes, datasets, and pipelines. Human-oriented metadata systems focus on the social aspect of metadata. This is something that Airbnb has emphasized in their various blog posts on data tools, particularly their original Data Portal concept. Such tools should provide a place to disclose data owners, data consumers, domain experts, etc. Documentation and internal wiki tools provide a key foundation for metadata management, but these tools should also integrate with automated data cataloging as mentioned above. For example, data scanning tools can generate wiki pages with links to relevant data objects.

Once metadata systems and processes exist, data engineers can consume metadata in all kinds of useful ways. Metadata becomes a foundation for designing pipelines and managing data throughout the lifecycle.

DMBOK identifies four main categories of metadata that are useful to data engineers.

Business metadata

Technical metadata

Operational metadata

Reference metadata

Let’s briefly describe each category of metadata.
Business metadata
Business metadata relates to how data is used in the business, including business and data definitions, data rules and logic, how and where data is used, the data owner(s), and so forth.

A data engineer uses business metadata to answer non-technical questions about “who”, “what”, “where”, and “how”. For example, a data engineer may be tasked with creating a data pipeline for customer sales analysis. But, what is a “customer”? Is it someone who’s purchased in the last 90 days? Or someone who’s purchased at any time the business has been open? To use the correct data, a data engineer would refer to business metadata (data dictionary or data catalog) to look up how a “customer” is defined. Business metadata provides a data engineer the right context and definitions to properly use data.

Technical metadata
Technical metadata describes the data created and used by systems across the data engineering lifecycle. It includes the data model and schema, data lineage, field mappings, pipeline workflows, and much more. A data engineer uses technical metadata to create, connect, and monitor various systems across the data engineering lifecycle.

Here are some common types of technical metadata that a data engineer will use.

Pipeline metadata (often produced in orchestration systems.)

Data Lineage

Schema

Orchestration is a central hub that coordinates workflow across various systems. Pipeline metadata captured in orchestration systems provides the details of the workflow schedule, system and data dependencies, configurations, connection details, and much more.

Data lineage metadata tracks the origin and changes to data, and its dependencies, over time. As data flows through the data engineering lifecycle, it evolves through transformations and combinations with other data. Data lineage provides an audit trail of data’s evolution as it moves through various systems and workflows.

Schema metadata describes the structure of data that is stored in a system such as a database, a data warehouse, a data lake, or a file system; it is one of the key differentiators across different types of storage systems. Object stores, for example, don’t manage schema metadata - instead, this must be managed in a system like the Hive Metastore. On the other hand, cloud data warehouses manage schema metadata for engineers and users.

These are just a few examples of technical metadata that a data engineer should know about. This is not a complete list, and we’ll cover additional aspects of technical metadata throughout the book.

Operational metadata
Operational metadata describes the operational results of various systems and includes statistics about processes, job ids, application runtime logs, data used in a process, error logs, etc. A data engineer uses operational metadata to determine whether a process succeeded or failed and the data involved in the process.

Orchestration systems can provide a limited picture of operational metadata, but the latter still tends to be scattered across many systems. A need for better quality operational metadata, and better metadata management, is a major motivation for next-generation orchestration and metadata management systems.

Reference metadata
Reference metadata is data used to classify other data. This is also referred to as “lookup” data. Standard examples of reference data are internal codes, geographic codes, units of measurement, internal calendar standards. Note that much of reference data is fully managed internally, but items such as geographic codes might come from external standard references. Reference data is essentially a standard for interpreting other data, so if it changes at all, this change happens slowly over time