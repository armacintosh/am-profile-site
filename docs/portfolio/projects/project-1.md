# Urban Education Explorer

**Live Demo**: [https://public-data-graph-rag.netlify.app/](https://public-data-graph-rag.netlify.app/)
2025-01-10

### The Challenge
The Urban Institute provides a massive repository of educational data, yet its complexity often hinders accessibility.

<div class="grid cards" markdown>

-   **Extensive Data**

    3,000+ variables and 40+ endpoints from 25+ sources (IPEDS, College Scorecard).

-   **Comprehensive Coverage**

    Admissions, student outcomes, faculty, finance, safety, tax records, zip code, SES, and family income.

</div>

The challenge is that it's hard for people to know how to find what they are looking for. Navigating thousands of obscure variable codes (e.g., `cc_basic_2021`) requires extensive manual lookup, making it difficult to extract actionable insights.

### Our Approach

??? approach "GraphRAG for Data Codes"
    Unlike standard AI chatbots that might hallucinate variable names, our system uses semantic vector search to map natural language queries directly to the authoritative variable codes in the database. When a user asks a question, the system retrieves the most relevant "codes" from the dataset documentation.

??? approach "Knowledge Graph Context"
    These codes are not just retrieved as text; they are understood as nodes in a knowledge graph. The system identifies relationships—such as which directory a variable belongs to (e.g., IPEDS), its format (percentage, currency), and its entity type. This allows the AI to construct accurate, data-grounded answers.

??? approach "Interactive Visualization"
    Beyond chat, we integrated a full feature suite including interactive **Leaflet maps** for geospatial analysis and rich data tables. Users can filter institutions by specific criteria and see the results instantly on a map, or switch to the "Applicants" view to analyze student demographics and application flows.

### Results & Impact
*   **Democratized Data Access**: Transformed a technical API documentation site into a conversational interface, allowing non-technical users to query the database using plain English.
*   **Accurate Code Retrieval**: The GraphRAG system successfully disambiguates between thousands of similar variable names, ensuring that the analysis is based on the correct underlying data fields.
*   **Unified Analysis Workflow**: users can move seamlessly from asking high-level questions in the Chat interface to deep-diving into specific schools in the Explorer view, with all complex data codes handled automatically in the background.

### Example Use
**Live Demo**: [https://public-data-graph-rag.netlify.app/](https://public-data-graph-rag.netlify.app/)

<div class="grid cards" markdown>

-   **Calculated Geomaps**

    ![Interactive Map View showing clustered educational institutions](./portfolio-project-1/map_view.png)

    *Fig 1: The Colleges view allows users to explore institutions geographically. It visualizes and displays school data across different education databases from IPEDS.*

-   **Contextual Analysis**

    ![Applicant Profile Analysis](./portfolio-project-1/applicant_profile.png)

    *Fig 2: Deep dive into applicant demographics and admission probability analysis. Provides relative performance based on national aggregated data sets.*

-   **Generative Chat**

    ![GraphRAG Chat Interface](./portfolio-project-1/chat_interface.png)

    *Fig 3: The Chat interface uses GraphRAG to map natural language queries to understand relevant data available in the Urban Education data sets.*

</div>

#### System Architecture


![System Architecture Diagram](./portfolio-project-1/system_architecture.png)


*Fig 4: The custom GraphRAG architecture combines serverless AI calls with client-side vector search for low-latency code retrieval.*


### Tech Stack
*   **Frontend**: React, TypeScript, Tailwind CSS
*   **AI & Logic**: Google Gemini (via Google Generative AI SDK), GraphRAG Architecture (Custom implementation with Vector Search + Knowledge Graph logic)
*   **Mapping**: Leaflet, React Leaflet
*   **Backend**: Netlify Functions (Serverless)
*   **Data Processing**: Client-side Vector Search (Cosine Similarity), Local JSON Data Stores