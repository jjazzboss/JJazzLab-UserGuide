# Rhythm files

Each rhythm generation engine can have its own rhythm files. **poprock.sty** or **TripHop.S510.prs** are examples of rhythm files used by the [YamJJazz](https://www.jjazzlab.com/en/doc/yamjjazz) rhythm generation engine.

## Rhythm files location <a id="rhythm-files-location"></a>

JJazzLab expects rhythm files to be in the **User Directory for Rhythm Files**. This directory is defined in the **Options/Rhythms**. 

{% hint style="info" %}
You can use up to 2 levels of sub-directories to organize the rhythms. Sub-directories whose name starts with an underscore '\_' are not scanned.
{% endhint %}

![](../.gitbook/assets/userdirforrhythmfiles.png)

## Rhythm files scanning <a id="rhythm-files-scanning"></a>

Your rhythm/style files are scanned at startup only upon a fresh install, and the rhythm list is saved into a “cache” file.

This cache file is then used to get the rhythm list upon next startups, which is much faster than the initial scanning -especially if you have many rhythm files. 

{% hint style="info" %}
If you add or remove rhythm files you need to manually start a re-scan in order to update the cache file. This can be done in **Option/Rhythms** \(see image above\).
{% endhint %}

## Adding new rhythm files <a id="adding-new-rhythm-files"></a>

In order to avoid having too many files cluttering the **User Directory for Rhythm Files**, the recommended way is:

1. **Test the rhythm files**  
   In the rhythm selection dialog, use the **Add Rhythms** button to load additional rhythm files for the current session only. The files can be anywhere on your hard drive.  
  
    ![](../.gitbook/assets/addrhythmsbutton.png) 

  
   Standard Yamaha styles with extension .sty, .prs, .sst or .bcs should appear in the **YamJJazz standard styles**. Extended Yamaha styles \(.yjz\) should appear in the **YamJJazz extended styles**.   

2. **Copy the validated rhythm files** Once you have selected the “best” rhythm files, just copy them in the **User Directory for Rhythm Files** \(see above\).

**3. Force a Rescan from Options/Rhythms**

Quality of Yamaha style files found on the web may vary a lot. Furthermore some styles are sometimes “broken” \(invalid file format\). If there is an error the corresponding rhythm won’t show up in the rhythm selection dialog.

