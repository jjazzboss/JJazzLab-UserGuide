# Preguntas Frecuentes

## Me gustaría ayudar a JJazzLab y me gustaría que siga siendo gratis, cómo puedo ayudar? <a href="#how-to-help" id="how-to-help"></a>

* [Puedes donar ](https://www.jjazzlab.com/en/donate/)para que JJazzLab siga siendo gratis
* Ayuda a traducir JJazzLab => [translate](contribute/translate-jjazzlab/)
* Contribuye para mejorar la documentación => [Contribute ](contribute/improve-doc.md)
* Dale me gusta a los videos de Youtube y suscríbete al canal => [YouTube channel](https://www.youtube.com/channel/UC0L3SwjY6bhTj6jsbOYzzAw)
* Graba un video tuyo tocando con JJazzLab: los videos serán colocados en el canal de JJazzLab de YouTube
* Haz correr la voz! Habla sobre el tema y agrega enlaces a **www.jjazzlab.com** en redes sociales, blogs, sitios de internet, etc.
* Si eres desarrollador => [contribute code](https://github.com/jjazzboss/JJazzLab-X/blob/master/CONTRIBUTING.md)

## Uso MacOS, No puedo encontrar el menú Herramienta&#x73;**/Opciones?**

En MacOS las **opciones** son accesadas a través del menú principal **JJazzLab/Preferencias**.

## Cómo cambio la tonalidad de una canción? <a href="#how-to-transpose-song" id="how-to-transpose-song"></a>

1. Selecciona todos los símbolos de los acordes (click derecho y luego elegir "seleccionar todos los acordes")
2. Luego utiliza la rueda del ratón o haz click con el botón derecho y elige **"Transponer"**



## How to force a clean re-installation?

You need to reset all JJazzLab user settings (uninstall/re-install is not enough).

The simple way: menu **Tools/Options/Advanced,** button **Reset all user settings**.

The hard way: find the location of your **Netbeans user dir** in menu **Help/About/System Information**, **\*\*exit JJazzLab, then delete the** Netbeans user dir\*\*.

## I don't have administration privileges on my Windows computer, can I install JJazzLab?

Yes. When first prompted by the JJazzLab installer, select "Install only for me", then select an installation directory where you have write access (in My Documents for example).

## How to make fonts bigger? <a href="#font-bigger" id="font-bigger"></a>

In the JJazzLab installation directory, edit the file **etc/jjazzlab.conf** and add **--fontsize 16** (16 or any other value, default is 11) in the **default\_options** variable, you should end up with something like this:

`default_options="--branding jjazzlab -J-Djjazzlab.version=2.2.0 -J-Dplugin.manager.check.new.plugins=true -J-Dplugin.manager.check.interval=EVERY_DAY --fontsize 16"`

Restart JJazzLab. All menus should look bigger now.

This won't solve everything though, as some editor fonts do not depend on this setting. But you can tweak some of them using menu **Tools/Options/Theme**. Check each item in the list and if there is a font defined, change it to make it bigger. The user settings are automatically saved, so you need to do this only once.

## Can I start JJazzLab with command line arguments?

You can pass one or more .sng file names on the command line, JJazzLab will open them upon start.

```
# Example on Win10 (x64)
"C:\Program Files\JJazzLab\bin\jjazzlab64.exe" "C:\my dir\MySong.sng" "D:\AnotherSong.sng"
```

## How to submit a bug? How to find the "log" file?

Send an [email ](https://www.jjazzlab.com/en/contact/)or, if you're a GitHub user, create an [issue](https://github.com/jjazzboss/JJazzLab-X/issues).

We need the following information in order to help you:

* Provide the content of the **log file**&#x20;
* Describe what does not work as expected
* Describe the sequence of actions that caused the issue

{% hint style="info" %}
A new **log file** is created upon each start of JJazzLab. It's important to get the right log file when the problem occured.
{% endhint %}

To get the log file content:

1. Right after the problem has occured, go to menu **Tools/Options/Advanced**
2. Click on **Show Log Window**
3. Copy & paste **the full content** of this window in your bug report

If for some reason the above does not work:

1. Go to menu **Help/About** and find the location of your **Netbeans user dir**.  For ex. on Windows `C:\Users\MyName\AppData\Roaming\jjazzlab\2.2` For ex. on Linux `/home/MyName/.jjazzlab/2.2`
2. Open an explorer, go to this directory then to the **var/log** subdirectory
3. The last log file is **messages.log**, the previous one is **messages.log.1**, the before previous is **messages.log.2**, etc.
4. Find the relevant log file and send it with your bug report

{% hint style="danger" %}
If you can't find the **Netbeans user dir**., make sure your explorer shows the hidden files (e.g. the AppData directory is usually hidden on Windows)
{% endhint %}
