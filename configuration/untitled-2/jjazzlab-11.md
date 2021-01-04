# JJazzLab

## Song files and song mix files <a id="song-files-and-song-mix-files"></a>

When you save a song called _mySong_, JJazzLab actually saves 2 different files:

* **mySong.sng**: contains everything except the mix information
* **mySong.mix**: contains only the mix information, i.e. the configuration of the instruments used.

Why using 2 different files ?

Because the mix information is specific to your sound device. Integrating the mix data in the .sng file would make .sng files not portable between users, since users have different sound devices.

So when you open _mySong.sng_, JJazzLab also tries to open _mySong.mix_ in the same directory. If _mySong.mix_ does not exist then JJazzLab creates the mix using the default mix of the rhythm\(s\) used in _mySong.sng_ \(see below\).

## Default rhythm mix <a id="default-rhythm-mix"></a>

Each JJazzLab rhythm has a builtin default mix. This builtin default mix can only use GM instruments for maximum portability.

You can override the rhythm’s builtin mix by saving a default rhythm mix file:  Unlike the builtin mix, this rhythm mix can use any instruments.

By default this file is stored in the user rhythm directory set in the Rhythms Options/Preferences, but this can be changed in General Options/Preferences.

## Mix file lookup order <a id="mix-file-lookup-order"></a>

Combining the 2 paragraphs above, below is how JJazzLab looks for mix information when you load _myDir/mySong.sng_ and this songs uses the rhythm _16BeatRock_ :

1. use _myDir/mySong.mix_ if present
2. use _defaultRhythmMixDir/16BeatRock.mix_ if present
3. use _16BeatRock_ builtin default mix \(GM instruments only\)

Steps 2. and 3. are also used when you add a new rhythm in a song.

