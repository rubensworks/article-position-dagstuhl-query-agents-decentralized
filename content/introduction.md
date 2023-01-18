## Extended Abstract
{:#introduction}

While the [Web was originally envisioned](cite:cites webproposal) as a decentralized information space,
it has evolved to a place where the majority of data is flowing towards isolated *data silos*.
Since these data silos are in the hands of large companies and organizations, this leads to issues related to privacy and vendor lock-in.

To counter these problems, decentralization initiatives such as [Solid](cite:cites solid) are gaining popularity,
which allows users to store any kind of data in their own personal data vault, which they fully control.
These data vaults are personal Knowledge Graphs that can be represented as collections of [Linked Data documents](cite:cites linkeddata)
and more expressive [query APIs](cite:cites ldf, smartkg, brtpf).

The presence of such data vaults results in a large-scale distribution of data,
where applications involving multiple individuals' data require accessing
thousands or even millions of APIs
across different data vaults on the Web.
These applications cannot effectively be built today
due to the lack of querying techniques that can hande the requirements of decentralized environments like Solid.

A promising paradigm to tackle this query problem is [*Link Traversal Query Processing (LTQP)*](cite:cites linktraversal),
which is based on the [*follow-your-nose* principle](cite:cites linkeddata) of Linked Data
where query execution is done over a continuously growing range of documents by autonomously following hyperlinks between documents.

In order to apply LTQP effectively to decentralized environments, several open challenges need to be tackled:

1. To enable clients to select APIs with the most suitable query capabilities, there is a need to **represent the capabilities of query APIs using self-descriptive hypermedia descriptions**. [Current approaches](cite:cites ldf, spec:sparqlsd) have limited expressivity.
2. To enable clients to select and discover APIs matching their query needs, there is a need to **describe the contents of the data exposed through query APIs via hypermedia**, which could be cardinality-based, shape-based, or approximate summaries. [Current approaches](cite:cites summaries) lack the discovery and privacy-preservation.
3. To enable efficient client-side query execution, there is a need for **algorithms that provide (adaptive) query planning and execution over the heterogeneity of query APIs** in terms of capabilities, contents, and client-side policies. [Current techniques](cite:cites linktraversal) suffer from query termination problems caused by unselective link following technique,s and inefficient query plans caused by static non-adapting query planning.