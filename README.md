fontconfig profile
==================

This repository contains a customized configuration file to
[fontconfig](http://fontconfig.org) with a comfortable look on CJK
characters.

Currently, Chinese and Japanese profile are supported.

The main work on this configuration is to make a reasonable font fallback
strategy.

Prerequisite
------------

You are expected to have following fonts in your fonts path:

* `/usr/share/fonts`
* `/usr/share/X11/fonts/Type1`
* `/usr/share/X11/fonts/TTF`
* `/usr/local/share/fonts`
* `$XDG_DATA_HOME/fonts` defaults to `~/.local/share/fonts`

(`~/.fonts` directory is deprecated, and it's support will be
removed in the future)

**ASCII Font Support**

* DejaVu Serif (ASCII Serif)
* STIXGeneral (ASCII Serif)
* DejaVu Sans Condensed (ASCII Sans)
* Courier Typewritter (ASCII Monpspace Courier 10 Pitch modified v2)

  Monospace Font based on "Courier 10 Pitch" modified by @Thynson to get
  better appearance.

**CJK Font Support**

* Droid Sans (CJK Sans including "Droid Sans Fallback"&"Droid Sans Japanese")
* Adobe Song Std (ZH Serif "Adobe 宋体")
* AR PLBaosong2GBK Light (ZH Serif "文鼎报宋")
* Adobe Ming Std (JPN Serif "Adobe 明體")
* IPAMincho (JPN Serif "IPA 明朝")
* IPAexMincho (JPN Serif "IPAex 明朝")

**Optional Font Support**

* Courier X (ASCII Monospace.opt Courier 10 Pitch modified v3)

  Monospace Font based on "Courier 10 Pitch" modified by @Thynson with ASCII
  characters aligned to CJK characters. (Experimental)

* Adobe Fangsong Std (ZH Monospace.opt "Adobe 仿宋")

First, use `fc-list` to check for all available fonts you will need.

`DejaVu` font series are commonly installed by default across various
distributions. You can get Adobe&copy; Fonts from its product granted.

"[Courier X](https://github.com/thynson/Courier-X-Fonts)" and
"[Courier Typewritter](https://github.com/kirisetsz/Courier-Typewritter-Fonts)"
can be obtained from their github pages.

As for other missing font, refer to font wiki of your linux distribution to find packages.
Or, just find the font file and install them to the paths.

And for me, it's
[fedora wiki](http://fedoraproject.org/wiki/Category:Packaged_fonts)

And `yum install stix-fonts ipa-*-fonts google-droid-*-fonts` should install
all fonts available from repository.

Application
-----------

Typically, the repository is located at `$XDG_CONFIG_HOME/fontconfig`
in which `$XDG_CONFIG_HOME` refers to `~/.config` if not specified.

Thus, if you have not yet set your fontconfig, use following script to
checkout the repository.

```shell

cd ~/.config # Default $XDG_CONFIG_HOME
git clone https://github.com/kirisetsz/fontconfig.git

```

Otherwise, you are expected to backup your configuration first and put your
customization into `~/.config/fontconfig/conf.d/` which will be
automatically included to the configuration.
**Any help from your fork is welcomed :)**

The repository, by default, enables Chinese font solution. When you'd like
to have a tweak, simply refers to `conf.avail` to check for avaliable
options.

Enable options by manage symbolic link
(`ln -s ./conf.avail/??-XXX.conf ./conf.d/`)

Disable the option just remove the link from `conf.d`

40-console.conf
---------------

This configuration exports a font shortcut called `Console`.
It's designed to be used under terminal with
[Courier X](https://github.com/thynson/Courier-X-Fonts) and
Adobe Fangsong Std font family

You cannot pickup the font shortcut directly from a gtk font chooser.
Thus, one can use `dconf` to enable the font on a gnome-terminal or some
other terminal emulators.

For gnome-terminal,
find out profile id using `dconf list /org/gnome/terminal/legacy/profiles:/`

Then, write the font setting to the profile
`dconf write /org/gnome/terminal/legacy/profiles:/<Profile ID>/font "'Console 14'"`

For more information about the configuration detail, see
<http://www.freedesktop.org/wiki/Software/fontconfig/>

Contributor
-----------

Thynson &lt;thynson&#x2606;dummi.org&gt;

kirisetsz &lt;trinity&#x2605;dummi.org&gt;

License
-------

(The MIT License)

