# Dan's ATC24 Clearance Generator V3 - Instructions (basic)
## Airport Setup
<b> Airport </b><br>
Before you begin adding clearances to the table, you must first setup the airport. Dan's ATC24 Clearance Generator V3 supports a total of 9 airports. In order for the software to properly detect what airport you are entering, you must enter the full ICAO as shown below: <br>
- IRFD / Greater Rockford
- IMLR / Mellor
- ILAR / Larnaca
- IPAP / Paphos
- IIAB / Mconnel AFB
- ITKO / Tokyo
- IPPH / Perth
- IGRV / Grindavik
- ISAU / Sauthemtona<br>
All of the SID data is taken from Aeronav Charts, so all 9 airports will be supported over at Aeronav: https://aeronav.space/app

<b> Departure Runway </b><br>
The departure runway must match the airport originally entered, for example you may not enter a departure runway of 08R at Rockford, as it does not exist. If an airport has multiple runways with similar identifiers (eg. runway 09R and 09L at Mconnel), you must specify one only.

<b> Standard Initial Climb </b><br><
The standard initial climb is the initial climb that will be given to all aircraft when generating a clearance, unless of course you override it using the custom entries (see complex guide for more info). The minimum value you can enter is at or above 1000ft, or at or below 5000ft. The ft units is <b> not </b> required, simply enter the number.

## Generating Clearances
<b> Callsign </b><br>
The callsign has no validation for the characters you can enter, though may I suggest you use ICAO codes to make the experience realistic, for example: EasyJet 123, would be given a callsign of EZY123, or radio callsign of Easy 123. If you are unaware of some other airline's ICAO codes, you can search it up.

<b> Aircraft Type </b><br>
Once again aircraft types aren't validated completely, though I will suggest once again that you use ICAO codes, for example an Airbus A340-600 has an ICAO of A346. And if you are unsure, you can search them up.

<b> Destination </b><br></b>
All airports in the PTFS map are supported, including the most remote ones (eg. IDCS), so no need to set a destination of an airport nearby. You must enter the ICAO code of the destination, and if you would like to enter a custom destination (see complex guide), then you must enter 'CUST' into the field. 
If you enter the same destination of the origin airport or if the destination airport is too close to the origin airport, the software may ask you to enter a custom departure (see complex guide), or to select the VECTOR/CUSTOM departure method if you have selected the SID method. This is due to the destination being too close to be given a SID, or if extremely close, a vector. 

<b> Departure Method </b><br>
We have 2 main departure methods that I have personally gathered and verified myself: SID or Vector. <b> If you are unfamiliar with what a Standard Instrument Departure (SID) is, may I suggest that you do so now, as using this software to its full potential will require you to have a wide range of knowledge. The SID and Vector is determined from the destination direction relative to the airport, for example the LOGAN4 departure heads North towards Perth and Tokyo, making it perfect SID's for destinations of those 2 airports. </b>
Determining which one to use, I would highly recommend that you ask the pilot requesting the clearance if they are able to fly a SID, as there are many new and unknowledgeable pilots on ATC24 that are unaware of what it is (quick tip, you can tell sometimes by how confident they speak on the radio, eg. if you hear pauses in transmissions "Easy 1..2..3, request.. uhh.. IFR clearance").
For more information on custom departures, see the complex guide.

<b> Squawk Code </b><br>
By default, squawk codes are randomly generated, though if you wish to enter a custom squawk, it must be valid for a squawk code, containing no numerical values above 7 and no longer than 4 characters long. This means that the highest squawk code you can get is 7777. 
The squawk will randomly be generated when you enter the following values: 'R', 'RND', or '' (meaning null, in case you accidentally enter the field. The same principal will apply when randomly generating a squawk code (will loop until value is correct).

## After Generation
<b> Pre Departure Clearance </b><br>
After clicking <i> EXECUTE AND ADD, </i> the software will automatically generate the clearance, add it to the table, then it will enter the clearance into a Pre Departure Clearance (PDC) template and copy it to your clipboard. If you entered any custom entries (see complex guide), then the PDC will be unavailable and instead you will be left with a message letting you know on the clipboard. You will then check 24Scope (may I recommend you use this website for your controlling, as it is extremely convenient in keeping track of aircraft) for the discord username of the aircraft, then find them in the VC to DM them the PDC.

<b> Moving to 24Scope </b><br>
After sending the PDC, the <i> COPY LAST VIA </i> and <i> COPY LAST SQUAWK </i> buttons allow you to copy the information over onto 24Scope quickly to keep your operations as structured and understandable as possible.

<b> Full Clearances Table </b><br>
If the clearances table reaches its maximum capacity (25), then the software will automatically clear it for you. After doing so it will result in a complete loss of all previous values, so make sure you've copied them over beforehand. 
If you would like to manually clear the table, you may do so.

<b> All Buttons <b/><br>
- <i> COPY LAST PCD </i> - Copies the last generated PDC to your clipboard
- <i> COPY PREV PDCS </i> - Allows you to copy any other previous PCDs (use the index values along the middle of the clearances table to do so)
- <i> COPY LAST VIA </i> - Allows you to copy the short form SID/Vector value to enter into 24Scope
- <i> COPY LAST SQUAWK </i> - Allows you to copy the squawk to enter into 24Scope
- <i> REMOVE ALL CLEARANCES </i> - Removes all PDCs and clearances. Does not reset the app.
- <i> QUICK GUIDE </i> - Reminds you of 2 hidden keys you may need when adding clearances.




