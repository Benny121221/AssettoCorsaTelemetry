# Forkers Notes

This is abandonware to a legendary degree. At the time of writing it has had no commits for 6 years, apart from my own. Most of the functionality is in an undocumented DLL with no known source code (or known to me at least). Because the project is unlicensed reverse engineering is theoretically illegal. And the WPF app is 99% broken. All it does (correctly) is log CSVs.

Fortunately, those CSVs are rather useful, and while a few fields are broken, most work as expected. However, I was not able to concretely find the frequency of logs even with a decompiler. Experimentally the frequency seems to be once every 15 ms (66.667 Hz). I cannot ascertain whether this is consistent or dependent on system load. Unfortunately this means I must suggest that you log the start and end times of your session and divide by the number of rows. And this makes the unwarranted assumption that the logging interval is consistent enough for this to be useful.

Since the graphs are broken, I suggest you plot the CSVs in Excel or another graphing tool. If I may shamelessly plug my own graphing program, it is available here: https://github.com/Benny121221/WPlot. If you want a C# plotting library, I contribute to this one: https://github.com/swharden/ScottPlot. Or use one of your preference, whatever floats your boat.

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
