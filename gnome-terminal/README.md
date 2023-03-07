# one-monokai-gnome-terminal-color-theme
Monokai Everywhere color theme for GNOME Terminal

### How to apply theme:
Download 'gnome_terminal.dconf' file
1. Create a new profile in GNOME Terminal settings, rename it to e.g. 'default'. The name will be overwritten on import, you can then rename it again to what you want
   This step is not necessary if you already have created a profile that is not the default "unnamed" profile. Just note that the profile's settings will be overwritten.
2. Set the new profile as the default profile
3. run `dconf dump /org/gnome/terminal/legacy/profiles:/`, see that it returns output similar to this:

    ```
    dconf dump /org/gnome/terminal/legacy/profiles:/
    [/]
    list=['e27d087d-18c4-4b72-83be-c84103543515']
    default='e27d087d-18c4-4b72-83be-c84103543515'

    [:e27d087d-18c4-4b72-83be-c84103543515]
    visible-name='default'
    ```

4. Copy the UUID of the created profile (in the example it is :e27d087d-18c4-4b72-83be-c84103543515 )
5. Run `dconf load /org/gnome/terminal/legacy/profiles:/:e27d087d-18c4-4b72-83be-c84103543515/ < one-monokai.dconf`
   Replace the UUID with the one from your profile.
   This will import the settings from the file to the profile and also apply it as the current profile.
   <b>Note the trailing `/` after the UUID in the command</b>
6. Modify other settings as needed.