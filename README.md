# JJazzLab

{% hint style="danger" %}
**!! The spanish documentation is NOT uptodate with latest version JJazzLab 5 !!**
{% endhint %}

{% hint style="info" %}
¿Quieres agregar temas o mejorar la documentación? ¡Claro que puedes! 😀 Visita la [pagina de contribución](contribute/improve-doc.md) para la documentación.
{% endhint %}

## ¿Por donde empiezo?

Hecha un vistazo a este [video tutorial](video-tutorials.md#for-starters).

## ¿Qué es JJazzLab?

🎵 JJazzlab es una aplicación de escritorio que genera pistas automáticamente para cualquier canción, aunque se trate de canciones complejas. Es un amigo para la Jam con el cual te puedes divertir improvisando en casa, aprender cosas nuevas o simplemente practicar tu instrumento. Es una gran herramienta para profesores.

🎷 JJazzLab esta diseñado para poder crear pistas de audio que no sean aburridas, con variedad, acentos rítmicos y que sean dinámicas. Puedes empezar un solo tranquilamente y gradualmente ir creando la atmósfera que mas gustes!

💻 Gracias a la plataforma de base JJazzlab que es open source los desarrolladores pueden agregar nuevas características muy fácilmente y generar nuevas posibilidades para la aplicación.

## Características

### Pistas (backing tracks)

* Generación instantánea de pistas Midi con batería, percusiones, bajo, piano, guitarra, etc.
* Gran nivel de detalle para configurar las pistas: variaciones en el ritmo, intensidad, silencios en los instrumentos, variación del tempo, etc.
* Reproducir desde el inicio, desde un compás determinado o en bucle la selección deseada.
* Reproducir con transposición directa (interesante para el saxo por ejemplo).
* Cualquier estructura de canción: Intro, solo, 1ra coda, etc.
* Ajuste de tempo, transposición, silenciar instrumentos deseados.
* Soporte para pistas con distintos ritmos, con tempos distintos.
* Posibilidad de exportar a un archivo Midi, facilidad para convertir de Midi a MP3.
* Click configurable y pre conteo.

### Editor

* Posee distintos tipo de editores: editor de hoja de acordes, editor de estructura de canción, editor de acordes, consola de mezcla (mix), editor de notas de cada canción.
* Editor multi-archivo con ventanas flotantes o fijas
* Interfaz de usuario intuitiva con la posibilidad de deshacer/rehacer ilimitadamente y copiar y pegar entre canciones
* Inserción libre de acordes (cuantificados o no), posibilidad de definir acordes sincopados o anticipaciones
* Soporta todos los tipos de acordes de pop-rock y jazz, permite también acordes definidos por el usuario
* Permite editar la forma en que los acordes son reproducidos: la armonía que hay por detras, acentos, variacion en la armonia durante solos, sustitucion de acordes, ...
* Moldes (templates) de canciones personalizables
* Interfaz de usuario personalizable (colores y fuentes con temas)
* Posibilidad de imprimir la hoja de acordes y la estructura de la canción



### Ritmos

* Soporte de archivos de estilos Yamaha (formatos SFF1 & SFF2) y con ello acceso a miles de estilos gratis en la web!
* Cientos de ritmos por defecto con el instalador
* Soporte de archivos de estilo "YamJJazz Yamaha extendidos" para obtener mas variaciones en los ritmos
* Arquitectura abierta: Se pueden agregar nuevos motores de generación de ritmos con plugins

### Midi

* Conectate a cualquier motor de audio gracias a la tecnología Midi: SoundFont player (recomendado para la JJazzLab SoundFont), sintetizador interno de Java, sintetizador externo, VST host vía puerto Midi virtual como ‘LoopBe1’
* Compatible con instrumentos GM/GM2/XG/GS
* Compatible con cualquier instrumento Midi a través de archivos de instrumentos Cakewalk (.ins)
* Mapeo automático de batería/percusiones desde archivos Yamaha XG a archivos GM/GM2/GS.
* Fuentes de sonido JJazzlab optimizadas para una alta calidad de reproducción y selección automática de instrumentos
* Seteos listos para usar para VirtualMidiSynth (Windows) y FluidSynth (Linux)
* Posibilidad de definir mezclas por defecto para cada ritmo
* Posibilidad de definir instrumentos por defecto a ser utilizados

### Importación

* Hojas de acordes de Band-In-A-Box
* Hojas de acordes de musicXML
* Hojas de acordes de Impro-Visor

### Otros

* Notificaciones automáticas cuando hay nuevas versiones
* Basado en el framework de aplicaciones open-source de Netbeans
