# FrostFleet - RiverWatch
### Difficulty: medium

> "A Maritime Investigator at Tinselwick River Authority has received an automated distress alert from patrol vessel FROSTSTAR, which went dark during a Christmas Eve patrol along the Frostwick River. The vessel's AIS system transmitted one final ""ghost ping"" before all communications ceased. The investigator must analyze the AIS coordinates, calculate distances to all registered river docks using the Haversine formula, cross-reference Captain Wintergale's log entries for observational clues, and identify the exact dock where the vessel ran aground to dispatch the rescue team before the incoming storm makes the river impassable. Flag Format:HTB{DOCK_NAME_DOCK_ID} Example: HTB{HARBOR_POINT_D042}"

## Step 1
Start and spawn the docker sandbox. 

We are then met with the following system interface:
<img width="1873" height="995" alt="image" src="https://github.com/user-attachments/assets/64fa22a6-6838-445a-8e9a-29c55db9a7c1" />

## Step 2
Let's access the `Mission Dossier` and look at the objectives.
```
SITUATION OVERVIEW:

Patrol vessel FROSTSTAR has gone dark during routine Christmas Eve
patrol operations. Last radio contact was at 23:30 on December 24.
Vessel was investigating reports related to the ongoing Starshard
disappearances in Tinselwick.

At 23:47, our AIS system received a single "ghost ping" - an
automated distress beacon indicating the vessel has run aground
and has been stationary for 6+ hours.


VESSEL DETAILS:

Name: FROSTSTAR
Type: Patrol Vessel (18m)
Captain: Hollis Wintergale
Crew: 3 personnel
Last Known Position: Ghost ping at 42.3456°N, 71.0892°W

```
<img width="633" height="948" alt="image" src="https://github.com/user-attachments/assets/3b9c66e3-42fb-46da-b9a8-470112780a6e" />

```
YOUR MISSION:

Using the FrostFleet OS navigation tools, you must:

1. Analyze the AIS ghost ping coordinates
2. Cross-reference with dock registry database
3. Review Captain Wintergale's log entries for clues
4. Calculate distances to potential locations
5. Identify the EXACT dock where FROSTSTAR ran aground
```

## Step 3
Let's check the `AIS Plotter`:
<img width="1872" height="996" alt="image" src="https://github.com/user-attachments/assets/50bb2b4c-56ce-43e5-8182-6336fd54cd0e" />
<img width="1872" height="994" alt="image" src="https://github.com/user-attachments/assets/30f1cd20-22da-49f1-901e-3737c27fd6e4" />


## Step 4
Access the `Dock Registry` for cross-references:
<img width="902" height="599" alt="image" src="https://github.com/user-attachments/assets/e52fb4da-fdd7-4112-956b-8f4c6be09c88" />


## Step 5
I didn't use the `Distance Calculator`, `Captain's Logs`, and `River Map` to judge that the answer is **"Everlight Landing"**.

If we use the `Distance Calculator` out of all the dock location, the closest is **"Everlight Landing"**.
<img width="903" height="600" alt="image" src="https://github.com/user-attachments/assets/d85c3adf-15f1-473e-b308-d48a1c8e86d4" />

<img width="846" height="313" alt="image" src="https://github.com/user-attachments/assets/29332752-58fa-41f2-a1ae-c3435cbef084" />

Flag: `HTB{EVERLIGHT_LANDING_D004}`

