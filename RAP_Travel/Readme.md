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
Data Element |  Domain | Label (Short) | Label (Medium) | Label (Long) |
| :--- | :--- | :--- | :--- | :--- |
| **Z88TRAVEL_ID** | Z88TRAVEL_ID | Travel ID | Travel ID | Travel Number |
| **Z88TRAVEL_TITLE** | Z88TRAVEL_TITLE | Title | Travel Title | Travel Title |
| **Z88TRAVEL_DESC** | Z88TRAVEL_DESC | Description | Description | Travel Description |
| **Z88TRAVEL_NAME** | Z88TRAVEL_NAME | Traveler | Traveler Name | Traveler Name |
| **Z88TRAVEL_PLACE** | Z88TRAVEL_PLACE | Place | Place | Departure Place |
| **Z88TRAVEL_STATUS** | Z88TRAVEL_STATUS | Status | Status | Travel Status |
