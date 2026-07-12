---
type: source
tags: [seo, aeo]
date_published: 2018-04-01
date_ingested: 2026-07-11
origin: raw/articles/entity-oriented-search-balog-2018-selective.md
---

# Entity-Oriented Search (Krisztian Balog, 2018)

**Citation:** Balog, K. (2018). Entity-Oriented Search. The Information Retrieval Series, Vol. 39, Springer Open. https://doi.org/10.1007/978-3-319-93935-3

**Scope:** Selective ingest of Chapters 1 (Introduction), 5 (Entity Linking), and 8 (Leveraging Entities in Document Retrieval). Chapters 3-4, 6-7 are theoretical algorithms outside SEO scope.

## Key takeaways

- **Entity definition**: An entity is uniquely identifiable by its name(s), type(s), attributes, and relationships to other entities. This is the structural unit modern search systems (including AI) use to organize information.
- **Knowledge representation hierarchy**: Entity catalog → Knowledge repository → Knowledge base (structured facts/triples). Wikipedia/Freebase/DBpedia are canonical examples.
- **Entity-oriented search (EOS) definition**: Organizing and accessing information centered around entities and their attributes/relationships (vs. document-based or keyword-based retrieval).
- **User benefit of EOS**: Richer, more effective user experience by allowing interaction with specific entities rather than generic document lists.
- **Machine benefit of EOS**: Better understanding of queries, documents, and user context/preferences → enabling more intelligent retrieval.
- **Entity linking pipeline**: Three stages — (1) mention detection (identify text spans referring to entities), (2) candidate selection (generate ranked candidate entities), (3) disambiguation (select correct entity based on context). Foundation for connecting unstructured text to structured knowledge bases.
- **Entity-based query expansion**: Map query to entities → extract expansion terms from entity descriptions (names, types, attributes, related entities) → re-weight and use for document ranking. Improves retrieval by capturing semantic relationships beyond keyword matching.
- **Latent entity space**: Projects queries and documents into entity-space where single dimension = one entity, enabling retrieval of documents about an entity even if they don't mention it by name.
- **Application areas**: Web search, e-commerce, question answering, domain-specific search, structured data retrieval — not limited to general web search.
- **Historical roots**: Converges four fields: Information Retrieval (entity retrieval task), Databases (entity-relationship model), NLP (named entity recognition), Semantic Web (RDF/URIs/ontologies for structured data).

## What this updates in the wiki

- Created new concept page [[entity-oriented-search-fundamentals]] covering the definition, properties, knowledge representation (catalogs/repositories/bases), entity linking pipeline, and the distinction between EOS vs. semantic search vs. traditional document retrieval.
- Cross-linked from [[generative-engine-optimization]] as foundational: modern AI search systems (Google's Knowledge Graph integration, AI Overviews) are built on entity-oriented retrieval — entities are how AI systems parse queries and retrieve relevant information.
- Cross-linked from [[how-google-search-works]] (indexing/retrieval stages) to emphasize that entity linking and entity-based ranking are parallel processes to traditional term-based ranking in modern search engines.
- New actionable section in [[geo-content-optimization-tactics]]: "Entity recognition and disambiguation in content" — guidance on ensuring entities in your content are unambiguously expressed so systems can correctly link mentions to knowledge bases.
- No conflicts — this is foundational IR theory underlying modern search and AI. Complements rather than contradicts existing wiki content.
