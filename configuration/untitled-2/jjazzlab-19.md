# JJazzLab

JJazzLab can import _.SG\*_ or _.MG\*_ song files.

Only the following Band-In-A-Box data are used to generate the corresponding JJazzLab song :

* **song structure**: chorus start, chorus end, number of chorus, tag after, tag start, tag end, 2 bar ending
* **chord symbols**: name, position \(including optional push settings\), rest/hold/shot settings
* **song settings**: allow push/rest in first/middle/last chorus.

The song import feature is **not** 100% reliable, but most of the files should be OK.

## Time signature limitation <a id="time-signature-limitation"></a>

By default the imported song will be in 4⁄4: for most files time signature changes are ignored.

