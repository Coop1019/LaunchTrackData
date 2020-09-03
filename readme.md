# LaunchTrack Data
## Contribute to the LaunchTrack Database!

## Data format:
### Present/Future Launches:
	{
        "name": "Mission name",
        "rocketID": 0,
        "siteID": 0,
        "launchTime": 0,
        "genDate": "Plain text readable date if no exact date is known",
        "craft": "If there is a specific craft",
        "id": 49156,
        "description": "Description text goes here. Use \n for new lines",
        "recoveryStatus": "Enter recovery status here",
        "destination": "Destination (if any)",
        "patchURL": "https://cdn.launchtrack.app/images/patches/*path to patch image*",
        "crewed": "",
        "liveURL": "",
        "isLive": false,
        "orbit": "LEO"
    }
### Past Launches:
	{
        "name": "Mission Name",
        "rocketID": 0,
        "siteID": 0,
        "launchTime": 0,
        "craft": "",
        "id": 1599137173,
        "description": "Description goes here",
        "recoveryStatus": "Complete",
        "destination": "Of Course I Still Love You",
        "patchURL": "https://cdn.launchtrack.app/images/patches/sx_starlink.png",
        "crewed": "",
        "replayURL": "YouTube link",
        "outcome": 0,
        "orbit": "LEO"
    },

### Data Legend
- name: This is the name of the mission. Keep it short.
- rocketID: This is the corresponding ID for the rocket. With the current data set:
	- 0: Falcon 9
	- 1: Electron
	- 2: Atlas V
	- 3: Delta IV Heavy
	- 4: Falcon Heavy
- siteID: Launch site corresponding ID.
	- 0: LC-39A KSC, FL
	- 1: SLC-40 CC, FL
	- 2: LC-1A NZ
	- 3: SLC-41 CC, FL
	- 4: SLC-4E VAFB, CA
	- 5: LC-2 Wallops, VA
	- 6: SLC-37B CC, FL
	- 7: SLC-6 VAFB, CA
	- 8: LC-1B NZ
- launchTime: Unix integer time for liftoff
- genDate: (FUTURE LAUNCHES ONLY) Human readable string for current launch NET or range
- craft: String specifier for craft details. Leave empty if not relevant. With SpaceX, use booster number.flight as format (1060.2) and it will be properly parsed.
- id: This needs to be a unique integer number. Once set, leave it be in case anything gets tied to it. Typically, use a random long number.
- description: Description text for the launch. Don't go too long, but detail is good. Use \n for new lines and replace all double quotes (") in text with single quotes (') to avoid potential parsing issues
- recoveryStatus: String for status of recovery.
	- "Planned": If recovery is planned (i.e. SpaceX)
	- "Complete": if recovery is succesful
	- "🚫": If no recovery is planned (i.e. ULA)
	- "Failure": If landing fails
	- "In Development": If attempts are actively being made towards recovery (i.e. Rocket Lab)
- destination: Where the rocket is going to land (if recovered)
	- "Of Course I Still Love You"
	- "Just Read the Instructions"
	- "Landing Zone 1"
	- "Landing Zone 2"
	- "Landing Zone 4"
- patchURL: String URL for where the patch image is hosted. Must be 400x400px png image ON OUR SERVER. If you add to this git repo under the images/patches folder, the url will be of the format "https://cdn.launchtrack.app/images/patches/*path to patch image*"
- crewed: If mission is crewed, add string to say as such here. Use Emoji astronauts to signify the crew if possible.
- liveURL: (FUTURE LAUNCHES ONLY) String URL for YouTube link to live stream
- isLive: (FUTURE LAUNCHES ONLY) Boolean (true or false) for if said link above is currently live
- replayURL: (PAST LAUNCHES ONLY) String URL for YouTube mission replay link.
- outcome: (PAST LAUNCHES ONLY) Outcome of the Mission
	- 0: Mission Success
	- 1: Mission Failure
	- 2: Pending (Mission still in progress, example can be long duration crew missions)
	- 3: Partial Success/Failure (When its a bit iffy)
- orbit: 3 letter acronym for the orbit (can be longer if needed) (LEO, GTO, etc)
