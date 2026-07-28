# Best Western Aruba Design Parameters

## Hardware Models & PoE Loads

| Category | Item | Part Number | PoE Load | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Guest AP** | In-Room Guest Room AP | R3V48A | 10W | Use 20W if IP Phone attached |
| **Guest AP** | Shared Guest Room AP | R3V48A | 10W | 1 per 2 rooms (Drywall) |
| **Guest AP** | Hallway AP | R2H29A | 10W | Use only if room drops missing |
| **Common AP** | Lobby/Reception | R2H29A | 10W | |
| **Common AP** | Fitness Center | R2H29A | 10W | |
| **Common AP** | Meeting Room | Q9H62A | 15W | 1 per meeting room |
| **Common AP** | Restaurant | R2H29A | 10W | |
| **Common AP** | Outdoor Patio/Pool | R4W44A | 15W | |
| **Mounting** | R3V48A Mount | R3V58A | - | 1 per AP |
| **Mounting** | R2H29A / Q9H62A Mount | R3J18A | - | 1 per AP |
| **Mounting** | R4W44A Mount | JW053A | - | 1 per AP |
| **Switch** | 48-Port PoE | JL675A | 740W | |
| **Switch** | 24-Port PoE | JL677A | 370W | |
| **Switch** | 8-Port (DMZ) | JL679A | - | MDF Only |
| **SFP** | 1GB Multimode | J4858D | 5W | |
| **SFP** | 1GB Singlemode | J4859D | 5W | |
| **Security** | Gateway | USEQ:000GATEWAY:RG-901h | - | |

## Labor & Service SKUs

| Category | SKU / Item | Calculation Rule |
| :--- | :--- | :--- |
| **Labor** | Heat Map | 1 per property |
| **Labor** | 003INSTALL | 1 per device |
| **Labor** | 005SETUP | 1 per property |
| **Labor** | GuestSupportServices-CNC | 1 per property |
| **Services** | WiFi-Helpdesk | 1 per property |
| **Services** | USSW:RG-RM-50 | 1 per room |

## Infrastructure & Connectivity

| Item | Specification | Description for BOM |
| :--- | :--- | :--- |
| **Indoor Cable** | 200 ft per AP | Indoor CAT6 Cable |
| **Outdoor Cable** | 200 ft per AP | Outdoor CAT6 Cable |
| **Patch Cable** | 6-inch | CAT6 Patch Cable 6in |
| **Patch Cable** | 1-foot | CAT6 Patch Cable 1ft |
| **Patch Cable** | 3-foot | CAT6 Patch Cable 3ft |
| **Patch Cable** | Fiber (3M) | Fiber Patch Cable LC-LC 3M |
| **Rack (MDF)** | 12U | 12U Wall Mount Rack |
| **Rack (IDF)** | 8U | 8U Wall Mount Rack |
| **UPS** | 1500VA | 1500VA Battery Backup |
| **Patch Panel** | 24-Port | 24-Port Patch Panel (2 per 48-port switch, 1 per 24-port) |

## Brand-Specific Logic Exceptions
- **Hallway Design:** If room drops are missing, use R2H29A in hallways (1 per 4 rooms for drywall, 1 per 1 room for concrete).
- **IPTV Core:** If IPTV is present, use Cisco C9300 series for core switching (C9300L-24T-4X-M for 0-2 IDFs).
