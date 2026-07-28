# Wyndham Aruba Design Parameters

## Hardware Models & PoE Loads

| Category | Item | Part Number | PoE Load | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Guest AP** | In-Room Guest Room AP | R3V48A | 10W | Use 20W if IP Phone attached |
| **Guest AP** | Shared Guest Room AP | R3V48A | 10W | 1 per 2 rooms (Drywall) |
| **Common AP** | Lobby/Reception | R2H29A | 10W | |
| **Common AP** | Fitness Center | R2H29A | 10W | |
| **Common AP** | Meeting Room | Q9H63A | 15W | 1 per meeting room |
| **Common AP** | Restaurant | R2H29A | 10W | |
| **Common AP** | Outdoor Patio/Pool | R4W44A | 10W | |
| **Mounting** | R3V48A Mount | R3V58A | - | 1 per AP |
| **Mounting** | R2H29A / Q9H63A Mount | R3J18A | - | 1 per AP |
| **Mounting** | R4W44A Mount | JW052A | - | 1 per AP |
| **Switch** | 48-Port PoE | R9Y03A | 740W | |
| **Switch** | 24-Port PoE | R8N87A | 370W | |
| **SFP** | 1GB Multimode | J4858D | 5W | |
| **Security** | Gateway | R1B20A | - | |
| **Licensing** | AP License | Q9Y60AAE | - | 1 per AP |
| **Licensing** | Switch License | Q9Y70AAE | - | 1 per Switch |
| **Licensing** | Gateway License | S0U83AAE | - | 1 per Gateway |

## Labor & Service SKUs

| Category | SKU / Item | Calculation Rule |
| :--- | :--- | :--- |
| **Labor** | Network Ethernet Infrastructure | 1 per property |
| **Labor** | Cabling - Common Area APs | 1 per Common Area AP |
| **Labor** | Heat Map / Survey | 1 per room count |
| **Labor** | 24-port Switch Install | 1 per 24-port switch |
| **Labor** | 48-port Switch Install | 1 per 48-port switch |
| **Labor** | AP Installation | 1 per AP |
| **Labor** | BBUPS Installation | 1 per UPS |
| **Labor** | Gateway Installation | 1 per Security Device |
| **Labor** | Project Management | 1 per room count |
| **Labor** | Documentation | 1 per room count |
| **Labor** | Training | 1 per room count |
| **Labor** | Post Survey Tuning | 1 per room count |
| **Services** | 24x7x365 WiFi Helpdesk | 1 per property |
| **Services** | NOC Setup Fee | 1 per property |

## Infrastructure & Connectivity

| Item | Specification | Description for BOM |
| :--- | :--- | :--- |
| **Indoor Cable** | 200 ft per AP | Indoor CAT6 Cable |
| **Outdoor Cable** | 200 ft per AP | Outdoor CAT6 Cable |
| **Patch Cable** | 6-inch | CAT6 Patch Cable 6in |
| **Patch Cable** | 1-foot | CAT6 Patch Cable 1ft |
| **Patch Cable** | 3-foot | CAT6 Patch Cable 3ft |
| **Rack (MDF)** | 12U | 12U Wall Mount Rack |
| **Rack (IDF)** | 8U | 8U Wall Mount Rack |
| **UPS** | 1500VA | 1500VA Battery Backup |
| **Patch Panel** | 24-Port | 24-Port Patch Panel (2 per 48-port switch, 1 per 24-port) |
| **Certification** | Cable Certification | 1 per AP |

## Brand-Specific Logic Exceptions
- **Labor Scaling:** Many labor items for Wyndham scale based on the total room count rather than a flat property fee.
- **Licensing:** Every hardware component requires a corresponding cloud license SKU.
