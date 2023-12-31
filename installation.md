# Installation

Download files are available at [https://www.jjazzlab.com/en/download](https://www.jjazzlab.com/en/download).

## Windows instructions

Download and run the setup program, which embeds everything you need.

{% hint style="info" %}
If you don't have admin. rights on your computer, choose **Install for me only** during setup
{% endhint %}

{% hint style="warning" %}
If you get a **Windows Smart Screen** alert

<img src=".gitbook/assets/win10smartscreen.png" alt="" data-size="original">&#x20;

Windows Smart Screen blocks the program NOT because it is a malware (it is NOT!), but just because JJazzLab is new, so Windows security servers don't have enough statistics to evaluate its "security reputation".

Once enough users will have successfully downloaded and installed it, Windows Smart Screen will not block the program anymore.

You can find more explanations in this [good article](https://www.digitalcitizen.life/what-smartscreen-filter-how-does-it-work).
{% endhint %}

## MacOS instructions

You must first install FluidSynth (I recommend via Homebrew): [https://github.com/FluidSynth/fluidsynth/wiki/Download](https://github.com/FluidSynth/fluidsynth/wiki/Download).&#x20;

Then download and open the appropriate package.

{% hint style="warning" %}
If you get a **security alert**

Using the **Finder**, select the JJazzLab package, **ctrl-click menu**, **Open**, this will give you the choice to open the application in spite of the security alert.
{% endhint %}

{% hint style="warning" %}
There is a known bug on MacOS: sometimes, after the computer wakes up from sleep mode, the audio can lag 2 or 3 seconds behind. This is due to a JDK problem, JJazzLab can't do anything.
{% endhint %}



## Linux instructions

Download and open the package for your Linux distro.&#x20;

All JJazzLab packages embed the JJazzLabSoundFont.sf2 and depend on FluidSynth (>=2.1). If you use the .zip package (which can not declare dependencies), you must first install yourselft FluidSynth: [https://github.com/FluidSynth/fluidsynth/wiki/Download](https://github.com/FluidSynth/fluidsynth/wiki/Download).

{% hint style="warning" %}
If FluidSynth makes some "crackling" noise, make sure your Linux is optimized for audio applications: [https://jackaudio.org/faq/linux\_rt\_config.html](https://jackaudio.org/faq/linux\_rt\_config.html)
{% endhint %}
