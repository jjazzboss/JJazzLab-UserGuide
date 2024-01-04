# Installation instructions

## Windows

Download and run the setup program at [https://www.jjazzlab.com/en/download](https://www.jjazzlab.com/en/download), which embeds everything you need.

{% hint style="info" %}
If you don't have admin rights on your computer, choose **Install for me only** during setup
{% endhint %}

{% hint style="warning" %}
If you get a **Windows Smart Screen** alert

<img src=".gitbook/assets/win10smartscreen.png" alt="" data-size="original">&#x20;

Windows Smart Screen blocks the program NOT because it is a malware (it is NOT!), but just because JJazzLab is new, so Windows security servers don't have enough statistics to evaluate its "security reputation".

Once enough users will have successfully downloaded and installed it, Windows Smart Screen will not block the program anymore.

You can find more explanations in this [good article](https://www.digitalcitizen.life/what-smartscreen-filter-how-does-it-work).
{% endhint %}

## MacOS

You must first install FluidSynth manually (I strongly recommend via Homebrew): [https://github.com/FluidSynth/fluidsynth/wiki/Download](https://github.com/FluidSynth/fluidsynth/wiki/Download).&#x20;

Then download the appropriate package at [https://www.jjazzlab.com/en/download](https://www.jjazzlab.com/en/download) and open it.

{% hint style="warning" %}
If you get a **security alert**

Using the **Finder**, select the JJazzLab package, **ctrl-click menu**, **Open**, this will give you the choice to open the application in spite of the security alert.
{% endhint %}

## Linux

{% hint style="danger" %}
If FluidSynth makes some "crackling" noise, make sure your Linux is optimized for audio applications: [https://jackaudio.org/faq/linux\_rt\_config.html](https://jackaudio.org/faq/linux\_rt\_config.html)
{% endhint %}

#### Using packages

JJazzLab packages are only proposed in selected formats (.deb, .rpm, ...).&#x20;

Download the relevant package for your distro  at [https://www.jjazzlab.com/en/download](https://www.jjazzlab.com/en/download), then open it with your package manager (`apt`, `zypper`, ...).

{% hint style="info" %}
JJazzLab packages declare a dependency on the FluidSynth (>=2.1) package. So the package manager should automatically install it if it's not already present on your system.
{% endhint %}

#### Using zip package&#x20;

The .zip package should work on any Linux distro.

1. &#x20;Install FluidSynth (>=2.1) manually: [https://github.com/FluidSynth/fluidsynth/wiki/Download](https://github.com/FluidSynth/fluidsynth/wiki/Download)
2. Download and extract the JJazzLab .zip file\
   `unzip -X -d JJazzLab JJazzLab-4.0.2-linux-x64.zip`
3. Make sure that all extracted files have `read` file permissions for all users, and that `bin/jjazzlab` has execution permission for all users, as shown below:  ![](<.gitbook/assets/2024-01-03 11\_38\_13-Ubuntu22LTS \[Running] - Oracle VM VirtualBox.png>)
4. Run`bin/jjazzlab`

{% hint style="warning" %}
If FluidSynth is not available when you run JJazzLab, it means that JJazzLab was not able to locate the FluidSynth shared library on your system. Please report the problem.
{% endhint %}

{% hint style="danger" %}
JJazzLab embeds its own Java Runtime Engine. You don't have to deal with Java at all. Trying to use a different JRE/JDK will certainly generate problems.
{% endhint %}
