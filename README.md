# qb-policejob
Police Job for QB-Core Framework :police_officer:


## Installation
### Manual
- Download the script and put it in the `[qb]` directory.
- Go To qb-core/shared/job.lua and paste this

```
 ['bcso'] = {
        label = 'Blaine County Sheriff Dept',
        type = "leo",
        defaultDuty = false,
        offDutyPay = false,
        grades = {
            ['0'] = { name = 'Solo Cadet', payment = 2200 },
            ['1'] = { name = 'Deputy', payment = 2550 },
            ['2'] = { name = 'Senior Deputy', payment = 2975 },
            ['3'] = { name = 'Corporal', payment = 3300 },
            ['4'] = { name = 'Sergeant', payment = 3950 },
            ['5'] = { name = 'Major', payment = 4375 },
            ['6'] = { name = 'Captain', payment = 4900 },
            ['7'] = { name = 'Under Sheriff', payment = 5450, isboss = true },
            ['8'] = { name = 'Sheriff', isboss = true, bankAuth = true, payment = 6500 },
            },
    },
    ['sasp'] = {
        label = 'San Andreas State Police',
        type = "leo",
        defaultDuty = false,
        offDutyPay = false,
        grades = {
            ['0'] = { name = 'Cadet', payment = 1500 },
            ['1'] = { name = 'State Officer', payment = 4500 },
            ['2'] = { name = 'State Trooper', payment = 5000 },
            ['3'] = { name = 'Trooper Sergeant I', payment = 6000 },
            ['4'] = { name = 'Trooper Sergeant II', payment = 8000 },
            ['5'] = { name = 'Trooper Lieutenant', payment = 10000 },
            ['6'] = { name = 'Assistant Commissioner', payment = 12000, isboss = true },
            ['7'] = { name = 'Commissioner Of Police', payment = 15000, isboss = true },
            },
    },
    ['sapr'] = {
        label = 'San Andreas State Park Rangers',
        type = "leo",
        defaultDuty = false,
        offDutyPay = false,
        grades = {
            ['0'] = { name = 'Solo Cadet', payment = 200 },
            ['1'] = { name = 'Junior Ranger', payment = 250 },
            ['2'] = { name = 'Ranger', payment = 275 },
            ['3'] = { name = 'Senior Ranger', payment = 300 },
            ['4'] = { name = 'Sergeant', payment = 350 },
            ['5'] = { name = 'Lieutenant', payment = 375 },
            ['6'] = { name = 'Captain', payment = 400 },
            ['7'] = { name = 'Game Warden', payment = 450, isboss = true },
            },
    },
    ['lspd'] = {
        label = 'Los Santos Police Department',
        type = "leo",
        defaultDuty = false,
        offDutyPay = false,
        grades = {
            ['0'] = { name = 'Officer', payment = 800 },
            ['1'] = { name = 'Senior Officer', payment = 1200 },
            ['2'] = { name = 'Senior Lead Officer', payment = 1400 },
            ['3'] = { name = 'Corporal', payment = 1600 },
            ['4'] = { name = 'Sergeant', payment = 1800 },
            ['5'] = { name = 'Sergeant 2', payment = 2000 },
            ['6'] = { name = 'Lieutenant', payment = 2400 },
            ['7'] = { name = 'Captain', payment = 2800 },
            ['8'] = { name = 'Asst Chief', payment = 3000 },
            ['9'] = { name = 'LSPD Chief', payment = 3300 },
            },
    },
```

## Dependencies
- [qb-core](https://github.com/qbcore-framework/qb-core)
- [qb-bossmenu](https://github.com/qbcore-framework/qb-bossmenu)  (Deprecated) - For the boss menu
- [qb-management](https://github.com/qbcore-framework/qb-management) (Replaces qb-bossmenu) - For the boss/gang menu
- [qb-garages](https://github.com/qbcore-framework/qb-garages) - For the vehicle spawner
- [qb-clothing](https://github.com/qbcore-framework/qb-clothing) - For the locker room
- [qb-phone](https://github.com/qbcore-framework/qb-phone) - For the MEOS app and notifications etc.
- [qb-log](https://github.com/qbcore-framework/qb-logs) - (Deprecated) - For logging certain events
- [qb-smallresources](https://github.com/qbcore-framework/qb-smallresources) (Replaces qb-log) - qb-log was added to qb-smallresources
- [qb-menu](https://github.com/qbcore-framework/qb-menu) - For the vehicle menus
- [qb-input](https://github.com/qbcore-framework/qb-input) - For accessing evidence stashes

## Features
- Classical requirements like on duty/off duty, clothing, vehicle, stash etc.
- Citizen ID based armory (Whitelisted)
- Fingerprint test
- Evidence locker (stash)
- Whitelisted vehicles
- Speed radars across the map
- Stormram
- Impounding player vehicle (permanent / for an amount of money)
- Integrated jail system
- Bullet casings
- GSR
- Blood drop
- Evidence bag & Money bag
- Police radar
- Handcuff as an item (Can used via command too. Check Commands section.)
- Emergency services can see each other on map

### Commands
- /spikestrip - Places spike strip on ground.
- /pobject [pion/barier/schotten/tent/light/delete] - Places or deletes an object on/from ground.
- /cuff - Cuffs/Uncuffs nearby player
- /escort - Escorts nearby plyer.
- /callsign [text] - Sets the player a callsign on database.
- /clearcasings - Clears nearby bullet casings.
- /jail [id] [time] - Sends a player to the jail.
- /unjail [id] - Takes the player out of jail.
- /clearblood - Clears nearby blood drops.
- /seizecash - Seizes nearby player's cash. (Puts in money bag)
- /sc - Puts soft cuff on nearby player.
- /cam [cam] - Shows the selected security cam display.
- /flagplate [plate] [reason] - Flags the vehicle.
- /unflagplate [plate] - Removes the flag of a vehicle.
- /plateinfo [plate] - Displays if a vehicle is marked or not.
- /depot [price] - Depots nearby vehicle. Player can take it after paying the cost.
- /impound - Impounds nearby vehicle permanently.
- /paytow [id] - Makes payment to the tow driver.
- /paylawyer [id] - Makes payment to the lawyer.
- /radar - Toggles the police radar.
- /911 [message] - Sends a report to emergency services.
- /911r [id] - Used to respond the emergency alerts.
- /911a [message] - Sends an anonymous report to emergency services (gives no location).
- /anklet - Places anklet (tracking device) on nearby player.
- /removeanklet [citizenid] - Removes the anklet from player.
- /ebutton - Used to respond an emergency alert.
- /takedrivinglicense - Takes the driving license from nearby player.
- /takedna [id] - Takes a DNA sample from the player.

## Credits
!Original script (https://github.com/qbcore-framework/qb-policejob)


