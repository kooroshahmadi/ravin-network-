---
tags:
  - security/physical
  - environment
created: 2025-12-27
check: enriched
---

# Environmental Controls

Protecting against non-human threats (Fire, Heat, Water).

### 1. Fire Suppression
*   **Water Sprinklers:** Good for people, **bad for electronics**. (Water destroys servers).
*   **Special Hazard Systems (Clean Agents):** Use gases like **FM-200** or **Halon** (Legacy) to suck the oxygen out or chemically stop the fire without damaging the servers.

### 2. HVAC (Temperature & Humidity)
*   **Hot Aisle / Cold Aisle:** Arranging server racks so they face opposite directions.
    *   *Cold Aisle:* Where cool air enters the front of the servers.
    *   **Hot Aisle:** Where hot air exhausts from the back.
*   **Humidity:**
    *   *Too Low:* Static Electricity (ESD) kills chips.
    *   *Too High:* Condensation (Water) shorts circuits.

### 3. Power Management
*   **UPS (Uninterruptible Power Supply):** Battery backup for short outages (minutes). Used to shut down servers gracefully.
*   **Generator:** Diesel engine for long outages (days).