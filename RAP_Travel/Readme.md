```mermaid
flowchart BT
    DB[("ZTBUSINESS_TRAVEL\nDatabase Table")]

    subgraph CDS ["Step 2 · CDS Views"]
        ROOT["ZI_BUSINESS_TRAVEL\nInterface View"]
        PROJ["ZC_BUSINESS_TRAVEL\nProjection View"]
    end

    subgraph BDEF ["Step 3 · Behavior Definition"]
        BROOT["ZI_BUSINESS_TRAVEL\nBDEF Root"]
        BPROJ["ZC_BUSINESS_TRAVEL\nBDEF Projection"]
    end

    IMPL["ZBP_BUSINESS_TRAVEL\nBehavior Implementation"]

    subgraph SRV ["Step 5 · Service Layer"]
        SDEF["ZSD_BUSINESS_TRAVEL\nService Definition"]
        SBND["ZSB_BUSINESS_TRAVEL\nOData V4 Binding"]
    end

    DB --> ROOT & PROJ
    ROOT --> BROOT
    PROJ --> BPROJ
    BROOT & BPROJ --> IMPL
    IMPL --> SDEF --> SBND
```
--------------------

| Domain Name | Data Type | Length | Description |
| :--- | :--- | :--- | :--- |
| **ZTRAVEL_ID** | NUMC | 8 | Unique travel identification number |
| **ZTRAVEL_TITLE** | CHAR | 50 | Short title of the business trip |
| **ZTRAVEL_DESC** | CHAR | 200 | Detailed description of the travel purpose |
| **ZTRAVEL_NAME** | CHAR | 40 | Full name of the traveler |
| **ZTRAVEL_PLACE** | CHAR | 40 | Geographical location (Departure/Destination) |
| **ZTRAVEL_STATUS** | CHAR | 1 | Workflow status (O: Open, A: Accepted, R: Rejected) |

-------------------

