# Network Design Readiness Criteria

This document outlines the required data points needed to perform a professional Wi-Fi network design and generate an accurate Bill of Materials (BOM) according to enterprise hospitality standards.

## 1. Physical Infrastructure & Floorplans
- **Floorplans**: High-resolution PDF or Image files for every floor. Must include a graphical scale or known dimension for calibration.
- **Room Count**: Exact number of guest rooms per floor.
- **Wall Materials**: Identification of wall types (e.g., sheetrock/drywall, concrete, brick, or mortar).
- **MDF/IDF Locations**: Clearly marked locations for the Main Distribution Frame and any Intermediate Distribution Frames.

## 2. Low-Voltage & Cabling
- **Existing Wired Drops**: Confirmation if hard-wired CAT6 data drops are currently present in guest rooms.
- **IPTV / IP Phones**: Confirmation if the design must support IPTV or IP Phones (affects PoE and port counts).
- **Fiber Uplinks**: Details on existing or planned fiber runs between MDF and IDFs (Multimode vs. Singlemode).

## 3. Scope of Work (SOW) Variables
- **Common Areas**: List of areas requiring coverage (Lobby, Fitness Center, Meeting Rooms, Restaurant, Pool, etc.).
- **Outdoor Coverage**: Requirements for patios or pool decks.
- **Mounting Preferences**: Behind-TV (In-room) vs. Ceiling/Wall (Hallway).

## 4. Hardware Ecosystem
- **Preferred Vendor**: Aruba, Omada, or Meraki.
- **Survey Data**: Availability of Hamina (.json) or Ekahau (.esx) project files if a physical survey was already performed.

## Decision Logic (Aruba Example)
- **In-Room Design**: Required if guest room walls are concrete/brick (1 AP per room) or if wired drops exist.
- **Hallway Design**: Used only if wired drops are absent AND walls are sheetrock (1 AP per 4 rooms).
- **PoE Buffering**: 15% buffer required on switch port calculations.
- **UPS Sizing**: 1500VA standard for MDF/IDF.
