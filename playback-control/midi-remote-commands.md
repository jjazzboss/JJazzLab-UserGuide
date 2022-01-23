# Midi remote commands

If you have a Midi controller connected to your computer, you can use it to control JJazzLab playback.

For example you can start/pause the playback, or skip to the next song part, just by pressing a note on your piano keyboard.

Remote control via Midi IN is configured from the **Midi** panel of the **Options/Preferences**, as shown abobe.

By default each command is configured to be triggered by a specific incoming note. For example receiving a C1 note (Midi pitch=24) will trigger the play/pause command.

To configure a command with another note or with different incoming Midi messages, select the command and use **Midi Learn**.

Press the **Midi learn** button to put JJazzLab in a listening mode during a few seconds. Use this time to send the Midi messages which should trigger the command. For example, if you have a Midi keyboard and want to change the note, just press the note. If you have a Midi controller with pads, just activate the pad you want to use.

JJazzLab will display the Midi messages received which are now associated to the selected command. If Midi messages correspond to a single note, the note is displayed.
