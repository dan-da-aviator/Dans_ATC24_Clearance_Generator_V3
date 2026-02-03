# Dan's ATC24 Clearance Generator V3 - Processes
## Introduction
Welcome to Dan's ATC24 Clearance Generator V3. There are 4 main processes within this software that make up it's structure:
- Gathering of SID/VECTOR data
- Using destinations to determine the departure
- Correcting data if custom entries have been entered
- Generating PCDs and storing for later use

## Initial Setup
When setting up the airport, the SID/VECTOR data is automatically gathered and stored for later use. Previously on version 1 & 2, the data would be gathered every time you add a clearance to the table, making the software unbelievably inefficient. This data has been gathered and validated by myself, so there is no doubt in my mind that any of this is incorrect.
You may think that there are just 2 sets of arrays used to store this, though there are actually 4, including the following data:
- Short form SID (eg. RFD6.LCK - RH 150 - decoding to Rockford 6 departure with the Larnaca transition, turning right heading 150 after departure)
- Long form SID (eg. RFD6 DEP - LCK TRANS - AFT DEP RWY 07R RIGHT HDG 150 - this time including the departure runway)
- Short form vector (eg. RH 150-  decoding to right heading 150 degrees)
- Long form vector (eg. TURN LEFT HDG 360)
The long form SID is used for the PDCs, and the short form is used in the clearances table as well as the text copied to your clipboard when you click the  <i> COPY LAST VIA </i> button. This is mainly to minimize the use of space and to keep it professional.
The short form vector on the other hand is the only used for the text you copy to your clipboard when clicking the button. And on the other hand the long form SID is used for the clearances table and PDCs.

The reason why the departure runway is always included in the SID is due to some departures requiring a heading after departure, and these need to include the context of 'AFT DEP' in them. To save myself the pain of adding the departure runway to the SIDs that don't need a departure runway added, I simply added it to them all.

If there is a same destination of the origin airport, the value will be set to "C", where it will be used later, and if the destination is too close to properly fly a SID, the it will be filled with "N/A", also being used later.

## Using Destinations To Determine Departure
If you look a the source code, you will be able to see that each airport has it's own number assigned to it from 0 to 19. From this I can easily call the number in the array based off the destination, the array of values against airports will always remain the same (eg. 0 will always equal IRFD). If a custom departure has been entered, it will be corrected before the software checks for the values "C" or "N/A" as mentioned earlier if the airport is too close for a SID, or is the same as the origin with no custom departure.

## Correcting For Custom Entries
From here on, the software will then apply any custom values that haven't already been applied.

## Pre Departure Clearances
The software will then generate a PDC, and depending on the departure method there will be 2 templates it drops it into. The first one is the Vector one, which doesn't include the departure runway in the long form vector data, meaning it will need to be added. Then the SID, which includes the departure runway, so no departure runway variable is needed. Additional data is also included, such as centre frequencies and chart links.

The PDC is then stored in an array of 0 to 24, which is kept track of by a counter that resets every time the table is cleared either automatically or manually. When you clear the table, believe it or not the PDCs are actually still there, you just don't have access to them.
