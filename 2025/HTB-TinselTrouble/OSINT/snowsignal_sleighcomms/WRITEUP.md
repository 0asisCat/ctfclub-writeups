# SnowSignal - SleighComms
### Difficulty: easy

> "A Signal Operator at Tinselwick Signal Intercept Station has intercepted an emergency transmission from a civilian sleigh that went off-course during a snow squall on Christmas Eve. The pilot managed to send a distress beacon using encoded bell tones before their communication equipment failed. The operator must analyze the bell tone sequence, decode it using the station's reference manual, cross-reference the decoded patterns with the landmark database, and identify the correct location to dispatch the rescue team before time runs out. Flag Format: HTB{LOCATION_PREFIX} Example: HTB{STFR}"

## Step 1
Start and spawn the docker sandbox. 

We are then met with this terminal like web interface:

<img width="1870" height="996" alt="image" src="https://github.com/user-attachments/assets/15ef25b3-d0fa-47a0-af08-724ff40a4a18" />

We first access the `Mission Brief` and use the following steps as our main guide:
<img width="843" height="726" alt="image" src="https://github.com/user-attachments/assets/a0eab1c1-415e-47e5-8575-3230e7601f34" />
```
YOUR MISSION:
1. Analyze the intercepted tone sequence in SIGNAL PLAYER
2. Decode using the TONE DECODER REFERENCE MANUAL
3. Cross-reference decoded patterns with LANDMARK DATABASE
4. Identify the distress location to coordinate rescue
```
## Step 2
Let's open the `Signal Player`. You may play the sound and click the `Apply Filter` button for clearer sound.

For more straightforward and easier analysis, click the `Waveform`, and you'll see the following visual graph:

<img width="844" height="728" alt="image" src="https://github.com/user-attachments/assets/0cac37dd-08ff-49d4-abd5-164c1afaffd5" />

## Step 3
Open the `Decoder Manual`. This will be our main references in getting the flag:

<img width="784" height="843" alt="image" src="https://github.com/user-attachments/assets/1bc76b6a-4070-44af-b40a-68751e024ec0" />
<img width="777" height="788" alt="image" src="https://github.com/user-attachments/assets/d1534133-42c9-40cf-9ba4-b05f74763196" />

## Step 4
Checking the `Signal Player` again, we have the following number of dings:
> [1 DING] [2 DINGS] [1 DING] [3 DINGS] [2 DINGS]
> 
> RESULTS: ST + FR + ST + EV + FR = STFRSTEVFR = ?

## Step 5
To finally find the specific location, we will check the `Landmark Database`:
<img width="722" height="637" alt="image" src="https://github.com/user-attachments/assets/556cc9da-9c94-47ad-b01f-e14da9991ecf" />
<img width="722" height="595" alt="image" src="https://github.com/user-attachments/assets/492c8ae7-ab3b-4cc8-8147-230b8fda77e8" />

Out of all the landmarks, the one that is equivalent to our previous signal is `Starfrost Chapel Way`.

Flag: `HTB{STFRSTEVFR}`

