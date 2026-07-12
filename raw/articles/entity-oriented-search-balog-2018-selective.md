# Entity-Oriented Search (Balog 2018) — Selective Extract

**Source:** Krisztian Balog. "Entity-Oriented Search." Springer Open, 2018.
**Type:** Academic textbook on information retrieval
**Chapters extracted:** 1 (Introduction), 5 (Entity Linking), 8 (Leveraging Entities in Document Retrieval)
**Accessed:** 2026-07-11

## Chapter 1: Introduction — Foundational Concepts

### What Is an Entity?

**Definition 1.1:** An entity is a uniquely identifiable object or thing, characterized by its name(s), type(s), attributes, and relationships to other entities.

### Entity Properties

- **Unique identifier**: One-to-one correspondence between entity ID and the object it represents (e.g., Wikipedia article IDs, Freebase IDs)
- **Name(s)**: Entities have one or more surface forms and aliases; humans easily resolve ambiguity from context
- **Type(s)**: Entities can be categorized into multiple entity types (e.g., PERSON, LOCATION, ORGANIZATION); serves as a semantic category/class
- **Attributes**: Characteristics/features of an entity (e.g., birth date, location, height for a person)
- **Relationships**: How entities are associated with each other (e.g., "Homer wrote the Odyssey", "Einstein was discovered by Albert Einstein")

### Knowledge Representation

**Definition 1.3:** A knowledge repository (KR) is a catalog of entities with entity type information, descriptions, and (optionally) properties of entities in semi-structured or structured format. Example: Wikipedia, DBpedia, Freebase, YAGO.

**Definition 1.4:** A knowledge base (KB) is a structured knowledge repository containing a set of facts (assertions/subject-predicate-object triples) about entities. Example: DBpedia knowledge base, Freebase.

The relationship: Entity catalog ⊂ Knowledge repository ⊂ Knowledge base. A KB always has KR properties, but the reverse is not true.

### Entity-Oriented Search: Definition & Significance

**Definition 1.5:** Entity-oriented search is the search paradigm of organizing and accessing information centered around entities, and their attributes and relationships.

**User perspective:** Entities are natural units for organizing information. Allowing users to interact with specific entities offers a richer and more effective user experience than traditional document-based retrieval.

**Machine perspective:** Entities allow for better understanding of search queries, documents, and users (context and preferences). Entities enable search engines to be more intelligent.

### Application Areas

Entity-oriented search is not limited to web search. Applications include:
- Web search (e.g., Google's Knowledge Graph, entity cards)
- E-commerce search
- Domain-specific search (medical, legal, academic)
- Question answering systems
- Structured data retrieval (databases, knowledge bases)

### Historical Evolution

Entity-oriented search has roots in four major research areas:
1. **Information Retrieval** (from 1960s onward): shifted from document retrieval to entity retrieval
2. **Databases** (entity-relationship model, 1976 onward): entities recognized as meaningful units for data organization
3. **Natural Language Processing** (especially named entity recognition)
4. **Semantic Web** (2001 onward): structured representation of entities and relationships using RDF, URIs, ontologies

The convergence of these fields has led to entity-oriented search as a coherent research area.

---

## Chapter 5: Entity Linking

### Definition & Task

**Definition 5.1:** Entity linking is the task of recognizing entity mentions in text and linking them to the corresponding entries in a knowledge repository.

Entity linking bridges unstructured text with structured knowledge bases by:
1. Detecting entity mentions in documents
2. Disambiguating which entity each mention refers to
3. Linking mentions to knowledge base entries

### Entity Linking Pipeline

The canonical entity linking approach consists of three components:

**1. Mention Detection**
- Identifies text spans (mentions) that potentially refer to entities
- Uses lexicon-based string matching or NLP techniques (named entity recognition)
- Must handle entity name variations, abbreviations, nicknames
- Example: "Einstein" → potential mention of Albert Einstein

**2. Candidate Selection**
- Generates a ranked list of candidate entities for each mention
- Uses the mention text to look up potential matches in knowledge base
- Maintains a set of candidate entities (typically top-k ranked)
- Must balance precision and recall

**3. Disambiguation**
- Selects the correct entity for each mention based on context
- Ranks candidates based on likelihood of being the correct referent
- Uses document context, entity properties, relationships
- Confidence score determines whether to accept or reject the linking

### Related Tasks

**Named Entity Recognition (NER):** Detecting entity mentions in text and classifying their types (PERSON, LOCATION, ORGANIZATION, etc.). Foundation for entity linking but focused on detection/classification, not disambiguation.

**Named Entity Disambiguation (NED):** Assigning entity identifiers to mentions (linking mentions to knowledge base). Also called "named entity resolution" or "named entity normalization."

**Entity Coreference Resolution:** Clustering entity mentions so that mentions referring to the same entity are grouped together, even without mapping to a knowledge base.

---

## Chapter 8: Leveraging Entities in Document Retrieval

### Three Approaches to Leverage Entities

**1. Expansion-based methods:** Utilize entities as a source to enrich query and/or document representations with additional terms, keeping original representations intact.

**2. Projection-based methods:** Treat entities as a latent layer between queries and documents.

**3. Entity-based methods:** Explicitly model entities recognized in documents and queries as first-class retrieval units, complementing traditional term-based representations.

### Mapping Queries to Entities (8.1)

Document retrieval requires identifying which entities a query refers to. Three methods:

- **Entities mentioned in the query**: Direct entity mentions (e.g., "Barack Obama" in "When was Barack Obama born?")
- **Entities retrieved from knowledge base**: Query a KB directly for relevant entities based on query terms
- **Entities from pseudo-relevant documents**: Extract entities from top-ranked documents retrieved with traditional IR, treating them as implicit query entities (pseudo-relevance feedback)

### Query Expansion Using Entities (8.2)

**Problem:** Keyword queries are typically too short to accurately express information needs.

**Solution:** Expand queries with semantically related terms from entity descriptions.

**Entity-centric query expansion approach:**
1. Map query to relevant entities (identify query entities)
2. Extract expansion terms from entity descriptions (names, types, attributes, related entities)
3. Re-weight terms based on their importance to the query entity
4. Use expanded query model for document ranking

**Term selection methods:**

*Unsupervised:*
- Term frequency: Frequency of term in entity description
- Term spread: How many different fields/sections the term appears in
- Term proximity: Distance between expansion term and original query terms in entity description
- Taxonomy-based: Similarity based on entity types

*Supervised:*
- Train classifier to identify good expansion terms
- Ground truth labels: expansion terms that improve retrieval effectiveness
- Features combine unsupervised signals above

### Entity-Based Document Ranking (8.3)

**Traditional IR limitation:** Documents without explicit mention of query terms have no retrieval score, even if they're about the query topic.

**Latent entity-based approach:** Project queries and documents into a latent entity space where:
- One dimension = one entity
- Query and document projections allow matching in higher-level concept space
- Discovers hidden semantic relationships

**Benefits:** Can retrieve documents about an entity even if they don't mention the entity by name, if they mention related entities or attributes.

---

## Key Insights for Search and Retrieval

1. **Entities are structural units:** Modern search engines organize information around entities, not just keywords or documents.

2. **Entity linking enables context understanding:** By recognizing and disambiguating entity mentions, systems can understand document content at a semantic level.

3. **Entity-based query expansion:** Expanding queries with entity-related terms improves retrieval for both traditional and semantic search.

4. **Knowledge bases are essential infrastructure:** Large-scale structured repositories (Wikipedia, Freebase, DBpedia, Google Knowledge Graph) enable entity-oriented search at scale.

5. **Multiple entity representations:** Entities can be represented as:
   - Semi-structured data (Wikipedia articles)
   - Structured data (RDF triples in knowledge bases)
   - Unstructured text (entity descriptions)
   - All are useful for different retrieval tasks

6. **Entity disambiguation is foundational:** Correctly resolving which entity a mention refers to is critical for all downstream entity-oriented retrieval tasks.
