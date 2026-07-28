# IHG Meraki Design Parameters

## Hardware Models & PoE Loads

| Category | Item | Part Number | PoE Load | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Guest AP** | In-Room Guest Room AP | CW9172H | 10W | Use 20W if IP Phone attached |
| **Guest AP** | Shared Guest Room AP | CW9172H | 10W | 1 per 2 rooms (Drywall); Round up if floor room count is odd |
| **Common AP** | Lobby/Reception | CW9172I | 10W | |
| **Common AP** | Fitness Center | CW9172I | 10W | |
| **Common AP** | Meeting Room | CW9176I | 15W | 1 per meeting room |
| **Common AP** | Restaurant | CW9176I | 15W | |
| **Common AP** | Outdoor Patio/Pool | CW9163E | 10W | Use 4 x CW-ANT-O1-NS-00 |
| **Common AP** | Beach | CW9163E | 10W | 3 units; Use 4 x CW-ANT-O1-NS-00 per AP |
| **Common AP** | Other Outdoor | CW9163E | 10W | Use 2 x MA-ANT-20 per AP |
| **Mounting** | CW9172H Mount | MA-MNT-MR-H3 | - | Required for IPTV/Phone on CW9172H |
| **Mounting** | CW9163E Antenna (Standard) | CW-ANT-O1-NS-00 | - | 4 per AP for Patio, Pool, Beach |
| **Mounting** | CW9163E Antenna (Other) | MA-ANT-20 | - | 2 per AP |
| **Switch** | 48-Port PoE | MS150-48MP-4X | 740W | 85% Usable: 629W |
| **Switch** | 24-Port PoE | MS150-24MP-4X | 370W | 85% Usable: 314W |
| **Switch** | 8-Port DMZ Switch | MS130-8X | - | MDF Only |
| **SFP** | 1GB Multimode | MA-SFP-1GB-SX | 5W | |
| **SFP** | 1GB Singlemode | MA-SFP-1GB-LX10 | 5W | |
| **SFP** | 10GB Multimode | MA-SFP-10GB-SR | 5W | |
| **SFP** | 10GB Singlemode | MA-SFP-1GB-LR | 5W | Per official doc table (Note: likely MA-SFP-10GB-LR) |
| **Security** | Gateway (<100 rooms) | MX95 | - | |
| **Security** | Gateway (100-200 rooms) | MX105 | - | |
| **Security** | Gateway (>200 rooms) | MX250 | - | |

## Labor & Service SKUs

| Category | SKU / Item | Calculation Rule |
| :--- | :--- | :--- |
| **Labor** | 8-port Switch Installation | 1 per MS130-8X |
| **Labor** | 24-port Switch Installation | 1 per 24-port switch (MDF + IDF) |
| **Labor** | 48-port Switch Installation | 1 per 48-port switch (MDF + IDF) |
| **Labor** | AP Installation | 1 per AP (all models) |
| **Labor** | BBUPS Installation | 1 per UPS |
| **Labor** | Gateway Installation | 1 per Security Device in MDF |
| **Labor** | Bellinta NUC Installation | 1 per property |
| **Labor** | Heat Map / Final Site Survey | 1 per property |
| **Labor** | Labeling Cable and Network Equipment | 1 per property |
| **Labor** | Post survey tuning | 1 per property |
| **Labor** | NOC and Meraki Dashboard Setup | 1 per property |
| **Labor** | Post install documentation | 1 per property |
| **Labor** | Project Management | 1 per property |
| **Labor** | Training | 1 per property |
| **Expenses** | Shipping & Handling Expense | 1 per property |
| **Expenses** | Travel Expenses | 1 per property |
| **Services** | IHG GIA Guest Support Services | 1 per property |

## Infrastructure & Connectivity

| Item | Specification | Description for BOM |
| :--- | :--- | :--- |
| **Indoor Cable** | 200 ft per AP (Indoor CW9172I/CW9176I) | Indoor CAT6 Cable |
| **Outdoor Cable** | 200 ft per AP (Outdoor CW9163E) | Outdoor CAT6 Cable |
| **Patch Cable** | 6-inch (CW9172H/IPTV/Phone) | CAT6 Patch Cable 6in |
| **Patch Cable** | 1-foot | CAT6 Patch Cable 1ft |
| **Patch Cable** | 3-foot | CAT6 Patch Cable 3ft |
| **Patch Cable** | Fiber (3M) | LC-LC 3M Fiber Patch Cable |
| **Rack (MDF)** | 12U | 12U Rack |
| **Rack (IDF)** | 8U | 8U Rack |
| **UPS** | 1500VA | 1500VA UPS |
| **Patch Panel** | 24-Port | 24 Port Patch Panel (2 per MS150-48MP-4X, 1 per MS150-24MP-4X) |
| **Certification** | Cable Certification | 1 per installed AP (CW9172H, CW9172I, CW9176I, CW9163E) |

## Brand-Specific Logic Exceptions
- **IPTV Core Switch Scaling:**
  - **0–2 IDFs with fiber:** Use 1 × `C9300L-24T-4X-M`
  - **3–5 IDFs with fiber:** Use 1 × `C9300-24T-M` + 1 × `C9300-NM-8X-M`
  - **6–10 IDFs with fiber:** Use 1 × `C9300X-12Y-M` + 1 × `MA-CBL-TA-1M` (Direct Attach cable to MX)
- **HA Security:** If High Availability is requested, include 2 × Gateway units and required accessories.
