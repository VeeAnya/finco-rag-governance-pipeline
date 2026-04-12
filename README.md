FinCo UK AI Governance RAG Pipeline
Overview
An enterprise grade Retrieval Augmented Generation pipeline built for FinCo UK, a fictional 200 person financial services organisation. The system allows staff to query internal AI governance documentation using natural language and receive accurate, cited answers grounded in company policy rather than general model knowledge.
Built to demonstrate practical RAG architecture, responsible AI principles and enterprise document management capability.
The Business Problem
FinCo UK staff have no easy way to get answers to AI governance questions. Policy documents exist but are lengthy, complex, and rarely read. Staff ask the same questions repeatedly, get inconsistent answers, and the compliance team spends significant time on queries that a well designed system could handle automatically.
This RAG pipeline solves that problem by making governance knowledge instantly queryable in plain English, with every answer grounded in and cited from the actual policy documents.
Architecture
Documents stored in GitHub are ingested into a Pinecone vector database via an n8n ingestion workflow. Each document is chunked, embedded using OpenAI embeddings, and stored as searchable vectors. When a query is received, n8n converts it to a vector, retrieves the most relevant chunks from Pinecone, and passes them to Claude as context. Claude generates a grounded answer citing the source document and section. Every query and response is logged to Airtable for compliance auditing.
Enterprise Design Decisions
Source citation on every answer. Every response includes the document and section the answer was drawn from. This is non negotiable in a regulated financial services environment where staff need to know the basis for governance guidance.
Confidence handling built in. When a question cannot be answered from the available documents the system says so explicitly rather than hallucinating an answer. Staff are directed to contact the AI Governance Committee directly.
Query logging to Airtable. Every question asked and every answer given is logged with a timestamp. This creates an audit trail that surfaces knowledge gaps, informs policy updates, and demonstrates compliance to regulators.
Responsible AI principles embedded throughout. The system is designed to augment human judgement not replace it. All answers include a note that staff should verify guidance with the AI Ethics Lead for complex or sensitive situations.
Documents Ingested
FinCo UK Responsible AI Policy. Covers acceptable use, prohibited use cases, EU AI Act risk classification, and governance structure.
FinCo UK AI Adoption Strategy. Covers the 12 month adoption roadmap, stakeholder mapping, ADKAR baseline assessment, and communications strategy.
FinCo UK Staff Guide. Plain English guide explaining what AI means for staff, what is changing, and what is expected of them.
Tools Used
n8n — workflow automation and RAG pipeline orchestration
Pinecone — vector database for document storage and semantic search
OpenAI — text embedding model for converting documents and queries to vectors
Claude API — large language model for answer generation
Airtable — query and response logging for compliance auditing
GitHub — document version control and storage
Skills Demonstrated
RAG pipeline design and implementation. Vector database configuration and management. Enterprise document preparation and chunking strategy. Responsible AI governance applied to system design. Prompt engineering for grounded, cited responses. Compliance audit trail design. n8n workflow automation at intermediate level.
Screenshots
Coming soon.
