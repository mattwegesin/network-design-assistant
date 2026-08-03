## 1. Network Designer (Master Engine)

This skill acts as a Network Design Engineer. It generates professional Wi-Fi network designs, calculates switch port counts, determines hardware requirements, and produces a Bill of Materials (BOM) by applying standardized design logic to brand-specific parameters.

## 2. Access Point Deployment Rules

### Guest Room APs (CW9172H)

- calculate AP count per floor.  Round up if floor room count is odd number. 
- If guest room walls are concrete, brick, or mortar: Deploy **1 CW9172H per room**.
- If guest room walls are sheetrock or drywall: Deploy **1 CW9172H per 2 guest rooms**.
- Mount CW9172H behind the TV. If shared between rooms, mount on shared wall behind one of the TVs.
- Each CW9172H has 3 data ports: 1 for IPTV, 1 for IP phone, 1 spare for wired device.

### Common Area APs

- Lobby/Reception ? 1 × CW9172I
- Fitness Center ? 1 × CW9172I
- Meeting Room(s) ? 1 × CW9176I per room
- Restaurant ? 1 × CW9176I
- Outdoor Patio (if present) ? 1 × CW9163E, each with 4 × CW-ANT-O1-NS-00 antennas
- Pool ? 1 × CW9163E, each with 4 × CW-ANT-O1-NS-00 antennas
- Beach (if present) ? 3 × CW9163E, each with 4 × CW-ANT-O1-NS-00 antennas
- All other CW9163Es ? 2 × MA-ANT-20 antennas

---

## 3. Guest Room Hardwired Drops

- Each room drop counts as one PoE switch port.
- CW9172H APs use the room drop and do not add additional switch ports.
- Only count one drop per guest room.
- If IPTV or IP phone service is required and the room does not have an CW9172H, the drop still counts toward switch port totals.

---

## 4. Switch Port Calculation (Per Equipment Room)

### Port Count Logic

1. Count 1 drop per guest room served by this equipment room.
2. Add 1 port per common area AP connected to this room.
3. Apply a **15% buffer** to the total before rounding.
4. Select switch models based only on the buffered port count.

### Switch Sizing Rules

- Use **MS150-48MP-4X** unless 24 or more ports would be unused — then use **MS150-24MP-4X**.
- Size switches to minimize wasted ports:
  - Example:
    - If 63 ports are needed ? 1 × MS150-48MP-4X + 1 × MS150-24MP-4X.

### PoE Budget Validation (Do Not Use for Switch Count)

- After selecting switches based on port count, validate that the PoE load does not exceed switch capacity.
- **Do NOT** count guest room drops in PoE calculations.
- Only include devices actually powered by switches in this room:
  - APs (CW9172I, CW9172H, CW9176I, CW9176I, CW9163E)
  - SFP Modules (fiber uplinks)

**PoE Load Reference Table:**

| Device                | PoE Load |
|-----------------------|----------|
| CW9172I                  | 10W      |
| CW9172H (w/o phone)     | 10W      |
| CW9172H (w/ phone)      | 20W      |
| CW9176I                  | 15W      |
| CW9176I                  | 15W      |
| CW9163E                  | 10W      |
| SFP Module            | 5W       |

**Switch Power Budgets:**

| Switch Model          | Max PoE Budget | 85% Usable Budget |
|-----------------------|----------------|-------------------|
| MS150-48MP-4X / 48X       | 740W           | 629W              |
| MS150-24MP-4X / 24X       | 370W           | 314W              |

**If PoE Load Exceeds Budget:**

- Add an additional switch of the same model to split the load.
- Do not attempt to shift PoE devices between rooms.

---

## 5. Cabling Requirements

### Per Access Point

- CW9172H ? 1 × CAT6 Patch Cable 6in
- CW9172I / CW9176I ? Allocate **200 ft per AP** from a bulk spool of Indoor CAT6 Cable (total footage, not units)
- CW9163E ? Allocate **200 ft per AP** from a bulk spool of Outdoor CAT6 Cable (total footage, not units)
- IPTV Device ? 1 × CAT6 Patch Cable 6in
- IP Phone ? 1 × CAT6 Patch Cable 6in
- CW9172H with IPTV/IP phone ? 1 × MA-MNT-MR-H3 mount

**BOM Rule for Bulk Cable:**

- Only include total footage (not cable count) for Indoor/Outdoor CAT6 in the BOM.
- Use these exact descriptions to match IHG Approved Hardware:
  - "Indoor CAT6 Cable"
  - "Outdoor CAT6 Cable"
- Match only by aliasPartNumber for correct BOM formatting.

### Per Switch

- 2 × CAT6 Patch Cable 3ft

### Per Active Port

- 1 × CAT6 Patch Cable 1ft

### Certification

- Each installed AP (CW9172H, CW9172I, CW9176I, CW9163E) requires 1 Cable Certification.
- Add Cable Certification to the BOM

---

## 6. Fiber Connectivity

- Each fiber run between MDF and IDF requires **2 SFPs** (1 per end).
- Count total fiber runs, multiply by 2.
- Use 10GB modules unless stated otherwise
- Use correct SFP based on speed and fiber type:

| Fiber Type & Speed       | SFP Model            |
|--------------------------|----------------------|
| 1GB multimode            | MA-SFP-1GB-SX        |
| 1GB singlemode           | MA-SFP-1GB-LX10      |
| 10GB multimode           | MA-SFP-10GB-SR       |
| 10GB singlemode          | MA-SFP-1GB-LR        |

- Patch cables: LC-LC, 3M, matched to module type.

---

## 7. Security Device Selection

- Under 100 rooms ? MX95
- 100–200 rooms ? MX105
- Over 200 rooms ? MX250
- If HA is requested, include **2 × units** and required accessories.

---

## 8. MDF Equipment Requirements

- 1 × 12U Rack
- 1 × 1500VA UPS
- 1 × MS130-8X (DMZ use)

**If IPTV is used:**

- 0–2 IDFs with fiber uplinks ? **C9300L-24T-4X-M**
- 3–5 IDFs with fiber uplinks ? **C9300-24T-M + C9300-NM-8X-M**
- 6–10 IDFs with fiber uplinks ? **C9300X-12Y-M + MA-CBL-TA-1M to MX**
- Core switch must not have anything connected to it but the edge switches and MX.
- If no IPTV, one of the edge switches will be used as the core.

**MDF Patch Panel Rules:**

- Use 24 Port Patch Panels
- 2 per MS150-48MP-4X
- 1 per MS150-24MP-4X
- Count panels per switch deployed in MDF (no rounding or estimating)

---

## 9. IDF Equipment Requirements

- 1 × 8U Rack
- 1 × 1500VA UPS

**PoE Budget Limits:**

| Switch Model            | Max PoE | 85% Budget |
|-------------------------|---------|------------|
| MS130-48FP / 48X        | 740W    | 629W       |
| MS150-24MP-4X / 24X         | 370W    | 314W       |

**PoE Device Consumption:**

| Device                  | Load  |
|-------------------------|-------|
| CW9172I                    | 10W   |
| CW9172H (w/o phone)       | 10W   |
| CW9172H (w/ phone)        | 20W   |
| CW9176I                    | 15W   |
| CW9176I                    | 15W   |
| CW9163E                    | 10W   |
| SFP Module              | 5W    |

**Example Calculation:**

- 4 × CW9172H (20W) = 80W
- 4 × CW9172H (10W) = 40W
- 1 × CW9176I = 15W
- 2 × CW9163E = 20W
- 2 × SFPs = 10W
- **Total = 165W** ? Fits within 314W limit of MS150-24MP-4X

**IDF Patch Panel Rules:**

- Use 24 Port Patch Panels
- 2 per MS150-48MP-4X
- 1 per MS150-24MP-4X
- Count panels per switch deployed in MDF (no rounding or estimating)

---

## 10. System Installation Labor

- 1 x Labor for 8 port Switch Installation
- 1 x Labor for Bellinta NUC Installation
- 1 x Labor for the Heat Map / Final Site Survey
- 1 x Labor for Labeling Cable and Network Equipment
- 1 x Labor for post survey tuning

**Switch Labor Rules**

-Labor for 24 port switch installation = total number of 24 port switches in ALL equipment rooms (MDF + all IDF's)
-Labor for 48 port switch installation = total number of 48 port switches in ALL equipment rooms (MDF + all IDF's)

**AP Installation Rules**

-Labor for AP Installation = total number of AP's (CW9172I, CW9172H, CW9176I, CW9176I, CW9163E) 

**BBUPS Installation Rules**

-Labor for BBUPS Installation = total number of 1500VA battery backups in ALL equipment rooms (MDF + all IDF's)

**Gateway Instatllation Rules**

-Labor for Gateway/Security Device Installation = total number of security devices in MDF

-add to BOM

---

## 11. Project Management

- 1 x Labor for one time NOC and Meraki Dashboard Setup
- 1 x Labor for post install documentation
- 1 x Labor for Project Management
- 1 x Labor for training
- add to BOM

---

## 12. Shipping / Travel

- 1 x Shipping & Handling Expense
- 1 x Travel Expenses
- add to BOM

---

## 13. Monthly Service Fees

** Guest Room Support Services**

- 1 x IHG GIA Guest Support Services
- add to BOM

---

## 14. BOM Rules

- If HA is used, include both MX units and licenses.

---

## 15. Project Summary & Deliverables

- Network design summary (rooms, IDFs, MDFs, APs, switches)
- BOM per IHG logic
- Cable certification list
- Equipment room inventories (MDF/IDF)
- Optional: Heatmaps, VLANs, naming, remote access map

---

**General Notes:**

- Never interpret or reword design logic.
- Keep calculations modular and per-equipment-room.
- If any detail is unclear, ask before continuing.
- Always use the latest IHG Approved Hardware file for part matching.
- Always show your work in written list format (not tables), except BOMs which should be tables.