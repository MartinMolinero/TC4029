# Databases

## Jafari, R. (2022). Hands-On Data Preprocessing in Python. 

- databases are technological solutions to record and retrieve data effectively and efficiently.
-  We want databases to be good at what they are meant to do: the effective and efficient storage and retrieval of data. We want a database to be fast, accurate, and secure. We also want a database to be able to serve our needs as regards quick sharing and synching.

- databases are not designed to serve our analytics purposes. So, it should not be a surprise that the data in the database is organized in a way that serves its functions – the effective and efficient storage and retrieval of data – rather than being organized for our analytics purposes.

- locate and collect data from various databases and sources, and reorganize it into a dataset that has the potential to answer questions about our decision-making environment

- data might be coming from one database but, all the same, the data needs to be reorganized into a dataset that is designed for our analytics needs.

- We did define a database as a technological solution for storing and retrieving data both effectively and efficiently. However, a dataset is a specific organization and presentation of some data for a specific reason.

- The "specific reason" for such a dataset is the analytics goals and the "specific organization and presentation" of that dataset is to support those goals.


## Amazon AWS (2022). Data Warehouse Concepts

- A data warehouse is a central repository of information that can be analyzed to make more informed decisions. Data flows into a data warehouse from transactional systems, relational databases, and other sources, typically on a regular cadence.

- Data and analytics have become indispensable to businesses to stay competitive. Business users rely on reports, dashboards, and analytics tools to extract insights from their data, monitor business performance, and support decision making. Data warehouses power these reports, dashboards, and analytics tools by storing data efficiently to minimize the input and output (I/O) of data and deliver query results quickly to hundreds and thousands of users concurrently.

- A data warehouse architecture is made up of tiers. The top tier is the front-end client that presents results through reporting, analysis, and data mining tools. The middle tier consists of the analytics engine that is used to access and analyze the data. The bottom tier of the architecture is the database server, where data is loaded and stored

-  Data is stored in two different types of ways: 1) data that is accessed frequently is stored in very fast storage (like SSD drives) and 2) data that is infrequently accessed is stored in a cheap object store, like Amazon S3.

- A data warehouse may contain multiple databases. Within each database, data is organized into tables and columns. Within each column, you can define a description of the data, such as integer, data field, or string. Tables can be organized inside of schemas, which you can think of as folders

- A data warehouse is specially designed for data analytics, which involves reading large amounts of data to understand relationships and trends across the data. A database is used to capture and store data, such as recording details of a transaction.

- data lake is a centralized repository for all data, including structured, semi-structured, and unstructured. A data warehouse requires that the data be organized in a tabular format, which is where the schema comes into play. The tabular format is needed so that SQL can be used to query the data.

- A data mart is a data warehouse that serves the needs of a specific team or business unit, like finance, marketing, or sales. It is smaller, more focused, and may contain summaries of data that best serve its community of users.

## Oracle Data Warehouse

- A data warehouse is a type of data management system that is designed to enable and support business intelligence (BI) activities, especially analytics. Data warehouses are solely intended to perform queries and analysis and often contain large amounts of historical data. The data within a data warehouse is usually derived from a wide range of sources such as application log files and transaction applications.

- A data warehouse centralizes and consolidates large amounts of data from multiple sources. Its analytical capabilities allow organizations to derive valuable business insights from their data to improve decision-making. 

- A typical data warehouse often includes the following elements:

A relational database to store and manage data
An extraction, loading, and transformation (ELT) solution for preparing the data for analysis
Statistical analysis, reporting, and data mining capabilities
Client analysis tools for visualizing and presenting data to business users
Other, more sophisticated analytical applications that generate actionable information by applying data science and artificial intelligence (AI) algorithms, or graph and spatial features that enable more kinds of analysis of data at scale

- Four unique characteristics (described by computer scientist William Inmon, who is considered the father of the data warehouse) allow data warehouses to deliver this overarching benefit. According to this definition, data warehouses are

Subject-oriented. They can analyze data about a particular subject or functional area (such as sales).
Integrated. Data warehouses create consistency among different data types from disparate sources.
Nonvolatile. Once data is in a data warehouse, it’s stable and doesn’t change.
Time-variant. Data warehouse analysis looks at change over time.


- A well-designed data warehouse will perform queries very quickly, deliver high data throughput, and provide enough flexibility for end users to “slice and dice” or reduce the volume of data for closer examination to meet a variety of demands—whether at a high level or at a very fine, detailed level.

- When data warehouses first came onto the scene in the late 1980s, their purpose was to help data flow from operational systems into decision-support systems (DSSs). These early data warehouses required an enormous amount of redundancy.

- Data Warehouses, Data Marts, and Operation Data Stores
Though they perform similar roles, data warehouses are different from data marts and operation data stores (ODSs). A data mart performs the same functions as a data warehouse but within a much more limited scope—usually a single department or line of business. This makes data marts easier to establish than data warehouses. However, they tend to introduce inconsistency because it can be difficult to uniformly manage and control data across numerous data marts.

ODSs support only daily operations, so their view of historical data is very limited. Although they work very well as sources of current data and are often used as such by data warehouses, they do not support historically rich queries.


## McKinney, W. (2022). Python for Data Analysis (3rd ed.). O´Reilly Media.

