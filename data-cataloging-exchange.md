
# Data Cataloging and Exchange

How can we exchange datasets across different people, groups and settings, similar to how books are managed-within and across-libraries? This is typically what people have in mind these days when they say things like data catalogs, data lakes, data mesh and data space. In the past, organizations approached this problem by building or assembling a system, if they had the resources, or adopting one that estimated their pre-set data cataloging needs and workflows. We can call this the *pre-big data cataloging approach*: customized in-house system, pre-set data workflows, with some pre-set data exchange with external systems. However, in a time where change is the norm and connectivity is the first assumption, the rise and fall of data-workflows across new systems has become the modus operandi. So, what is the situation like today, and how might it look like tomorrow? I will discuss some ideas I've had around this problem. In what follows I will use the term 'data' to refer to datasets, be they structured or not, streaming or batch, etc.

Data is the new oil. However, unlike oil, data is not fungible. If it were, then this whole problem of data catagloging and exchange will not be a problem at all, just throw them in any container and take out more when you need it. Furthermore, data is not only differentiated *structurally* (storage technology, format, schema), but also in its content (naturally) and quality: not all data is created equal. That's why there is a rising trend of thinking about data *as an asset.* Furthermore, today the primary use-case is data moving across systems, teams, groups, and organizations.  

So, if each data asset is different, and assets are typically most valauble outside of the environments they where generated in, then how can we encode this uniqueness for others to understand, evaluate, and know how to use it. This lead me to the following abstraction: *metadata*.  Metadata is defined as the *structured information that describes, explains, locates, or otherwise makes it easier to retrieve, use, manage, and exchange a data asset*. So, each asset includes two parts: data and its metadata. This is a helpful abstraction although the distinction and boundary is not always straightforward. For example, to a data analyst, a JSON document containing the creation date and list of fields of a dataset is metadata, whereas to a person building a data catalog, the same JSON document is data. The disctintion is useful because it highlights the importance of a down-played barrier in streamlining data exchange and workflows: a lack of systematically documented metadata in practice (ex., metadata in someone's mind doesn't count). Furthermore, it opens up the discussion on what is metadata, and does it typically look like, how does it differ across applications and environments. 

So looking at data as an asset which is constituted of data and metadata, and the requirement of exchanging it across environments, what is the state of the art?

...Describe the state of the art


...Identify the gap


...Introduce the approach


...


In specific, a question that interests me has been: what standards and approaches 


1. National Information Standards Organization (NISO). Understanding Metadata. 2004. https://www.lter.uaf.edu/metadata_files/UnderstandingMetadata.pdf.






