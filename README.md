# glibrary 2.0 

## Overview

gLibrary is a service that offers both access to existing data repositories and creation of new ones via a simple REST API.

A **repository** in the gLibrary lingo is a virtual container of one or more data **collection**. 

A **collection** provides access to a relational DB table or to a non-relational (NoSQL) DB collection. Currenly gLibrary supports MySQL, PostgreSQL, Oracle and MongoDB. 

Each repository can group together one of more collections, providing a virtual and uniform interface to data tables coming from different databases that could be potentially of different types (for example one collection provides access to a PostGreSQL table and another to a MongoDB collection). JSON is used as the input and output data format.

Once collections are imported or created from scratch, the gLibrary RESTA APIs can be used to retrieve, create, update and delete collection's records, that in gLibrary lingo are called **items**. Moreover a powerful filtering system is available to make queries on collections. All the criteria are specified using the query string of the API GET call. (ex `/v1/repos/fantasy_company/orders?filter[where][userId]=acaland&filter[where][orderQuantity][gt]=200&filter[where][limit]=100` will search for 100 orders issued by the user `acaland` with a quantity of 100)

Each item can have one or more *attachment*, that we call **replica**. Replicas can be stored on Grid Storage Elements (Disk Pool Manager) or Cloud Storage (OpenStack Swift is supported). 

**Relations** between two collections of the same repository can be created, if foreign keys are properly assigned. Currently we support one-to-many relations.

## API

You can find the documentation for the API [here](https://github.com/csgf/glibrary/blob/master/docs/glibrary2.md)




