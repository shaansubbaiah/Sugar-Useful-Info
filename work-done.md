<h1 align="center">Debian Advocacy for Sugar</h1>


<div align="center">
    Google Summer of Code 2020
    <span> | </span>
    Sugar Labs
</div>
<div align="center">
    <a href="https://github.com/shaansubbaiah">
        <strong>Shaan Subbaiah B C</strong>
    </a>
</div>


<div align="center">
    <h4>
        <a href="">
            About
        </a>
        <span> | </span>
        <a href="">
            Issues Reported
        </a>
        <span> | </span>
        <a href="">
            Pull Requests
        </a>
        <span> | </span>
        <a href="">
            Work Pending
        </a>
    </h4>
</div>


## About

The project revolves around the packaging, testing and debugging of Debian(Experimental, Release, Stable versions) with Sugar and its dependencies, checking the functioning of the core features of the application, online collaboration, saveand resume features

The official project idea can be found in [sugarlabs/GSoC](https://github.com/sugarlabs/GSoC/blob/master/Ideas-2020.md#debian-advocacy-for-sugar)


## Issues reported

`05-Jun` - Sugar - DBus NoReply Error [Sugar-devel](http://lists.sugarlabs.org/archive/sugar-devel/2020-June/058403.html)

&emsp; &emsp; &emsp;└ Write - Activity crashing on resizing and moving tables.

&emsp; &emsp; &emsp;└ Browse - Activity doesn't open due to missing dependencies.


`06-Jun` - Sugar - Sugar 0.117-3 on Debian - AttributeError: 'str' object has no attribute 'decode' [#923](https://github.com/sugarlabs/sugar/issues/923)


`12-Jun` - Write - Default font is different for guest on joining collaboration session. [#43](https://github.com/sugarlabs/write-activity/issues/43)


`13-Jun` - Write - Error on closing Write Activity [#42](https://github.com/sugarlabs/write-activity/issues/42)


`16-Jun` - Write - Crashes while trying to resize table cells vertically [#41](https://github.com/sugarlabs/write-activity/issues/41)


`19-Jun` - [Sugar-devel](http://lists.sugarlabs.org/archive/sugar-devel/2020-June/058458.html)

&emsp; &emsp; &emsp;└ Browse - Collaboration doesn't work.

&emsp; &emsp; &emsp;└ Pippy - Dark mode is not applied to Pippy tabs created after Dark Mode is enabled.

&emsp; &emsp; &emsp;└ Read - Collaboration doesn't work; Sometimes  last 2 characters in a txt file are missing.

&emsp; &emsp; &emsp;└ Terminal - Warning in Activity log. Traceback in Sugar.

&emsp; &emsp; &emsp;└ Write - Sometimes, TTS ends halfway through the last word.


`30-Jun` - Read - When highlighting text, a wrong logging level was used. [[Sugar-devel]](http://lists.sugarlabs.org/archive/sugar-devel/2020-June/058501.html)


`30-Jun` - Calculate - Warning when attempting to calculate an expression; Error when using 'pi' and 'e' in expression; Hovering over Algebraic, Trigonometric toolbar buttons throws errors; Submitting trigonometric functions without values displays an error in the Activity but only the first character is highlighted red instead of the full function; Submitting logical expressions without values throws errors; Submitting / pressing '=' without entering any value throws errors. [[Sugar-devel]](http://lists.sugarlabs.org/archive/sugar-devel/2020-June/058501.html)


`04-Jul` - [Sugar-devel](http://lists.sugarlabs.org/archive/sugar-devel/2020-July/058522.html)

&emsp; &emsp; &emsp;└ Browse - HTTPError not handled while trying to copy an image [#112](https://github.com/sugarlabs/browse-activity/issues/112)

&emsp; &emsp; &emsp;└ Chat - Prevent user from sending smileys when disconnected [#30](https://github.com/sugarlabs/chat/issues/30)

&emsp; &emsp; &emsp;└ Jukebox - Errors when navigating above and below the first and last songs respectively [#30](https://github.com/sugarlabs/jukebox-activity/issues/30)

&emsp; &emsp; &emsp;└ Write - Multiple issues due to AbiWord causing Segmentation Faults.


`10-Jul` - Memorize - Editing the game doesn’t work, the activity gets stuck [#29](https://github.com/sugarlabs/memorize-activity/issues/29)


`16-Jul` - [Sugar-devel](http://lists.sugarlabs.org/archive/sugar-devel/2020-July/058546.html)

&emsp; &emsp; &emsp;└ Calculate - Typing random text instead of digits/variables throws an error. [#67](https://github.com/sugarlabs/calculate-activity/issues/67)

&emsp; &emsp; &emsp;└ Browse - Collapsing the Bookmarks bar lags/ causes multiple refreshes. Unconfirmed.

&emsp; &emsp; &emsp;└ Memorize - Activity saves its state to the Datastore but does not load it properly, a fresh instance is started. Therefore, the user is unable to save their progress and continue later; On hovering over ‘grid size’ buttons, a warning is displayed; The activity’s sounds and images (which are optional) depend on art4apps (http://wiki.sugarlabs.org/go/Art4Apps), which is not installed by default.

&emsp; &emsp; &emsp;└ EToys - Error window upon launching, menu frozen on Debian Bullseye.


`10-Aug` - Terminal - Report unused function [Github Comment](https://github.com/sugarlabs/terminal-activity/pull/47)


`15-Aug` - Sugar - 502 Bad Gateway, When trying to view an activity help page [#931](https://github.com/sugarlabs/sugar/issues/931)



## Bugs opened in AbiWord:

Write - Segmentation faults while performing various actions
bugzilla.abisource.com/show_bug.cgi?id=13934

<details>
<summary>Click to view the complete bug report</summary>
<p>

```markdown

Bug#: 13934	Product:  AbiWord	Version: 3.0.4	Platform: PC
OS/Version: Linux	Status: NEW	Severity: major	Priority: P3
Resolution: 	Assigned To: domlachowicz@gmail.com	Reported By: shaansubbaiah.cs18@bmsce.ac.in	QA Contact: abisource-qa-spam@abisource.com
Component: Front End - GTK	Target Milestone: ---
URL: 
Summary: Segmentation faults while performing various actions
Keywords:  
Status Whiteboard: 
Opened: 2020-08-11 12:09

    I have found some bugs that can be reproduced in the minimal AbiWord python
    snippet.
    I can reproduce it on Debian 10(Buster) and Debian 11(Bullseye) with AbiWord
    v3.0.2-8 and v3.0.4~dfsg-2 respectively.

    Bugs found that crash the AbiWord instance:
    1. Resizing a cell in a table vertically
    2. Moving an image to the extreme left/right of the page
    3. Right Click -> Insert Table
    4. Right Click -> Click Paragraph -> Click Tabs
    5. Right Click -> Set Language



    Log when following 3 (Right Click -> Insert Table), in Debian 11
    ```
    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_radio_button_get_group:
    assertion 'GTK_IS_RADIO_BUTTON (radio_button)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_spin_button_set_value:
    assertion 'GTK_IS_SPIN_BUTTON (spin_button)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_spin_button_set_value:
    assertion 'GTK_IS_SPIN_BUTTON (spin_button)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_toggle_button_get_active:
    assertion 'GTK_IS_TOGGLE_BUTTON (toggle_button)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.135: gtk_widget_set_sensitive:
    assertion 'GTK_IS_WIDGET (widget)' failed
    /usr/lib/python3/dist-packages/gi/overrides/Gtk.py:1632: Warning: invalid
    (NULL) pointer instance
    return _Gtk_main(*args, **kwargs)
    /usr/lib/python3/dist-packages/gi/overrides/Gtk.py:1632: Warning:
    g_signal_connect_data: assertion 'G_TYPE_CHECK_INSTANCE (instance)' failed
    return _Gtk_main(*args, **kwargs)

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.137: gtk_window_set_title:
    assertion 'GTK_IS_WINDOW (window)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.137: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.137: gtk_label_set_text: assertion
    'GTK_IS_LABEL (label)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.137:
    gtk_spin_button_set_increments: assertion 'GTK_IS_SPIN_BUTTON (spin_button)'
    failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.137: gtk_spin_button_set_range:
    assertion 'GTK_IS_SPIN_BUTTON (spin_button)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.137: gtk_spin_button_set_value:
    assertion 'GTK_IS_SPIN_BUTTON (spin_button)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.137: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1216): Gtk-CRITICAL **: 12:49:34.137: gtk_label_get_label: assertion
    'GTK_IS_LABEL (label)' failed
    Segmentation fault
    ```

    Log when following 4 (Right Click -> Click Paragraph -> Click Tabs), in Debian
    11
    ```
    (minabi.py:1240): Gtk-CRITICAL **: 13:02:57.054: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1240): Gtk-CRITICAL **: 13:02:57.054: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1240): Gtk-CRITICAL **: 13:02:57.054: gtk_window_set_title:
    assertion 'GTK_IS_WINDOW (window)' failed

    (minabi.py:1240): Gtk-CRITICAL **: 13:02:57.054: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1240): Gtk-CRITICAL **: 13:02:57.054: gtk_label_set_text: assertion
    'GTK_IS_LABEL (label)' failed

    (minabi.py:1240): Gtk-CRITICAL **: 13:02:57.054: gtk_builder_get_object:
    assertion 'GTK_IS_BUILDER (builder)' failed

    (minabi.py:1240): Gtk-CRITICAL **: 13:02:57.054: gtk_label_get_label: assertion
    'GTK_IS_LABEL (label)' failed
    Segmentation fault
    ```



    Minimal AbiWord python snippet used:
    ```
    #!/usr/bin/python

    import gi

    gi.require_version('Abi', '3.0')
    from gi.repository import Abi

    gi.require_version('Gtk', '3.0')
    from gi.repository import Gtk

    win = Gtk.Window(title="PyAbiword")
    Abi.init([])
    widget = Abi.Widget()
    win.add(widget)
    win.connect("delete-event", Gtk.main_quit)
    win.show_all()

    Gtk.main()
    ```



    Debian 11(Bullseye):
    libgtk-3-0                     3.24.20-1
    libgtk2.0-bin                  2.24.32-4
    gir1.2-abi-3.0                 3.0.4~dfsg-2 
    libabiword-3.0                 3.0.4~dfsg-2

    Debian 10(Buster):
    libgtk-3-0                     3.24.5-1
    libgtk2.0-0                    2.24.32-3
    gir1.2-abi-3.0                 3.0.2-8
    libabiword-3.0                 3.0.2-8


    Please let me know if any other information is required.
```

</p>
</details>

## Bugs opened in Debian:
Browse - Fails to start, error "glib-compile-schemas: not found
bugs.debian.org/963068
<details>
<summary>Click to view the complete bug report</summary>
<p>

```markdown
From: Shaan Subbaiah <shaansubbaiah.cs18@bmsce.ac.in>
To: Debian Bug Tracking System <submit@bugs.debian.org>
Subject: sugar-browse-activity: Fails to start, error "glib-compile-schemas: not found"
Date: Thu, 18 Jun 2020 19:30:36 +0530

Package: sugar-browse-activity
Version: 205-2
Severity: important

Dear Maintainer,

*** Reporter, please consider answering these questions, where appropriate ***

   * What led up to the situation?
	Installing sugar-browse-activity.

   * What exactly did you do (or not do) that was effective (or ineffective)?
	Start Browse Activity from Sugar.

   * What was the outcome of this action?
	Browse does not start.

Error in org.laptop.WebActivity-1.log:

sh: 1: glib-compile-schemas: not found
Traceback (most recent call last):
  File "/usr/bin/sugar-activity3", line 5, in <module>
    activityinstance.main()
  File "/usr/lib/python3/dist-packages/sugar3/activity/activityinstance.py", line 230, in main
    instance = create_activity_instance(activity_constructor, activity_handle)
  File "/usr/lib/python3/dist-packages/sugar3/activity/activityinstance.py", line 59, in create_activity_instance
    activity = constructor(handle)
  File "/usr/share/sugar/activities/Browse.activity/webactivity.py", line 192, in __init__
    self._tabbed_view = TabbedView(self)
  File "/usr/share/sugar/activities/Browse.activity/browser.py", line 147, in __init__
    self.settings = _get_local_settings(activity)
  File "/usr/share/sugar/activities/Browse.activity/browser.py", line 129, in _get_local_settings
    source = Gio.SettingsSchemaSource.new_from_directory(path, None, True)
gi.repository.GLib.Error: g-file-error-quark: Failed to open file “/home/ssbc/.sugar/default/org.laptop.WebActivity/data/schemas/gschemas.compiled”: open() failed: No such file or directory (4)

As a workaround, installing libglib2.0-dev package fixes the issue.
Browse is then able to start successfully.

*** End of the template - remove these template lines ***


-- System Information:
Debian Release: bullseye/sid
  APT prefers unstable
  APT policy: (990, 'unstable'), (500, 'stable-updates'), (500, 'testing'), (500, 'stable')
Architecture: amd64 (x86_64)

Kernel: Linux 5.6.0-2-amd64 (SMP w/2 CPU cores)
Locale: LANG=en_IN, LC_CTYPE=en_IN (charmap=UTF-8), LANGUAGE=en_IN:en (charmap=UTF-8)
Shell: /bin/sh linked to /usr/bin/dash
Init: systemd (via /run/systemd/system)
LSM: AppArmor: enabled

Versions of packages sugar-browse-activity depends on:
ii  dconf-gsettings-backend [gsettings-backend]  0.36.0-1
ii  gir1.2-evince-3.0                            3.36.5-2
ii  gir1.2-gdkpixbuf-2.0                         2.40.0+dfsg-5
ii  gir1.2-glib-2.0                              1.64.1-1
ii  gir1.2-gtk-3.0                               3.24.20-1
ii  gir1.2-pango-1.0                             1.44.7-4
ii  gir1.2-rsvg-2.0                              2.48.7-1
ii  gir1.2-soup-2.4                              2.70.0-1
ii  gir1.2-sugarext-1.0                          0.117-1
ii  gir1.2-telepathyglib-0.12                    0.24.1-2+b1
ii  gir1.2-webkit2-4.0                           2.28.2-2+b1
ii  python3                                      3.8.2-3
ii  python3-cairo                                1.16.2-3
ii  python3-dbus                                 1.2.16-2
ii  python3-gi                                   3.36.0-3
ii  python3-sugar3                               0.117-1

Versions of packages sugar-browse-activity recommends:
ii  ca-certificates  20200601

sugar-browse-activity suggests no packages.

-- no debconf information

```

</p>
</details>



## Pull Requests


`21-Jun` - Pippy - Fix dark mode is not set on new tabs [#83](https://github.com/sugarlabs/Pippy/pull/83) - `Merged`


`30-Jun` - Read - Fix wrong logging label on highlight [#44](https://github.com/sugarlabs/read-activity/pull/44) - `Merged`


`08-Jul` - JukeBox - Fix playlist navigation [#31](https://github.com/sugarlabs/jukebox-activity/pull/31) - `Merged`


`24-Jul` - Sugar Toolkit GTK3 - Fix bundlebuilder not handling empty arguments [#452](https://github.com/sugarlabs/sugar-toolkit-gtk3/pull/452) - `Merged`


`29-Jul` - Memorize - Fix TypeError due to Bool arguments in ElementTree [#30](https://github.com/sugarlabs/memorize-activity/pull/30) - `Merged`


`02-Aug` - Calculate - Fix issues occured while raising RuntimeError [#69](https://github.com/sugarlabs/calculate-activity/pull/69) - `Merged`


`08-Aug` - Terminal - Fix issues in theme toggling button [#44](https://github.com/sugarlabs/terminal-activity/pull/44) - `Merged`


`10-Aug` - Terminal - Fix theme not switching to dark on toggle [#46](https://github.com/sugarlabs/terminal-activity/pull/46) - `Merged`


`12-Aug` - Browse - Fix HTTP 403 Error on copying images [#114](https://github.com/sugarlabs/browse-activity/pull/114) - `Merged`


`19-Aug` - Pippy - Fix no source tab on resume of empty file [#85](https://github.com/sugarlabs/Pippy/pull/85) - `Merged`



## Other


`21-Jul` - Find Words - Find fix for error in Web Activity [Github Comment](https://github.com/sugarlabs/sugar-web/issues/135#issuecomment-663847858)
