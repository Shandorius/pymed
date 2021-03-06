# My Fork of the [Original PyMed package](https://github.com/gijswobben/pymed)
This is my fork for the original PyMed package as it was no longer being maintained. I required MeSH terms and it has been modified from the initial module to do this.

#### What is added in this fork?
- MeSH Terms specified as "mesh"
- The ability to obtain the Trees beloging to MeSH terms as can be found in [MeSh Browser](https://meshb.nlm.nih.gov/search)
- References used in the article as described in the PubMed Database, specified as "references"

## Installation
This fork can be installed by running the following code in python:
``` 
pip install git+https://github.com/Shandorius/pymed#pymed
```
## Usage
The best usage for using this specific fork can be found in the "examples/recommended_way_of_search" folder as found on this page. It also shows all the available terms you can call for articles.

### Available terms for fetching articles (automatically includes all if you do not specify which ones you need as explained in the example):
- "pubmed_id"
- "title",
- "abstract",
- "keywords",
- "mesh",                     --> returns MeSH terms
- "mesh_id",                  --> returns MeSH id
- "mesh_full",                --> returns object with MeSH term, id and tree
- "mainTree",                 ---> returns a collection of the first 3 alphanumerics (no duplicates) related to the MeSh terms of the article example: ["C02", "M04", "T02"]
- "journal",
- "publication_date",
- "authors",
- "methods",
- "conclusions",
- "results",
- "copyrights",
- "references",
- "doi",
- "xml",

# PyMed - PubMed Access through Python
PyMed is a Python library that provides access to PubMed through the PubMed API.

## Why this library?
The PubMed API is not very well documented and querying it in a performant way is too complicated and time consuming for researchers. This wrapper provides access to the API in a consistent, readable and performant way.

## Features
This library takes care of the following for you:

- Querying the PubMed database (with the standard PubMed query language)
- Batching of requests for better performance
- Parsing and cleaning of the retrieved articles

## Examples
For full (working) examples have a look at the `examples/` folder in this repository. In essence you only need to import the `PubMed` class, instantiate it, and use it to query:

```python
from pymed import PubMed
pubmed = PubMed(tool="MyTool", email="my@email.address")
results = pubmed.query("Some query", max_results=500)
```

## Notes on the API
The original documentation of the PubMed API can be found here: [PubMed Central](https://www.ncbi.nlm.nih.gov/pmc/tools/developers/). PubMed Central kindly requests you to:

> - Do not make concurrent requests, even at off-peak times; and
> - Include two parameters that help to identify your service or application to our servers
>   * _tool_ should be the name of the application, as a string value with no internal spaces, and
>   * _email_ should be the e-mail address of the maintainer of the tool, and should be a valid e-mail address.

## Notice of Non-Affiliation and Disclaimer 
The author of this library is not affiliated, associated, authorized, endorsed by, or in any way officially connected with PubMed, or any of its subsidiaries or its affiliates. The official PubMed website can be found at https://www.ncbi.nlm.nih.gov/pubmed/.
