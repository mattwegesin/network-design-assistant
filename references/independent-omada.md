
## Guest Room Deployment Decision Logic
1. **Evaluate Existing Cabling First:** You MUST check if in-room data drops exist before selecting guest room APs.
2. **If NO existing drops (and walls are Drywall/Wood):** You MUST use a **Hallway Design**. Deploy 1 Hallway AP (EAP772) per 4 guest rooms in the corridors. Do not use Wall/In-Room APs (EAP775-Wall).
3. **If EXISTING drops are present:** 
   - Concrete/Brick Walls: Deploy 1 In-Room AP (EAP775-Wall) per room.
   - Drywall/Wood Walls: Deploy 1 In-Room AP (EAP775-Wall) shared between 2 rooms.
4. **Concrete/Brick without drops:** Require core drilling and new cabling; defaults to 1 In-Room AP (EAP775-Wall) per room.

# Independent Omada Design Parameters

## Hardware Models & PoE Loads

| Category | Item | Part Number | PoE Load | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **Guest AP** | In-Room Guest Room AP | EAP775-Wall | 25W | Wi-Fi 7 (Requires existing in-room data drops) |
| **Guest AP** | Shared Guest Room AP | EAP775-Wall | 25W | 1 per 2 rooms (Drywall AND existing drops present) |
| **Guest AP** | Hallway Guest Room AP | EAP772 | 25W | 1 per 4 rooms (Drywall/Wood AND NO existing drops) |
| **Common AP** | Lobby/Reception | EAP772 | 25W | Wi-Fi 7 |
| **Common AP** | Fitness Center | EAP772 | 25W | Wi-Fi 7 |
| **Common AP** | Meeting Room | EAP772 | 25W | 1 per meeting room |
| **Common AP** | Restaurant | EAP772 | 25W | Wi-Fi 7 |
| **Common AP** | Outdoor Patio/Pool | EAP772-Outdoor | 25W | Wi-Fi 7 |
| **Switch** | 24-Port Multi-Gig PoE | SG3428XPP-M2 | 770W | Default for Wi-Fi 7 |
| **Switch** | 48-Port PoE | TL-SG3452P | 384W | Legacy / Non-Wi-Fi 7 |
| **Switch** | 24-Port PoE | TL-SG3428MP | 384W | Legacy / Non-Wi-Fi 7 |
| **Controller** | Omada Hardware Controller | OC300 | - | |
| **Gateway** | Radical Networks Gateway | RNG-2500B | - | Default gateway |
| **SFP+** | 10GB Multimode | TL-SM5110-SR | 5W | |

## Labor & Service SKUs

| Category | SKU / Item | Calculation Rule |
| :--- | :--- | :--- |
| **Labor** | Heat Map | 1 per property |
| **Labor** | 003INSTALL | 1 per device |
| **Labor** | 005SETUP | 1 per property |
| **Labor** | GuestSupportServices-CNC | 1 per property |
| **Services** | WiFi-Helpdesk | 1 per property |

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
| **Patch Panel** | 24-Port | 24-Port Patch Panel |

## Brand-Specific Logic Exceptions
- **PoE Budget:** TP-Link Omada switches often have lower PoE budgets (e.g., 384W). The 85% rule is CRITICAL here to prevent over-subscription.
- **Wi-Fi 7 Power:** Wi-Fi 7 APs require higher PoE budget; ensure switch capacity is carefully validated.
