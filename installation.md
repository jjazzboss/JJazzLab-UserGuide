# Installation instructions

## Windows

Download and run the setup program at [https://www.jjazzlab.org/en/download](https://www.jjazzlab.org/en/download), which embeds everything you need.

{% hint style="warning" %}
If you get a **Windows Smart Screen** alert

<img src=".gitbook/assets/win10smartscreen.png" alt="" data-size="original">&#x20;

Windows Smart Screen blocks the program NOT because it is a malware (it is NOT!), but just because JJazzLab is new, so Windows security servers don't have enough statistics to evaluate its "security reputation".

Once enough users will have successfully downloaded and installed it, Windows Smart Screen will not block the program anymore.

You can find more explanations in this [good article](https://www.digitalcitizen.life/what-smartscreen-filter-how-does-it-work).
{% endhint %}

{% hint style="info" %}
If you don't have admin rights on your computer, choose **Install for me only** during setup
{% endhint %}

## MacOS

#### 1/ install [FluidSynth](https://github.com/FluidSynth/fluidsynth/wiki/Download) (>=2.2.0)

I **strongly** recommend via [Homebrew](https://brew.sh/): `brew install fluidsynth`

#### 2/ Download a JJazzLab package and install it

_Mac computers with Apple Mx processor_

Download the .pkg file at [https://www.jjazzlab.org/en/download](https://www.jjazzlab.org/en/download) and open it.



_Mac computers with Intel x64 processor_

.pkg files are not always supported on old MacOS versions, so we propose a .zip file, a basic solution but compatible with many MacOS versions.

* Download the .zip file and extract (open file with Finder)
* **Make sure** **that all extracted files** have **read** permission ('`r`'), and that `bin/jjazzlab` and `jdk/bin/java` have **execution** permission ('`x`'), as shown below:  ![](<.gitbook/assets/2024-01-03 11\_38\_13-Ubuntu22LTS \[Running] - Oracle VM VirtualBox.png>)\
  To add read+execution permission: `chmod a+rx bin/jjazzlab jdk/bin/java`
* Execute file `bin/jjazzlab` to start JJazzLab.

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

Download the relevant package for your distro  at [https://www.jjazzlab.org/en/download](https://www.jjazzlab.org/en/download), then open it with the relevant package manager (examples below) :

```bash
sudo apt-get install ./jjazzlab_4.0.2-1_amd64.deb
```

```sh
sudo gdebi install ./jjazzlab-4.0.2-0.x86_64.deb
```

```bash
sudo zypper install ./jjazzlab-4.0.2-0.x86_64.rpm
```

{% hint style="success" %}
JJazzLab packages declare a dependency on the FluidSynth (**>=2.2.0**) package. So the package manager should automatically install it if it's not already present on your system.
{% endhint %}

#### Using the tar.xz package&#x20;

The `.tar.xz` package should work on any Linux distro (x64).

1. &#x20;Install FluidSynth (**>=2.2.0**) manually: [https://github.com/FluidSynth/fluidsynth/wiki/Download](https://github.com/FluidSynth/fluidsynth/wiki/Download)
2. Download and extract the JJazzLab .tar.xz file, e.g\
   `tar -xf JJazzLab-4.0.2-linux-x64.tar.xz`
3. **Make sure** **that all extracted files** have **read permission** ('`r`'), and that `bin/jjazzlab` and `jdk/bin/java` have **execution permission** ('`x`'), as shown below:  ![](<.gitbook/assets/2024-01-03 11\_38\_13-Ubuntu22LTS \[Running] - Oracle VM VirtualBox.png>)\
   To add read+execution permissions: `chmod a+rx bin/jjazzlab jdk/bin/java`
4. Run`bin/jjazzlab`

#### Special case: `libfluidsynth.so.3` in a non-standard directory

On Linux, JJazzLab uses FluidSynth via its shared library `libfluidsynth.so.3` (or `libfluidsynth.so`). The file is expected to be in one of the standard directories:\
`/usr/lib/x86_64-linux-gnu, /usr/lib, /usr/lib64, /usr/local/lib, /lib`

If you successfully installed FluidSynth (**>=2.2.0**) but JJazzLab can't load FluidSynth, it's possible that `libfluidsynth.so.3` was installed in a non-standard directory. Once you found the file location (for example in `/tmp/lib/libfluidsynth.so.3`), you can tell JJazzLab where to find it:

* In the JJazzLab installation directory, edit file `etc/jjazzlab.con`f
* Add `-J-Dfluidsynthlib.path=/tmp/lib/libfluidsynth.so.3` at the end of the `default_options` variable
* Start JJazzLab

{% hint style="danger" %}
JJazzLab embeds its own Java Runtime Engine. You don't have to deal with Java at all. Trying to use a different JRE/JDK will certainly generate problems.
{% endhint %}
