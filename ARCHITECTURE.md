```mermaid
graph TD
    subgraph User_Layer [User Interaction]
        A[User Query] --> B[Azure AI Foundry Interface]
    end

    subgraph Orchestration_Layer [Azure AI Foundry / Agent Logic]
        B --> C{Search Orchestrator}
        C --> D[System Prompt & Safety Logic]
    end

    subgraph Data_Layer [Knowledge Retrieval]
        C --> E[Azure AI Search Index]
        E --- F[(Internal IT Knowledge Base)]
        C -.-> G[Azure AI Web Search Tool]
    end

    subgraph Reasoning_Layer [LLM Processing]
        D --> H[GPT-4o Model]
        H --> I[Response Generation]
    end

    subgraph Output_Layer [Final Output]
        I --> J[Answer + Citations]
        I --> K[Safety Disclaimer]
    end

    %% Security Styling
    style B fill:#0078d4,color:#fff
    style F fill:#f2f2f2,stroke:#333
    style G fill:#fff,stroke-dasharray: 5 5
```
