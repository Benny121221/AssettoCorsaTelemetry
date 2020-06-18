# Forkers Notes

This is abandonware to a legendary degree. At the time of writing it has had no commits for 6 years, apart from my own. Most of the functionality is in an undocumented DLL with no known source code (or known to me at least). Because the project is unlicensed reverse engineering is theoretically illegal. And the WPF app is 99% broken. All it does (correctly) is log CSVs.

Fortunately, those CSVs are rather useful, and while a few fields are broken, most work as expected. However, I was not able to concretely find the frequency of logs even with a decompiler. Experimentally the frequency seems to be beween 15 and 20 ms, on my computer. I added a `UNIXTimestamp` column to help work around this inconsistency

Since the graphs are broken, I suggest you plot the CSVs in Excel or another graphing tool. If I may shamelessly plug my own graphing program, it is available here: https://github.com/Benny121221/WPlot. If you want a C# plotting library, I contribute to this one: https://github.com/swharden/ScottPlot. Or use one of your preference, whatever floats your boat.

Currently I am working on figuring out how the `AcSdk.dll` works. Check on my progress at `../decompiled/`

## Strange Quirks
- The column for gears assigns reverse to 0, neutral to 1, first gear to 2, etc.
- Velocity is a 3-D vector, but it is recorded in the form `<x>:<y>:<z>`, which means if you open it in Excel, velocity is a time
    - This formatting is true for most vector quantities
- Many columns do not work, reporting either nonsense or nothing
    - Some are even so bold as to report binaries
    - They may have worked in 2014 when this was last updated
        - If you want to try a 2014 copy of the game, you are welcome to let me know if this is the case
    - The "important" columns (throttle, brake, gear, steering angle and speed) all work fine
        - So do the suspension, and tyre columns
     - Velocity and acceleration appear to be fine
     - All status and timing-related columns are broken (with the exception of the `UNIXTimestamp` column
     - Position and sector data is broken

This app reads from Assetto Corsa's shared memory, and unfortunately the memory map is subject to change quite often. The most recent memory map I could find is this: https://assettocorsamods.net/threads/doc-shared-memory-reference.58/

The most recent Asseto Corsa Comeptizione memory map that I could find is available here, it may be useful: https://www.assettocorsa.net/forum/index.php?threads/acc-shared-memory-documentation.59965/

Below is the original readme:

AssettoCorsaTelemetry
=====================

A telemetry application to use with Assetto Corsa

The end goal is to create a solid telemetry application with the ability to post the data online for other to critique or learn from. There may eventually be a mobile version.

The data is currently saved in a .csv format in your documents folder if you wish to look at the raw data gathered. You can also send this file to friends to load into this application and look at.

Only 3 things have been added so far: an Rpm/Speed chart, minimap, and a friction circle.
![Alt text](http://i.imgur.com/X4Aua0j.png)

You can change it to only look at a certain lap at a time
![Alt text](http://i.imgur.com/0OBM98x.png)

You can even change to to look at a certain sector of a lap (or a certain sector of all the laps combined).
![Alt text](http://i.imgur.com/0divnsZ.png)

Todo:
1) Create a plot to show specific data, specified by the user
2) Server to host the data
