
# Data Base Design ✍️  
> Created at 3/30/2021

We will see how we carry out the design process of the project database, we'll use `MongoDB`, if you want to know the reasons, check out the [Why MongoDB?](#why-mongodb)


## Tools Used 

| Herramientas              | Version                 | Source  |
| -------------             |:-------------:          | :-----:|
| Mongo Shell               | _0.9_                   | [🔗](https://www.mongodb.com/try/download/shell)        |
| Mongo JavaScript Driver   | _3.6_                   | [🔗](https://docs.mongodb.com/drivers/node/current/)    |
| Mongo Atlas               | _?_                     | [🔗](https://www.mongodb.com/es/cloud/atlas/register)   |
| Mongo Compass             | _1.26_                  | [🔗](https://www.mongodb.com/try/download/compass)      |


## Criteria on Data Modeling 
A big dilemma in NoSQL DB is deciding whether our documents should be` Referenced / Normalized` or `Embedded / Denormalized`. To establish whether it is Normalized or not, we will use the following criteria.


1. **Relationship Type** How two datasets are related to each other
2. **Data Access Patterns**. How often data is read and written. Read /write ratio.
3. **Data Closeness** How *much* the data is related, how we want to query.

|                       | Embedded / Denormalized                                                               | Referenced / Normalized                                       |
| -------------         |:-------------                                                                         | :-----|
| Relationship Type ❤  | 1 : Few <br>  1 : Many                                                                | 1 : Many <br> 1 : Ton <br> Many : Many                               |
| Data Access Patterns  | Data is mostly **read** <br> Data does not change quickly <br> High read/write ratio  | Data is updated a lot <br> Low read/write ratio               |
| Data Closeness        | Datasets really belong together                                                       | We frequently need to query both <br> datasets on their own   |


## Phases 
| Phase                 | Target & Method                           |
| -------------         |:-------------                             |
| [Conceptual Design]() | Conceptual Data Model - UML               |
| **Logical Design**    | Key-Value , Document, ColumFamily , Graph |
| **Physical Design**   | Document - MongoDB                        |

### Conceptual Design 

#### Entities 
The entities are shown in a very general way below, click on each one to go a little deeper 🐤

1. **Admin.** Person who manages the properties, clients and promissory notes. In addition to controlling what is displayed on the page
2. **Property.** Property that is being offered. Many properties can be purchased by many clients. *This is a 1:Few Relationship*
3. **Customer.** Person who buys or sell one or many properties. Many Customers can buy/sell various properties. *This is a 1:Few relationship*
4. **Promissory.** Legal Document that is generated when a purchase is made **in payments**

![alt text](./images/db-entities.png "entities")

Bueno, hay que ser mas especificos, veamos el siguiente diagrama UML para tener una idea mas clara de lo que necesitamos. 

### Logical Design 

#### Property Entity



### Physical Design 

## Why MongoDB?
**We use MongoDB mainly for performance**, we think using Mongo for this project is ideal for the following reasons

* **Semi-structured data**. Being properties, the structure of each type can vary, so a dynamic scheme can be a good option.
* **Limited query patterns**. Property searches don't usually have as many variables, so the queries are straightforward.
* **Without complex queries**. As mentioned in the previous point, the queries for the properties are not complex, using a non-SQL database will help to increase the performance of the queries even more.
* **Agile development.** MongoDB is suitable for fast iterative development, and its presentation in JSON format allows the rest of the work team to cooperate.

For more information about why and when to use MongoDB, check out this 👉 [link](https://www.mongodb.com/why-use-mongodb)

# References 📚 
Up, C. (2020, 9 july). Data Modeling Concepts in MongoDB Tutorial. Medium. [🔗](https://medium.com/@mjthakur413/data-modeling-concepts-in-mongodb-tutorial-codez-up-3b218c5aeb72)

Shin, K. S., Hwang, C. H., & Jung, H. J. (2016). NoSQL database Design Using UML Conceptual Data Model Based on Peter Chen’s Framework.ripublication. [🔗](https://www.ripublication.com/ijaer17/ijaerv12n5_12.pdf )
