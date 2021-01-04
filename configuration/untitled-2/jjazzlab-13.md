# JJazzLab

Each rhythm generation engine can have its own rhythm files. _poprock.sty_ or _TripHop.S510.prs_ are examples of rhythm files used by the [YamJJazz](https://www.jjazzlab.com/en/doc/yamjjazz) rhythm generation engine.

## Rhythm files location <a id="rhythm-files-location"></a>

JJazzLab expects rhythm files to be in the _User Directory for Rhythm Files_.

This directory is defined in the Rhythm panel of the Options/Preferences. You can use up to 2 levels of subdirectories to organize the rhythms. Subdirectories whose name starts with a ‘\_’ are not scanned.

## Rhythm files scanning <a id="rhythm-files-scanning"></a>

Your rhythm/style files are scanned at startup only upon a fresh install, and the rhythm list is saved into a “cache” file.

This cache file is then used to get the rhythm list upon next startups, which is much faster than the initial scanning -especially if you have many rhythm files. If you add or remove rhythm files you need to manually start a rescan in order to update the cache file. This can be done in the Rhythms panels of the Options/Preferences \(see image above\).

## Adding new rhythm files <a id="adding-new-rhythm-files"></a>

In order to avoid having too many files cluttering the _User Directory for Rhythm Files_, the recommended way is:

_1. Test the rhythm files_

In the rhythm selection dialog, use the Add Rhythms button to load additional rhythm files for the current session only. The files can be anywhere on your hard drive.  
 

Standard Yamaha styles with extension _.sty_, _.prs_, _.sst_ or _.bcs_ should appear in the _YamJJazz standard styles_. YamJJazz Extended Yamaha styles with extension _.yjz_ should appear in the _YamJJazz standard styles_. If it does not appear, see troubleshooting below.

_2. Copy the validated rhythm files_

Once you have selected the “best” rhythm files, just copy them in the _User Directory for Rhythm Files_ \(see above\).

_3. Force a Rescan from the Rhythm panel of the Options/Preferences_

## Troubleshooting <a id="troubleshooting"></a>

Quality of Yamaha style files found on the web may vary a lot. Furthermore some styles are sometimes “broken” \(invalid file format\). If there is an error the corresponding rhythm won’t show up in the rhythm selection dialog.

You can consult the log file \(click on the Show Log Window button from the General panel in the Options/Preferences\) to have more details about the errors JJazzLab encoutered while reading the files.

